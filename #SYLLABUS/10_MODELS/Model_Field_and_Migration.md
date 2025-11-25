<h2>Model Field and Migration</h2>

- First Go To `models.py` write Following code. </br></br>

<img width="1920" height="1080" alt="Screenshot 2025-11-25 223005" src="https://github.com/user-attachments/assets/cf183124-cf3a-42ef-aa03-4a7be9ac9f96" /> </br></br>

- GO TO Terminal and Execute Following Commands:
  1) `python manage.py makemigration` : It creates a migration file, but does NOT apply it to the database.
  2) `python manage.py migrate` : It updates the actual database. </br></br>

- Go To `db.sqlite3`  and Click on Refresh Button. Your Table display here.
- In Our Case class name is `student_info` and `app name` is base thats why it is showing Table Name: `'base_student_info'`. </br></br>
<img width="1920" height="1080" alt="Screenshot 2025-11-25 225659" src="https://github.com/user-attachments/assets/a2cd025b-2a3b-4159-b3a1-ffb0f1597c5b" /> </br></br>
