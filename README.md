# odootrain
odootraining 


Useful commands

    To run a command for postgresql db, either your user should have enough access rights, or you should use postgres linux user.
        We can switch to postgres user with this command sudo su postgres (type your password when asked). Now we are in a command prompt of the postgres user and we can come back to our user account with exit or pressing ctrl+d.
        Or we can run one command as postres user with sudo -u postgres COMMAND

    Delete a database:
        dropdb -U postgres db name
        sudo su postgres; dropdb db name ; exit
        sudo -u postgres dropdb db name

    Create a user for odoo in postgres
        sudo -u postgres createuser -d -R -S user name

    killing odoo-bin
        Press ctrl-c on the terminal which odoo-bin is running
        pkill -f -9 odoo-bin <-- use with care, can kill anything
        ps aux | grep odoo-bin find process id (PID) and kill with kill -9 PID
        lsof -i4:8069 -Fp | cut -c2- | xargs kill -9
