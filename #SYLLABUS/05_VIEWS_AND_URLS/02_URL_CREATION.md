<h2>----- ULR CREATION -----</h2>

- Create `urls.py` in App Folder.
- In Our case we have `ecom` App.
- In that file we have to write following code.
</br>

`from django.urls import path`</br>
`from . import views`</br></br>
`urlpatterns = [`</br>
    `path('Homepage',views.home),`</br>
`]`</br>

  
</br>
<img width="1920" height="1080" alt="Screenshot 2025-11-18 224255" src="https://github.com/user-attachments/assets/93f8d80e-faf5-4093-a750-d98fdb81a17e" />
</br></br>

1️⃣ from django.urls import path

- path is a Django function used to define URL patterns.
- It allows you to connect a URL to a view function.

- Example: path('login/', views.login) means when the user goes to /login, Django will run login() function.

2️⃣ from . import views

- This imports the views.py file inside the same app folder.
- The dot . means current package (same app).
- We need this so we can call the functions written in views.py.

3️⃣ urlpatterns = [

- urlpatterns is a required Django variable.
- It stores a list of all URLs that belong to this app.

4️⃣ path('Homepage', views.home),

- This creates a URL route.
- 'Homepage' → URL endpoint.
- 👉 When user visits: http://localhost:8000/Homepage
- views.home → This calls the home() function inside views.py.
- So when the user goes to /Homepage, the home() function will execute and send a response.
