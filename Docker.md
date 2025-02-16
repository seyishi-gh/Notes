### Custom options in `docker run`<br>

### Important
&ensp;`-it`: Runs the container in interactive mode with a terminal.<br>
&ensp;`ubuntu:latest`: Uses the latest Ubuntu image.<br>
&ensp;`/bin/bash`: Starts a Bash shell inside the container.<br>

### Common 
&ensp;`--name` `<name-of-container>`: Names the container for easy reference.<br>
&ensp;`--memory="<memory-space>"`: Limits the container to eg. `3g` of RAM.<br>
&ensp;`--net <my_custom_network>`: Connects the container to the custom network.<br>
&ensp;`--ip <custom-ip>`: Assings a specific IP address to the container.<br>
&nbsp;`-p <host-port>:<container-port>`: Maps port `host-port` to port `container-port` in the container.

### Examples for commands lines
1. Running a container with a custom ip and memory.<br>
`docker run -it --name my_ubuntu_container --memory="3g" --net my_custom_network --ip 192.168.100.10 ubuntu:latest /bin/bash`<br>