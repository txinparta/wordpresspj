# WordPress clean instalation through Composer
Plugins and themes are located outside the wp folder, so we can manage them separately: on one hand themes and plugins and on the other wordpress itself.

**Structure**
- public/
  - wp-content/ &emsp;&emsp;&nbsp;&nbsp;It contains plugins and themes
  - wp/	&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;Our subdirectory install location for WordPress
  - .htaccess &emsp;&emsp;&emsp;&emsp;If necessary
  - index.php
  - wp-config.php

- vendor/
- .gitignore
- composer.json
- composer.lock
- local-config.php
- .gitignore

# Starting our project

>1. Create a folder: **mkdir my_folder**
- Be sure you have composer installed. If you don't have it installed globaly, you can donwload the composer.phar localy (<code>curl -sS https://getcomposer.org/installer | php</code>)

>2. Create folder **my_folder/public/**

>3. Create **composer.json**. Copy the file uploaded in txinparta/wordpresspj

>4. Create **.gitignore**

>5. Install WordPress: run **composer install** (or <code>php composer.phar install</code>)

>6. Copy and move
```
	cp -R public/wp/{wp-content,index.php,wp-config-sample.php} public/
	mv public/wp-config-sample.php public/wp-config.php
```

>7. Modify **public/index.php**:
```
	require( dirname( __FILE__ ) . '/wp-blog-header.php' );
	Replace by:
	require( dirname( __FILE__ ) . '/wp/wp-blog-header.php' );
```

>8. Configure **local-config.php**. 
Fill out database data connection and keys (https://api.wordpress.org/secret-key/1.1/salt/).

>9. Configure **public/wp-config.php**
In the same way as it is in this repository.
