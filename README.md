# Codeigniter Setting

## Base URL Config

    $config['base_url'] = ((isset($_SERVER['HTTPS']) && $_SERVER['HTTPS'] == "on") ? "https" : "http"); 
    $config['base_url'] .= "://".$_SERVER['HTTP_HOST']; 
    $config['base_url'] .= str_replace(basename($_SERVER['SCRIPT_NAME']),"",$_SERVER['SCRIPT_NAME']);

## .htaccess

    <IfModule mod_rewrite.c>
      Options -Indexes 
      RewriteEngine  On
      RewriteCond  $1 !^(index\\.php|resources|robots\\.txt)
      RewriteCond  %{REQUEST_FILENAME} !-f 
      RewriteCond  %{REQUEST_FILENAME} !-d 
      RewriteRule ^(.+)$ index.php?/$1 [L,QSA]
    </IfModule>

