# mn_installer.sh
script to install masternode for pirl on stock ubuntu 16 64bit
This should be run as root and will do the following
1. update your boxes packages from the ubuntu repos
2. make a pirl username to run the service as, and a home directory if eeeded
3. download the pirl masternode binary and set permissions on it
4. setup a systemd service named pirlnode, enable it, and start it
5. setup the template for the needed environment variables for it to report properly to poseidon
6. install the ufw firewall and open needed ports 
7. update the ssh daemon to run on a non-standard port of your choice

To RUN THIS:

1. login as root on a fresh ubuntu 16 64 bit install
2. clone with "git clone https://github.com/phatblinkie/mn_installer.sh.git"
3. cd into the mn_installer.sh directory
4. edit the mn_installer.sh file, at the top you will see a few variables to set with descriptions
additional details are in the file

        #this one is on your masternode page, and is unique for each masternode you have
        #replace with your own values from poseidon
        ## https://poseidon.pirl.io/accounts/masternodes-list-private/
        MASTERNODE="----"

        #this one is on your account page, and is the only one for your account
        ## https://poseidon.pirl.io/accounts/settings/
        TOKEN=""


        SSHD_PORT="22"    #(recommended range is 1025-65535)

        YOURIP="a.b.c.d"       #no cidr addressing please only a single ip here

        RUNAS_USER="root"      #recommended username is pirl or root

5. change permissions on the file with `chmod 0755 mn_installer.sh`
6. execute the file with ./mn_installer.sh

