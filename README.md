# backup-mysql
   ## Back Up MySQL With Mysqldump And Crontab:
Backups of MySQL are made for ensuring data protection, facilitating disaster recovery, maintaining data integrity, complying with legal and regulatory requirements, providing version control, supporting testing and development, ensuring business continuity, and optimizing database performance. <br>
we made it with MySQLdump and crontab, MySQLdump is a tool for MySQL to made backups and the crontab are made to make this process automatic. <br>
You need to take care of how many backups you want to keep and delete the rest.
### Setup:
1. sudo su 
2. create a file as root in /root/.my.cnf:
   ```
   [client]
   user=root
   password=yourpassword
   ```
3. chmod 600 .my.cnf 
5. **this command is to backup all databases, change the path "/home/backups/db/" to the path where you want to store the backups:** <br> mysqldump -u root --all-databases > /home/backups/db/$(/bin/date +\%Y-\%m-\%d-\%H:\%M).sql.bak 
7. insert this command into crontab with this command and define how often you want the backup to happen: sudo crontab -u root -e 
8. **this command is to restore all the data into your mysql:** mysql -u root -p < the name of the backup you want to restore   
