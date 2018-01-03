#### Run Jupyter Notebook from Vagrant on Windows Browser
````
1. Make sure Vagrant fowarded_port is uncommented and the guest and host ports are changed.
 a. config.vm.network "forwarded_port", guest: 8888, host: 8888
2. Run the command below after vagrant ssh.
 a. jupyter notebook --ip=0.0.0.0 --no-browser
3. Open the browser with http://localhost:8888.

````
