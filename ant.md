**Install Ant Manually on Ubuntu**<br>
*Add the below to the end of /etc/bash.bashrc*<br><br>
ANT_HOME=/apache-install-dir/apache-ant-version<br>
PATH=$PATH:$HOME/bin:$ANT_HOME/bin<br>
export ANT_HOME PATH
