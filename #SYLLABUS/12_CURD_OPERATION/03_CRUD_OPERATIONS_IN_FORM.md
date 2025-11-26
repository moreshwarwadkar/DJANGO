<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/08a50f06-7816-46e4-8690-dca5e1818802" /><img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d39c73d5-a47d-4506-8860-90d5807ee999" /><img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a9a57b54-ceb1-44ac-9ee4-da67b7a8c01f" /><h2>CRUD Operations in From</h2>

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

<h2>---------- 3) Delete Operation ----------</h2>

- First Go To views.py file and Create a View for Delete Operation. </br>

<img width="1920" height="1080" alt="Screenshot 2025-11-26 150939" src="https://github.com/user-attachments/assets/936528a0-cfac-44f1-b6c3-75ca101ec83e" /> </br></br>

- Create URL For That View : `path('delete/<int:pk>',views.delete,name='delete'),` </br>

- Add Referenec and Pass iD :

<img width="1920" height="1080" alt="Screenshot 2025-11-26 151132" src="https://github.com/user-attachments/assets/1147150c-382d-4bec-be64-eccabdfc6cca" /> </br></br>


**Here We Complete Delete Operation*
--------------------------------------------------------------------------------------

<h2>---------- 4) TRASH ----------</h2>

- Create New Field: `is_delete=models.BooleanField(default=False)` </br>

<img width="1920" height="1080" alt="Screenshot 2025-11-26 153833" src="https://github.com/user-attachments/assets/0f0af4ac-ef74-4ad1-9ecb-08ddf8576b8f" /> </br></br>


- First Create `trash.html`

<img width="1920" height="1080" alt="Screenshot 2025-11-26 153124" src="https://github.com/user-attachments/assets/89c3411c-4555-4b45-9460-b24bbdeadf07" /> </br>

<img width="1920" height="1080" alt="Screenshot 2025-11-26 153133" src="https://github.com/user-attachments/assets/f14d27ec-2454-4acc-bb53-08265484498e" /> </br></br>

- Create View For Trash

<img width="1920" height="1080" alt="Screenshot 2025-11-26 153259" src="https://github.com/user-attachments/assets/ca23a0f1-8cb4-42e6-b82b-81096ab6c39b" /> </br></br>

- Update Following Code:

  1) In Delete View

  - ` task.is_delete=True` </br>
  -  ` task.save()`

<img width="1920" height="1080" alt="Screenshot 2025-11-26 153428" src="https://github.com/user-attachments/assets/12cbc327-9712-456d-9281-b7b0c91b8dd4" /> </br></br>


2) IN Home View

- `all_task = taskmodel.objects.filter(is_delete=False)`</br>

<img width="1920" height="1080" alt="Screenshot 2025-11-26 153552" src="https://github.com/user-attachments/assets/f8dc3631-aa61-4984-a307-8ed5adf665d2" /> </br></br>


- Create URL For Trash: `path('trash',views.trash,name='trash')` </br></br>

- Add Reference : `<a href="{% url 'trash' %}">Trash</a>` </br></br>


**Here We Complete Trash -*
--------------------------------------------------------------------------------------

<h2>---------- 4) TRASH : 1) Permanently Delete ----------</h2>

- Create view for Permanently Delete :

<img width="1920" height="1080" alt="Screenshot 2025-11-26 161913" src="https://github.com/user-attachments/assets/0a63a692-69d1-4cf8-b6ef-141dc6b55e4c" /> </br></br>

- Create URL for `p_delete` view : `path('p_delete/<int:pk>',views.p_delete,name='p_delete'),` </br>

- Add Reference : `<a href="{% url 'p_delete' i.id %}" class="btn btn-delete">Delete Task</a>` </br>

<img width="1920" height="1080" alt="Screenshot 2025-11-26 162958" src="https://github.com/user-attachments/assets/770557ce-6a9f-494c-b5a7-434ff75795c2" /> </br></br>


<h2>---------- 4) TRASH : 2) Restore ----------</h2>

- Create view for Restore :

<img width="1920" height="1080" alt="Screenshot 2025-11-26 162554" src="https://github.com/user-attachments/assets/d0954946-c226-449f-97f8-0cc332801a61" /> </br></br>

- Create URL For `restore` view : `path('restore/<int:pk>',views.restore,name='restore'),`</br>

- Add Reference : `<a href="{% url 'restore' i.id%}" class="btn btn-detail">Restore</a>`</br>

<img width="1920" height="1080" alt="Screenshot 2025-11-26 162820" src="https://github.com/user-attachments/assets/d0fbe318-35ae-4634-b3a5-dcf32f874d8c" /> </br></br>


<h2>---------- 4) TRASH : 3) Delete All ----------</h2>

Create View for Delete All :

<img width="1920" height="1080" alt="Screenshot 2025-11-26 163232" src="https://github.com/user-attachments/assets/3133e39f-29e7-4d58-aa7d-e6bff9399913" /> </br></br>

- Create URL For `delete_all` view : `path('delete_all',views.delete_all,name='delete_all'),`</br>

- Add Reference : `<a href="{% url 'delete_all' %}" class="btn btn-delete">Delete All </a></h2>`</br>

<img width="1920" height="1080" alt="Screenshot 2025-11-26 163402" src="https://github.com/user-attachments/assets/59b51f7a-77f5-4a4e-a100-2f235b7b5d52" /> </br></br>

<h2>---------- 4) TRASH : 3) Restore All ----------</h2>



























