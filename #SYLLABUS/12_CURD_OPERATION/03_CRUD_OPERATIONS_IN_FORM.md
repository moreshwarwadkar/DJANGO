<h2>CRUD Operations in From</h2>

- First Create App (base)
- Create Template : home.html
- Craete Views
- Create urls.py File </br></br>

**This is Our HomePage**

<img width="1920" height="1080" alt="Screenshot 2025-11-26 131429" src="https://github.com/user-attachments/assets/a3c1f656-332f-4fce-ba06-64e7ddbdbe8c" /> </br></br>


</br></br>
<h3>1) Create Model : ( We Create 'taskmodel' )</h3> </br></br>

<img width="1920" height="1080" alt="Screenshot 2025-11-26 130158" src="https://github.com/user-attachments/assets/ee9f4eb6-c8d7-4e02-aa7a-3df4e0aa4c87" /> </br></br>

<h3>2) Migration :</h3> </br>

`1: python manage.py makemigrations`</br>
`2: python manage.py migrate` </br></br>

**Table is Created ( Here it Display `base_taskmodel` )** </br></br>

<img width="1920" height="1080" alt="Screenshot 2025-11-26 131048" src="https://github.com/user-attachments/assets/752a1a67-80f8-43c8-8be5-3cd6109c0369" /> </br></br>

<h3>3) Create addtask.html :</h3> </br>

<img width="1920" height="1080" alt="Screenshot 2025-11-26 132413" src="https://github.com/user-attachments/assets/fb4f55b2-d89a-43ef-852c-d400db00bca1" /> </br></br>

<h3>4) Create views for addtask.html :</h3> </br>

- Firt in `views.py` Add: `from django.shortcuts import render,redirect`  ( Here we Add `redireect` only )
- Then: `from base.models import taskmodel`
- Create Views For addtask
- Add in Home Views: `all_task=taskmodel.objects.all()`
- Add in Home Views : `return render(request,'home.html',{'all_task':all_task})`   : Here Pass the Context</br>

<img width="1920" height="1080" alt="Screenshot 2025-11-26 133319" src="https://github.com/user-attachments/assets/ed1300d3-9136-4019-afe5-4c92cb6797b7" /> </br></br>






