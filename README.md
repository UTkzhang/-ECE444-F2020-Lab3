# ECE444-F2020-Lab4-And-Lab5
# Deliverable 1
This README along with all the changes should be in the branch "lab4_Microservice_Experiment", in the Lab3 repo.
# Deliverable 2
![deliverable 2 screenshot 1](https://github.com/UTkzhang/ECE444-F2020-Lab3/blob/master/assignment_imgs/Snip20201005_43.png)
![deliverable 2 screenshot 2](https://github.com/UTkzhang/ECE444-F2020-Lab3/blob/master/assignment_imgs/Snip20201005_44.png)
![deliverable 2 screenshot 3](https://github.com/UTkzhang/ECE444-F2020-Lab3/blob/master/assignment_imgs/Snip20201005_45.png)
![deliverable 2 screenshot 4](https://github.com/UTkzhang/ECE444-F2020-Lab3/blob/master/assignment_imgs/Snip20201005_46.png)

# Deliverable 3
The biggest difference between a Virtual Machine (VM) and a container is that VMs each operate on a unique Guest operating system (OS), and maintains its own OS resources, binaries, libraries, and applications, whereas a container sits on top of a host OS and shares the OS kernal. Both provide an isolated and consistent environment for developer applications to run on, but containers are more agile (faster to spin up and take down), lighter in size (as they do not have to bundle together all the OS resources), and better utilize system resources with less overhead on the virtualization component. 

A VM has "virtual" access to hardware resources through a hypervisor, meaning that each OS runs on a virtualized computer and sees its own "complete" set of processors, memory, storage, that is in reality a fraction of the physical resources. These operating systems on VMs do not share resources with each other, unlike programs running on the same OS. Contrarily, containers run as discrete processes on the OS, just like any other executable, and draws from the same pool of hardware resources as other programs on the host OS. The way that containers achieve its portability is by virtualizing the OS, rather than the computer hardware, by establishing its own file system and other support programs to run the contained software.


# ECE444-F2020-Lab3
 ECE444-F2020-Lab3 by Gensheng Zhang, note that this repo is a clone of https://github.com/miguelgrinberg/flasky

# Activity 1
Example at the end of chapter 3 modified, I chose to modify the /user/\<name\> route instead of the / route shown in the screenshot, because I didn't think it made alot of sense to hard-code the name for the / page. I'd rather the user be able to pass the name in through the URL path.
![activity 1 screenshot](https://github.com/UTkzhang/ECE444-F2020-Lab3/blob/master/assignment_imgs/Snip20200928_33.png)

# Activity 2
Default view of example 4.7 with the added email address field
![activity 2 screenshot 1](https://github.com/UTkzhang/ECE444-F2020-Lab3/blob/master/assignment_imgs/Snip20200929_34.png)

Filled in First name and UofT email address, clicked submit
![activity 2 screenshot 2](https://github.com/UTkzhang/ECE444-F2020-Lab3/blob/master/assignment_imgs/Snip20200929_35.png)

Filled in First name and Last name, and only First name in the email field, html validator prints error message
![activity 2 screenshot 3](https://github.com/UTkzhang/ECE444-F2020-Lab3/blob/master/assignment_imgs/Snip20200929_37.png)

Filled in First name and Last name (name change), and gmail address (email change), display the flash messages asked for by the lab
![activity 2 screenshot 4](https://github.com/UTkzhang/ECE444-F2020-Lab3/blob/master/assignment_imgs/Snip20200929_38.png)

# Acitivty 3
SQL databases are relational databases stored in tables (relations). This is very much like a traditional spreadsheet, with headers defining columns of data, and rows being the entries of data. Each table has a fixed number of columns (the schema for the relation), with a variable number of rows (one can add/remove/modify entries). The reason why a SQL database is relational is because tables have keys such as the primary key which holds a unique identifier for each row stored in the table, and the foreign key which reference the primary key of a row from a different table. These foreign key - primary key links form relationships between tables, and hence the term "relational databases". SQL databases are queried by the Structured Query Language (SQL). Due to the relationships, joining data between multiple relations is a strength of SQL.
 
NoSQL databases, on the other hand, do not follow the relational model described above. For example, data can be organized as collections, instead of tables, and documents, instead of rows. This isolated document approach makes joining data between collections/documents difficult, as there are no defined links. NoSQL databases, however, are easier to query as the collection -> document hierarchy is easier to understand in my opinion, and each document is mostly self-contained with all the information you'd need for a given query, abstracting away some of the complicated query logic that SQL may require. Also, the textbook mentions that NoSQL databases may perform between as it relaxes some of the consistency requirements which SQL databases demand. It also mentions, though, that SQL databases are more efficient and compact in terms of storing structured data. 

I have worked with both SQL (SQLserver, PostgresDB), and NoSQL (MongoDB) databases, and I believe that for data that doesn't require a lot of referencing and joins, NoSQL is easier to use. A good example of this is a User with a favourite Recipe.

In SQL, we may have a table for USER, and a table for RECIPE, with a foreign key from USER table that identifies the user's favourite recipe from the RECIPE table. This requires a logically sound SQL query (though its not complicated). With something like MongoDB, we can use embedded documents instead, having a User {//info about user} document and a FavouriteRecipe{//recipe} document, and embedding this FavouriteRecipe document inside User, User{//info about user, FavouriteRecipe{//recipe}}. As the textbook mentions, updating the recipe in the NoSQL variant will require a large number of operations (update the recipe for every user with this favourite recipe). On the other hand, querying the NoSQL version will be faster because it only requires fetching one self-contained document (no joins/other operations). 
