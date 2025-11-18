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

**-----------------------------</br></br>**

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

**-----------------------------</br></br>**

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

**-----------------------------</br></br>**

`4) Explain the role of the INSTALLED_APPS setting.`

Here are the **points** explaining the role of `INSTALLED_APPS` 👇

* It is a list inside `settings.py`.
* It tells Django which apps are active in the project.
* It includes both **built-in Django apps** and **custom apps** you create.
* If an app is not listed here, Django will **not recognize it**.
* Only apps inside this list can run **migrations**.
* Django loads models, signals, templates, and admin features only for apps listed here.
* Without adding your app to `INSTALLED_APPS`, it **will not work properly** in the project.

**-----------------------------</br></br>**

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

**-----------------------------**
**-----------------------------</br></br>**

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

**-----------------------------</br></br>**

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

**-----------------------------</br></br>**

`3) Can you pass context data to templates? How?`

Yes, you can pass context data to templates in Django using the context dictionary inside the render() function.

✅ How to Pass Context Data

- Step 1: In views.py

from django.shortcuts import render

def home(request):
    data = { </br>
        'name': 'Unik',</br>
        'age': 25 </br>
    }</br>
    return render(request, 'home.html', data)</br></br>


✔ Here, data is the context dictionary
✔ It is passed to the template

- Step 2: In home.html

`<h1>Hello {{ name }}</h1>`
`<p>Your age is {{ age }}</p>`


✔ `{{ name }} and {{ age }}` will display values from the context

📌 Summary

- Yes, you can pass context to templates
- Use: render(request, template, context_dict)
- Access values in template using {{ variable_name }}

**-----------------------------</br></br>**

`4) Difference between render() and HttpResponse()?`

🖼 render()

- Used to return an HTML template with data.
- It loads a template, fills it with context, then returns a response.
- Easier and commonly used for web pages.

Example:

`return render(request, 'home.html', {'name': 'Unik'})`

📄 HttpResponse()

- Returns raw text (string), HTML, JSON, or any plain response.
- Does NOT load templates automatically.
- Used for simple or custom responses.

Example:

`return HttpResponse("Hello World")`

**-----------------------------**
**-----------------------------</br></br>**











-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------


🚀 Django Interview Questions – Project Setup & Templates
📌 Django Project Setup & Views
1️⃣ What is the difference between a Django project and a Django app?

Project → Entire web application (container)

App → A module inside a project performing a specific task

A project can contain multiple apps

Apps are reusable, projects are not

Example: Project = Company, Apps = HR, Sales, Accounts

2️⃣ How do you create a new Django project and a new app?

Create virtual environment

Activate virtual environment

Install Django → pip install django

Create project → django-admin startproject projectname

Move inside → cd projectname

Create app → python manage.py startapp appname

Add app inside INSTALLED_APPS

Run server → python manage.py runserver

3️⃣ What is the purpose of settings.py, urls.py, and views.py?
File	Purpose
settings.py	Stores project configuration (database, installed apps, static files, etc.)
urls.py	Maps URLs to views (routing system)
views.py	Contains functions/classes that process requests and return responses
4️⃣ Explain the role of the INSTALLED_APPS setting.

Lists all active apps in the project

Django loads their models, migrations, signals, admin, templates

If an app is not added → Django ignores it

Required for migrations and admin

5️⃣ What is the difference between project-level urls.py and app-level urls.py?
Project-level	App-level
Main router for whole project	Handles only one app
Uses include() to connect apps	Maps URLs to views
Not reusable	Reusable in other projects
🎨 Rendering Templates
6️⃣ What is the role of the render() function in Django?

Combines template + context data and returns HTML

Uses Django’s template engine automatically

Simplifies HTML response handling

7️⃣ What are the parameters of render()?
render(request, template_name, context=None)

Parameter	Meaning
request	HTTP request object
template_name	HTML file
context	Dictionary of data (optional)
8️⃣ Difference between render() and HttpResponse()?
render()	HttpResponse()
Returns HTML template	Returns plain text/string
Supports context data	No template rendering
Most common for pages	Useful for manual responses
9️⃣ Can you pass context data to templates? How?

YES

Example:

views.py

return render(request, 'home.html', {'name': 'Unik'})


home.html

<h1>Hello {{ name }}</h1>

🧱 Template Inheritance
🔟 What is the use of extends in Django templates?

Used for template inheritance

Allows child template to reuse base layout

Avoids duplicate HTML code

1️⃣1️⃣ What is the purpose of {% block %} tags?

Marks editable sections inside templates

Child templates replace content inside these blocks

1️⃣2️⃣ What happens if a child template does not define a {% block %} that exists in the parent?

Django uses the default content written inside the block in the parent template

1️⃣3️⃣ Can one template extend multiple templates?

❌ NO
A template can only extend ONE parent template

♻ Template Reusability
1️⃣4️⃣ What is the use of {% include %} in Django templates?

Inserts another template inside current template

Used for repeating small components (header, footer, menu)

1️⃣5️⃣ Difference between extends and include?
extends	include
Parent-child inheritance	Simple insertion
Defines structure	Repeats reusable code
Used once per template	Can be used many times
1️⃣6️⃣ Can you include a template inside another template that already extends a base template?

✔ YES
Example: A template can extend base.html and include header.html.

📁 Project-Level vs App-Level Templates
1️⃣7️⃣ What is the difference between project-level templates and app-level templates?
Project-level	App-level
Stored in project templates folder	Stored inside each app
Used across multiple apps	Used only in that app
Better for shared layout	Better for app-specific pages
1️⃣8️⃣ When should you keep templates at project-level?

When templates are shared across multiple apps

Example: base.html, navbar.html

1️⃣9️⃣ When should you keep templates at app-level?

When templates belong only to one app

Example: Blog → post_list.html, post_detail.html

2️⃣0️⃣ What happens if both project-level and app-level templates have the same name?

➡ Django uses the first match based on the template search order
(App-level templates usually get priority if APP_DIRS=True)

🎁 Bonus Conceptual Questions
2️⃣1️⃣ What is TEMPLATES setting in settings.py?

Controls how Django loads and renders templates

Contains: backend, directories, context processors, APP_DIRS

2️⃣2️⃣ What is APP_DIRS: True in TEMPLATES?

Tells Django to look inside each app’s templates folder

Enables automatic template discovery

2️⃣3️⃣ How does Django find which template to render?

Checks paths listed in TEMPLATES['DIRS']
Then checks each app’s templates folder (if APP_DIRS=True)
Uses the first matching filename

2️⃣4️⃣ Can we use plain HTML files in Django without templates?

✔ YES, but
❌ You cannot use template tags ({{ }}, {% %})
✔ You can return HTML using HttpResponse()

2️⃣5️⃣ How would you debug a TemplateDoesNotExist error?

Check template name spelling
Check template folder location
Ensure APP_DIRS=True
Check TEMPLATES → DIRS path is correct
Confirm app is added to INSTALLED_APPS
