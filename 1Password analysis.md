- [Main note](/main.md)
- [Author](https://github.com/seyishi-gh) note - I'm not paying 4$ for the basic subscription 😭. So I will looking online for specific information. The idea is not looking straight to the answer. I'm thinking from "scratch" looking for the subjects that make this problem. It's just more fun like that. Stupid -> Genius -> Stupid.

## Trying Reverse engineering

### Is [1Password](https://1password.com/product/password-manager) working as I think?
- When you click in "sign in" in 1Password website. They ask for email, secret key and password. So I assume that this works with a hashed string in the 1Password database using something like bcrypt to match this string uploaded, then this key is localed stored in the website, like, maybe cookies, jwt or localStorage.<br>
But when you "sign up" It's says that this two passwords are esencial to the protection of the data, so.
They make a new unique secret key for each device. Probably is the private key in the end to end encryption or just making a new random string.<br>
In end to end encryption the public key usually is stored only for one user, It's more difficult storing a lot of public keys, but It's possible. The question is how they are doing it to encrypt this two hashed string. This must be imposible. Maybe they just store the plain secret key in something like jwt, then encrypt this with the public key of the service, so all is hashed and "secure".<br>

#### Sign up
&nbsp;1. Normal sign up with username, email and password.<br>
&nbsp;2. Creating a random secret key and temp stored securely in local.<br>
&nbsp;3. Get and create end to end data.<br>
&nbsp;4. Store all this shit in local machine like jwt or some fancy way.<br>

#### Sign in
&nbsp;Basically all the same except `2`<br>
&nbsp;2. Getting the plain secret key for login.

#### Normal exchange
&nbsp;1. Decrypt the encrypted local stored data (eg. jwt).<br>
&nbsp;2. Comparing the hashed data in server side.<br>
&nbsp;3. Getting the data encrypted and decrypt it in local.
&nbsp;4. User see all normal 👍.

- They probably get all the items at once, at the end all of this items have an id (uuid?).