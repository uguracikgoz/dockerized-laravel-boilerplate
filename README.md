# Dockerized laravel boilerplate

# 🇬🇧EN
The project to build up nginx, phpfpm, mysql, adminer by using docker-compose.
Php developers may use for getting started when get hired or moved up to another pc.
This project is developed for development env. Please do not forget to reconsider file permissions before going live for project's security.

Requirements:
-   docker
-   docker-compose
-   git
-   globally installed composer
-   give file permission to repo folder

TODO :
- clone the project from github
- go to regarding folder with cd command and go with command :"sudo docker-compose up -d"

OUTPUT : 
- on http://localhost:80, defaultly installed laravel project which is located in project folder can be accessed.
- mysql is supposed to work over 3306 port.
- you may access to adminer to control out mysql databases with ui over http://127.0.0.1:8080
    - to react at mysql with adminer
        -   server   : mysql
        -   username : root
        -   password : MYSQL_ROOT_PASSWORD variable that is defined in docker-compose.yml folder as a configuration parameter. The default value is expPass2019!
- In case of want to change any config related to nginx, the default.conf file is located and mounted on the same folder with the project.

p.s. : You may stop it with "sudo docker-compose down"
p.s. : Please stop service that may use ports those defined in docker-compose file such may : mysql, nginx or apache

Some more spesification :
- You may leave sql files into mysql-dump folder that you want to be imported in mysql. ci_sessions.sql table has already located as default for codeigniter session handling.
- You may want to create or implement a different laravel project into project folder. If you do, you need to consider mysql configuration that is shown on following:
```
        'mysql' => [
            'driver' => 'mysql',
            'host' => env('DB_HOST', 'localhost'),
            'port' => env('DB_PORT', '3306'),
            'database' => env('DB_DATABASE', ''),
            'username' => env('DB_USERNAME', ''),
            'password' => env('DB_PASSWORD', ''),
            'charset' => 'utf8mb4',
            'collation' => 'utf8mb4_unicode_ci',
            'prefix' => '',
            'strict' => true,
            'engine' => null,
            'modes'  => [
                'ONLY_FULL_GROUP_BY',
                'STRICT_TRANS_TABLES',
                'NO_ZERO_IN_DATE',
                'NO_ZERO_DATE',
                'ERROR_FOR_DIVISION_BY_ZERO',
                'NO_ENGINE_SUBSTITUTION',
            ]
        ]
```

# 🇹🇷TR
Php developer işe başlarken kullanabileceği compose projesidir.

Gereksinimler :
- docker
- docker-compose
- git
- global kapsamda kurulu composer
- dosya izinleri verilmeli

Yapılması gerekenler :
- Proje git üzerinden çekilir
- cd komutu ile indirilen klasöre gidilir ve "sudo docker-compose up -d" komutu kullanılır

Çıktı :

- http://localhost:8181 üzerinden proje üzerinde code klasörünün içerisindeki default gelen codeigniter projesine erişilebilir.
- 3306 portu üzerinden mysql çalışıyor olacaktır.
- http://127.0.0.1:8080 üzerinden adminera erişerek mysql üzerindeki veritabanlarını görsel arayüz ile kontrol edebilirsiniz.
    -   adminer üzerinden veritabanına ulaşabilmek için 
        -   server   : mysql
        -   username : root
        -   password : docker-compose.yml dosyasının içerisinde belirttiğiniz MYSQL_ROOT_PASSWORD değerinin karşılığıdır. Default olarak expPass2019! belirtilmiştir.
- Gerektiği taktirde değişiklikleri yapabilmek amaçlı nginx configurasyon dosyası default.conf olarak klasörün içerisine mount edilmiştir.

not : "sudo docker-compose down" ile durdurabilirsiniz.
not : kurulumdan önce lütfen fiziksel ortamda docker-compose.yml dosyasının içerisinde bulunan portları kullanan servisleri durdurun. Örn : mysql, nginx veya apache gibi

Biraz daha detay :
- Mysql içerisinde başlangıç için import etmek istediğiniz sql tablolarını, mysql-dump klasörüne bırakabilirsiniz. Default olarak codeigniter'ın session management için ihtiyaç duyduğu ci_session.sql tablosu bırakılmıştır.
- Eğer farklı bir laravel projesi implementasyonu düşünüyorsanız lütfen implementasyondan sonra aşağıdaki database ayarlarını göz önünde bulundurunuz:
```
        'mysql' => [
            'driver' => 'mysql',
            'host' => env('DB_HOST', 'localhost'),
            'port' => env('DB_PORT', '3306'),
            'database' => env('DB_DATABASE', ''),
            'username' => env('DB_USERNAME', ''),
            'password' => env('DB_PASSWORD', ''),
            'charset' => 'utf8mb4',
            'collation' => 'utf8mb4_unicode_ci',
            'prefix' => '',
            'strict' => true,
            'engine' => null,
            'modes'  => [
                'ONLY_FULL_GROUP_BY',
                'STRICT_TRANS_TABLES',
                'NO_ZERO_IN_DATE',
                'NO_ZERO_DATE',
                'ERROR_FOR_DIVISION_BY_ZERO',
                'NO_ENGINE_SUBSTITUTION',
            ]
        ]
```

🧿 
