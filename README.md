# MyCloset
Project for CSCI 3010.

By: Vananh Le & Isha Karki

This project is a website that allows users to essentially have their entirety of 
their closet all in one place. Based on a user's input of occasion or weather, our program will
find a relevant outfit for the user from the clothes in their closet. 

This project will heavily rely on PHP to act as the front end, back end, and integration layer. We intend to
use HTML/CSS for the front-end from PHP, as well as use SQL for the database.

To run this project, you must have XAMPP downloaded to your computer. XAMPP is a web server solution stack package developed by Apache Friends. Upon downloading, 
please be sure to start the MySQL Database server as well as the Apache Web Server. This will allow us to view the project in your browser.

Link to download XAMPP: https://www.apachefriends.org/index.html

Instruction for downloading XAMPP on Mac: https://www.youtube.com/watch?v=L2X6fDiqOC4
- Current version for Mac: 7.4.11

Instruction for dowloading XAMPP on Window 10: https://www.youtube.com/watch?v=N6ENnaRotmo
- Current version for Window 10: 7.4.11

Instruction for dowloanding XAMPP on Linux: https://www.youtube.com/watch?v=R5CUn5wGQGg
- Current version for Linux: 7.4.11

On Mac, you need to access your Applications folder where you'll see the folder containing the XAMPP files. In there, access your htdocs folder. Then, we would need to store the MyCloset folder. 
You might have to access the base directory of your Mac to see the XAMPP folder under Applications. To run the project, you need to have XAMPP in the background (APACHE and MySQL started).

On Window 10, you would need to access you Local Disk, find the htdocs folder in the XAMPP folder. You must store your MyCloset project within the htdocs folder. To run the project, you need to have XAMPP in the background (APACHE and MySQL started).

On Linux, check the location of your htdocs. It should be in opt/lampp, make sure your MyClass project is save in the htdocs folder. To run the project, please have XAMPP started and running in the background (APACHE and MySQL started).

To see the project in your browser, access your local host port for XAMPP / the foldername (in our case it will be localhost/MyCloset). Note the if you have a different port in your XAMPP (check in the XAMPP Control Panel for the port listed for the Apache file) you must include that port in the following manner (localhost:portnumber/MyCloset) 

To start XAMPP:
Windows: Look for the XAMPP Control Panel on your computer and open it, and start Module Apache and Module MySQL.
Mac: Navigate to "Manage Servers", click "MySQL Database" and hit "Start", and click "Apache Web Server" and hit "Start".
Linux: Similar to Mac.

To set up the database:

Make sure XAMPP is started! Go to your browser and access phpMyAdmin (localhost/phpMyAdmin or localhost:portnumber/phpMyAdmin)

Create a database call mycloset.

Execute the following SQL queries:

>CREATE TABLE IF NOT EXISTS account(
>    id INT(11) AUTO_INCREMENT, 
>    firstname TINYTEXT,
>    lastname TINYTEXT,
>    username TINYTEXT,
>    pwd LONGTEXT,
>    PRIMARY KEY(id)
);

>INSERT INTO account
>   (firstname,lastname,username,pwd)
>VALUES
>    ('firstname','lastname','yourusername',’yourpassword’
);

>CREATE TABLE IF NOT EXISTS clothing( idclothing INT NOT NULL AUTO_INCREMENT, typeofclothing TINYTEXT, color TINYTEXT, temp INT, pattern TINYTEXT, occasion INT, file_title LONGTEXT, PRIMARY KEY(idclothing) 
);

>CREATE TABLE IF NOT EXISTS outfits( idOutfit INT NOT NULL AUTO_INCREMENT, name TINYTEXT, bottoms INT, shirts INT, sweaters INT, onepieces INT, temperature INT, occasion INT, PRIMARY KEY(idOutfit) );

Getting the database working really depend on how you set up your XAMPP. To check if your database connection is correct, go to the MyCloset/includes/database_setup.php file to modify the username, password, and port as needed. 
![data_setup](checkpoints/screenshots/data_setup.png)
$dbServername="localhost:portnumber"; <= in replacement of portnumber, include the port where MySQL is running. To check this go to your XAMPP Control Panel, then check the port listed for MySQL

$dbUsername ="username"; <= in replacement of username, check your username for MySQL by going to "\xampp\phpMyAdmin\config.inc.php" and look at the line $cfg['Servers'][$i]['user'] = 'username'; and adjust the  database_setup.php accordingly

$dbPassword ="password"; <= in replacement of password, check your username for MySQL by going to "\xampp\phpMyAdmin\config.inc.php" and look at the line $cfg['Servers'][$i]['password'] = 'password'; and adjust the  database_setup.php accordingly

$dbName = "mycloset"; <= make sure your database for this project is named "mycloset"

To login to the site, go to localhost/MyCloset or localhost:portnumber/MyCloset. Then input the username and password that was set up in your mycloset database under the account table. To check the username and password that is under the account table, go to localhost/phpMyAdmin or localhost:portnumber/phpMyAdmin, then click on mycloset schema, then click on the account table to view

