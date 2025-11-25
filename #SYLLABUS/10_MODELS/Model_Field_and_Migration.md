<h2>Model Field and Migration</h2>

- First Go To `models.py` write Following code. </br></br>

<img width="1920" height="1080" alt="Screenshot 2025-11-25 223005" src="https://github.com/user-attachments/assets/cf183124-cf3a-42ef-aa03-4a7be9ac9f96" /> </br></br>

- GO TO Terminal and Execute Following Commands:
  1) `python manage.py makemigrations` : It creates a migration file, but does NOT apply it to the database.
  2) `python manage.py migrate` : It updates the actual database. </br></br>

- Go To `db.sqlite3`  and Click on Refresh Button. Your Table display here.
- In Our Case class name is `student_info` and `app name` is base thats why it is showing Table Name: `'base_student_info'`. </br></br>
<img width="1920" height="1080" alt="Screenshot 2025-11-25 225659" src="https://github.com/user-attachments/assets/a2cd025b-2a3b-4159-b3a1-ffb0f1597c5b" /> </br></br>


**-----------------------------------------------------------</br></br>**

✅ Line-by-Line Explanation

`from django.db import models`

- This line imports Django’s models module.
- It gives access to all model field types like CharField, IntegerField, DateField, etc.
- Without this import, you cannot create database models.

`class student_info(models.Model):`

- This creates a model class called student_info.
- The class inherits from models.Model, which means:
    Django will treat it as a database table.
    Django will create this table when you run migrations.
- Table name will automatically become:
`appname_student_info`


`s_name = models.CharField(max_length=100)`

- Creates a CharField, which stores short text.
- max_length=100 means the name cannot be longer than 100 characters.
- This will be a column in the database.


`s_add = models.CharField(max_length=100)`

- Another CharField for storing the student's address.
- Also limited to 100 characters.
- This will be another column in the same table.

📌 Additional Info

- Django automatically creates an id field (primary key), so you don't need to write it.

Table will look like:

id	s_name	s_add
