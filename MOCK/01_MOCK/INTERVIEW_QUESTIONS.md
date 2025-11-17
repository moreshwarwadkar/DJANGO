<h2>Django Interview Questions (Project Setup & Templates)</h2>

<h3>Django Project Setup & Views</h3>

`1) What is the difference between a Django project and a Django app?`

| Feature     | Django Project                                    | Django App                                     |
| ----------- | ------------------------------------------------- | ---------------------------------------------- |
| Definition  | The main container for your whole web application | A module that performs a specific task         |
| Purpose     | Manage the configuration of the entire site       | Handle one specific part or feature            |
| Contains    | Settings, URLs, templates, static files, apps     | Models, Views, Templates, URLs for one feature |
| Reusability | Usually not reusable                              | Can be reused in multiple projects             |
| Example     | `mysite`                                          | `blog`, `users`, `payments`                    |

</br>

🏗️ Django Project

A Django project is the entire web application.</br>
It’s like a container that holds everything — settings, configurations, and one or more apps.</br>
It defines: The database settings, Installed apps, URLs configuration, Static files, templates, etc.</br></br>

💡 Example:</br>
Think of a Django project like a company — it has rules, policies, and departments.</br></br>

⚙️ Django App

A Django app is a module or a component inside a project.</br>
Each app is responsible for one specific functionality.</br>
You can have multiple apps inside one project (e.g., login, blog, payment, etc.).</br>
Apps are reusable — you can use the same app in another project.</br></br>

💡 Example:</br>
Inside a company (project), you can have departments (apps) like:</br></br>

HR Department → users app</br>
Sales Department → orders app</br>
Finance Department → payments app</br></br>

-----------------------------</br></br>

`2) How do you create a new Django project and a new app?`

Here is the answer **in a list**:

*  Set-Up Virtual Environmemt: `python -m venv myenv`
*  Activate Virtual Environment: `myenv\Scripts\activate`
*  Install Django: `pip install django`
* Create a new project: `django-admin startproject projectname`
* Go inside the project folder: `cd projectname`
* Create a new app: `python manage.py startapp appname`
* Add the app name inside `INSTALLED_APPS` in `settings.py`
* Run the server: `python manage.py runserver`
* Open the project in browser: `http://127.0.0.1:8000/`

-----------------------------</br></br>

`3) What is the purpose of settings.py, urls.py, and views.py?`

🛠 settings.py

- Stores project configuration.
- Contains database settings, installed apps, middleware, static file settings, etc.
- Acts like the control panel of the project.

🌐 urls.py

- Handles the URL routing of the project or app.
- Maps a URL path to a view function.
- Acts like a traffic controller telling Django which view should run for a given URL.

👁️ views.py

- Contains functions or class-based views that process user requests.
- Returns responses (HTML, JSON, text, etc.).
- Acts as the brain of your app — takes input, processes it, and returns output.
