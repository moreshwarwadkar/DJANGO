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

-----------------------------</br></br>

`4) Explain the role of the INSTALLED_APPS setting.`

Here are the **points** explaining the role of `INSTALLED_APPS` 👇

* It is a list inside `settings.py`.
* It tells Django which apps are active in the project.
* It includes both **built-in Django apps** and **custom apps** you create.
* If an app is not listed here, Django will **not recognize it**.
* Only apps inside this list can run **migrations**.
* Django loads models, signals, templates, and admin features only for apps listed here.
* Without adding your app to `INSTALLED_APPS`, it **will not work properly** in the project.

-----------------------------</br></br>

`5) What is the difference between project-level urls.py and app-level urls.py?`

| Feature     | Project-level urls.py | App-level urls.py               |
| ----------- | --------------------- | ------------------------------- |
| Location    | Project folder        | Inside app folder               |
| Purpose     | Main routing file     | Handles that app's URLs         |
| Contains    | Includes app URLs     | Maps views within the app       |
| Scope       | Whole project         | Single app                      |
| Reusability | Not reusable          | Can be reused in other projects |

🏗 Project-level urls.py

- Located in the main project folder.
- Acts as the central URL router for the whole project.
- Includes the app-level URLs using path() or include().

Example:

path('blog/', include('blog.urls'))
Controls the main entry points of the website.

⚙️ App-level urls.py

- Located inside each app folder (you create it manually).
- Contains URLs related only to that specific app.
- Maps URLs to views inside the same app.

Example:

path('', views.home)
Makes each app modular and reusable.

<h3>Rendering Templates</h3>

`1) What is the role of the render() function in Django?`

🎯 Role of render() function in Django

- It is used to combine a template (HTML file) with data and return an HTTP response.
- It takes the request, the template name, and an optional context dictionary.
- It sends the result back to the browser as a complete HTML page.
- It simplifies the process of loading templates and returning responses.
- It automatically uses Django’s template engine.

🧩 Example
`return render(request, 'home.html', {'name': 'Unik'})`

✔ Loads home.html </br>
✔ Passes data (name: Unik) </br>
✔ Returns the final webpage to the user </br></br>


`2) What are the parameters of render()?`

The render() function in Django mainly takes three parameters:

1️⃣ request

- The HTTP request object
- It is always the first parameter

2️⃣ template_name

- The HTML file to be rendered
- Example: "index.html", "home/about.html"

3️⃣ context (optional)

- A dictionary of data you want to send to the template
- Example: {'name': 'Unik', 'age': 25}
- If no data is needed, you can skip it

📌 Full format:
`render(request, template_name, context=None)`


✔ request → Required </br>
✔ template_name → Required </br>
✔ context → Optional </br></br>
