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

🚀 Django Interview Questions – Project Setup & Templates <br>
📌 Django Project Setup & Views <br><br>
1️⃣ What is the difference between a Django project and a Django app? <br>

Project → Entire web application (container) <br>
App → A module inside a project performing a specific task <br>
A project can contain multiple apps <br>
Apps are reusable, projects are not <br>
Example: Project = Company, Apps = HR, Sales, Accounts <br><br>

2️⃣ How do you create a new Django project and a new app? <br>

Create virtual environment <br>
Activate virtual environment <br>
Install Django → pip install django <br>
Create project → django-admin startproject projectname <br>
Move inside → cd projectname <br>
Create app → python manage.py startapp appname <br>
Add app inside INSTALLED_APPS <br>
Run server → python manage.py runserver <br><br>

3️⃣ What is the purpose of settings.py, urls.py, and views.py? <br>

| File | Purpose | <br>
|------|---------| <br>
| settings.py | Stores project configuration | <br>
| urls.py | Maps URLs to views | <br>
| views.py | Handles requests & returns responses | <br><br>

4️⃣ Explain the role of the INSTALLED_APPS setting. <br>

Lists all active apps <br>
Django loads models, migrations, templates, admin <br>
If app not added → Django ignores it <br>
Required for migrations and admin <br><br>

5️⃣ What is the difference between project-level urls.py and app-level urls.py? <br>

| Project-level | App-level | <br>
|---------------|-----------| <br>
| Main URL router | Handles URLs inside only one app | <br>
| Uses include() | Maps URLs to views | <br>
| Not reusable | Reusable | <br><br>

🎨 Rendering Templates <br><br>
6️⃣ What is the role of the render() function? <br>

Combines template + context data <br>
Returns HTML response <br>
Uses Django template engine internally <br><br>

7️⃣ What are the parameters of render()? <br>

render(request, template_name, context=None) <br><br>

| Parameter | Meaning | <br>
|-----------|---------| <br>
| request | HTTP request object | <br>
| template_name | HTML file | <br>
| context | Optional dictionary | <br><br>

8️⃣ Difference between render() and HttpResponse()? <br>

| render() | HttpResponse() | <br>
|----------|----------------| <br>
| Returns HTML template | Returns plain text | <br>
| Uses template | No template | <br>
| Supports context | No context | <br><br>

9️⃣ Can you pass context data to templates? How? <br>

YES <br>
views.py → return render(request,"home.html",{"name":"Unik"}) <br>
home.html → {{ name }} <br><br>

🧱 Template Inheritance <br><br>
🔟 What is the use of extends? <br>

Used for template inheritance <br>
Reuses base layout <br>
Avoids duplicate HTML code <br><br>

1️⃣1️⃣ Purpose of block tags <br>

Defines editable sections <br>
Child templates override them <br><br>

1️⃣2️⃣ What happens if a block is not overridden? <br>

Parent content is used <br><br>

1️⃣3️⃣ Can a template extend multiple templates? <br>

❌ No, only one parent allowed <br><br>

♻ Template Reusability <br><br>
1️⃣4️⃣ What is the use of include? <br>

Inserts another template inside current template <br>
Used for navbar, footer, etc. <br><br>

1️⃣5️⃣ Difference between extends and include? <br>

| extends | include | <br>
|---------|---------| <br>
| Inheritance | Insertion | <br>
| Defines full layout | Reuses components | <br>
| Used once | Can be used many times | <br><br>

1️⃣6️⃣ Can you include inside an extending template? <br>

✔ YES <br><br>

📁 Project-Level vs App-Level Templates <br><br>
1️⃣7️⃣ Difference <br>

| Project-level | App-level | <br>
|---------------|-----------| <br>
| Shared templates folder | Stored inside each app | <br>
| Common layouts | App-specific pages | <br><br>

1️⃣8️⃣ When to keep templates project-level? <br>

When shared across apps (example: base.html) <br><br>

1️⃣9️⃣ When to keep templates app-level? <br>

When used only by one app (example: blog templates) <br><br>

2️⃣0️⃣ If both have same name? <br>

Django loads first match <br><br>

🎁 Bonus Questions <br><br>
2️⃣1️⃣ What is TEMPLATES setting? <br>

Controls how Django loads and renders templates <br><br>

2️⃣2️⃣ What is APP_DIRS=True? <br>

Tells Django to auto-scan template folder of every app <br><br>

2️⃣3️⃣ How does Django find templates? <br>

Searches TEMPLATES['DIRS'] <br>

Searches app templates folder <br>

Uses first match <br><br>

2️⃣4️⃣ Can we use plain HTML without Django templating? <br>

✔ Yes, but no {% %} or {{ }} allowed <br><br>

2️⃣5️⃣ How to fix TemplateDoesNotExist? <br>

Check template name <br>
Check folder path <br>
Ensure APP_DIRS=True <br>
Check INSTALLED_APPS <br><br>
