First Create Folder : Django_Project
Then Create Another Folder : ecom(mainfolder) [ IN Django_Project FOLDER ]

----- Open CMD in ecom(mainfolder) -----

-> M:\DJANGO\BACKUP_PROJECT\ecom(mainfolder)> python -m venv myenv

-> M:\DJANGO\BACKUP_PROJECT\ecom(mainfolder)> myenv\Scripts\activate     [ TO ACTIVATE VIRTUAL ENVIRONMENT ]

-> (myenv) M:\DJANGO\BACKUP_PROJECT\ecom(mainfolder)> pip install django   [ TO INSTALL DJANGO ]

-> piplist [ OPTIONAL ]

-> (myenv) M:\DJANGO\BACKUP_PROJECT\ecom(mainfolder)> django-admin startproject newP  

-> (myenv) M:\DJANGO\BACKUP_PROJECT\ecom(mainfolder)> cd newP [ CHANGE DIRECTORY ]

-> (myenv) M:\DJANGO\BACKUP_PROJECT\ecom(mainfolder)\newP> code . [ TO OPEN THAT PROJECT IN VS CODE ]

_ _ _ _ _ PROJECT SUCCESSFULY CREATED AND OPENED IN CODE _ _ _ _ _ 


----- THIS PROCESS INSIDE THE VS CODE -----

First Create New Terminal and then select PROMPT then type following :
-> (myenv) M:\DJANGO\BACKUP_PROJECT\ecom(mainfolder)\newP> python manage.py runserver

Then Open Given Link on that Terminal : http://127.0.0.1:8000/ [ THIS IS BASE URL ]

IN TERMINAL :-
-> To Stop the Server : CTRL + C [ THEN URL WILL NOT WORK ]
[ IF WE WANT TO RUN AGAIN SAME PROJECT THEN FOLLOW PREVIOUS STEP ]


***** SIMPLY COPY FOLLOWING COMMANDS *****

<ol>
  <li>python -m venv myenv</li>
  <li>myenv\Scripts\activate</li>
  <li>pip install django</li>
  <li>pip list (Optional)</li>
  <li>django-admin startproject ProjectName</li>
  <li>cd ProjectName</li>
  <li>code .</li>
</ol>


After Complete this 

<ol>
  <li>python manage.py runserver</li>
</ol>

Then Open Given Link on that Terminal
