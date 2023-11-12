# backup-mysql
1. create a file as root in /root/.my.cnf:
   [client]
   user=root
   password=yourpassword
2. chmod 600 .my.cnf
3. mysqldump --databases example_db > /home/backups/db/$(/bin/date +\%Y-\%m-\%d).sql.bak
4. insert this command into /etc/crontab with what frequencies that you want
5. mysql -u root example_db < 2023-11-12.sql.bak  # this command for restore the db 
