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


**--------------------------------------------------------------------------------------**

<h2>---------- 1) ADD TASK ----------</h2>

- Create `addtask.html` and create a Form</br>

<img width="1920" height="1080" alt="Screenshot 2025-11-26 135609" src="https://github.com/user-attachments/assets/42beb74b-0c4b-4420-9403-fd73512d5f4e" /> </br></br>

Create views for addtask.html :</h3> </br>

- Firt in `views.py` Add: `from django.shortcuts import render,redirect`  ( Here we Add `redireect` only )
- Then: `from base.models import taskmodel`
- Create Views For addtask
- Add in Home Views: `all_task=taskmodel.objects.all()`
- Add in Home Views : `return render(request,'home.html',{'all_task':all_task})`   : Here Pass the Context</br>

- Write Following Code for addtask Views:
<img width="1920" height="1080" alt="Screenshot 2025-11-26 135737" src="https://github.com/user-attachments/assets/16ff2953-1349-480a-b91d-5ad7d02ab156" /> </br></br>

- Then Create url for addtask views.
- `path('addtask',views.addtask,name='addtask')`
  
- To Print the data on a HomePage Write Following Code:

<img width="1920" height="1080" alt="Screenshot 2025-11-26 140030" src="https://github.com/user-attachments/assets/bd4c676c-1d26-460a-9d97-fc905b85bbb9" /> </br></br>


**Here We Complete Add Task and Display on Screen**
--------------------------------------------------------------------------------------

<h2>---------- 2) UPDATE ----------</h2>

- First Create `update.html` and Create Form.

<img width="1920" height="1080" alt="Screenshot 2025-11-26 140655" src="https://github.com/user-attachments/assets/11949569-ded9-437b-8f32-49a4378ab2bc" /> </br></br>

- Create a `View` for update.html: </br>

<img width="1920" height="1080" alt="Screenshot 2025-11-26 145730" src="https://github.com/user-attachments/assets/5bf15fd0-b32d-438e-b6a5-1e06b0948244" /> </br></br>

- Create URL For view `path('update/<int:pk>/',views.update,name='update'),` </br>

- Add the reference and Pass iD :

<img width="1920" height="1080" alt="Screenshot 2025-11-26 145921" src="https://github.com/user-attachments/assets/4d1b7be7-293e-4e76-aa95-e1041523d274" /> </br></br>

- Then Add Values:
- For Title - `value="{{task.title}}"`
- For Description - `value="{{task.desc}}"`

<img width="1920" height="1080" alt="Screenshot 2025-11-26 150040" src="https://github.com/user-attachments/assets/97bff624-58fd-42dc-ab80-8701787047a3" /> </br></br>


**Here We Complete Update and Display Updated Data on Screen**
--------------------------------------------------------------------------------------

<h2>---------- 3) TRASH ----------</h2>

- First Go To views.py file and Create a View for Delete Operation. </br>

<img width="1920" height="1080" alt="Screenshot 2025-11-26 150939" src="https://github.com/user-attachments/assets/936528a0-cfac-44f1-b6c3-75ca101ec83e" /> </br></br>

- Create URL For That View : `path('delete/<int:pk>',views.delete,name='delete'),` </br>

- Add Referenec and Pass iD :

<img width="1920" height="1080" alt="Screenshot 2025-11-26 151132" src="https://github.com/user-attachments/assets/1147150c-382d-4bec-be64-eccabdfc6cca" /> </br></br>


**Here We Complete Delete Operation*
--------------------------------------------------------------------------------------

<h2>---------- 3) TRASH ----------</h2>
















