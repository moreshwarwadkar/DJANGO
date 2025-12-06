<h2>API ( DJANGO REST FRAMEWORK [ DRF ] )</h2></br></br>

**`1) CREATE FOLDER : To_DO </br>`**
- Inside That Folder Create Virtual Invironment. </br>
- Then Create Two Project : `backend` and `frontend`.</br></br>



FIRST OPEN `backend` FOLDER </br></br>

- `python manage.py startproject to_api` ( CREATE todo_api APP )</br>
- Register App in `settings.py` File.</br>
- Create URL : </br>

<img width="1920" height="1080" alt="Screenshot 2025-12-06 080353" src="https://github.com/user-attachments/assets/c3f91d71-cdc5-4366-a9cf-c1c7cbcee14b" /></br></br>


- `pip install djangorestframework`</br>
- Register in a `'setting.py'` File ( `rest_framework` )</br></br>

OPEN `model.py` File and Write Following Code:</br>

<img width="1920" height="1080" alt="Screenshot 2025-12-06 073634" src="https://github.com/user-attachments/assets/36b204b5-cea8-46da-bfe3-0bfe95c8000b" /></br></br>

The Execute Following Commands:</br>
- `python manage.py makemigrations`</br>
- `python manage.py migrate`</br></br>

Then Check Table is Created:</br>

<img width="1920" height="1080" alt="Screenshot 2025-12-06 073904" src="https://github.com/user-attachments/assets/e73adbd1-5dca-4566-8fec-724d7c560f12" /></br></br>

CREATE `serializers.py` : </br>

<img width="1920" height="1080" alt="Screenshot 2025-12-06 074534" src="https://github.com/user-attachments/assets/7ca6e82a-1c4e-4584-8d96-87c8f4e4fe31" /> </br></br>

OPNE `views.py` Import :</br></br>

---------- READ OPERATION ---------- </br></br>

- `from django.shortcuts import render`</br>
  👉 Used to return HTML templates or web pages (not used in your API logic).</br></br>
  
- from django.http import HttpResponse</br>
  👉 Used to send a response (text or JSON) back to the client (browser/Postman).</br></br>
  
- from .models import TaskModel</br>
  👉 Imports the TaskModel table so you can read, create, update, and delete data from the database.</br></br>

- from .serializers import TaskSerializer</br>
  👉 Imports the serializer to convert Model ↔ Python data.</br></br>

- from rest_framework.renderers import JSONRenderer</br>
  👉 Converts Python data into JSON format.</br></br>

- from django.views.decorators.csrf import csrf_exempt</br>
  👉 Disables CSRF security for API requests so that POST/PUT/DELETE work without a CSRF token.</br></br>


WRITE FOLLOWING CODE IN `views.py` File :</br>

<img width="1920" height="1080" alt="Screenshot 2025-12-06 081649" src="https://github.com/user-attachments/assets/1c4c6fb5-e45b-4e51-a02c-58d746ae4eb0" /></br></br>

CREATE URL FOR `tasks view` : </br>

<img width="1920" height="1080" alt="Screenshot 2025-12-06 081636" src="https://github.com/user-attachments/assets/31bb60db-0b15-4e2d-820b-a1f84a3399a2" /></br></br>







