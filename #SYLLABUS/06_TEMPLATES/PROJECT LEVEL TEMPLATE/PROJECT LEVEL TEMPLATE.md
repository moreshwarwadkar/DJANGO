<h2> -----PROJECT LEVEL TEMPLATE----- </h2>
- Here we create a `templates` Folder in a root directory.

- Then Go To setting.py and add Following : </br></br>
	`'DIRS': [
       	    BASE_DIR/'templates'
            ],`</br></br>
`( Here Give the same name as a Folder Name, like ‘ templates ’ )`</br></br>

<img width="1920" height="1080" alt="02_PROJECT_LEVEL_TEMPLATE" src="https://github.com/user-attachments/assets/18d3eb02-ed69-41b6-a2ed-a318babc4d57" />
</br></br>
  
- Then create `main.html` and `nav.html` in that file. `[ IN ROOT DIRECTORY : templates ]`</br></br>
<img width="1920" height="1080" alt="01_PROJECT_LEVEL_TEMPLATE" src="https://github.com/user-attachments/assets/46346a5b-ccb3-4cfe-9797-435b411fa7de" /> </br></br>


- Go To `main.html` and write
   1) `{% load static %}` at the top of the page : 
   	</br>--> `{% load static %}` is used to enable the use of Django’s `{% static %}` tag so you can include CSS, JS, and image files in your template.</br></br>

  2) `<link rel="stylesheet" href="{% static 'style.css' %}">` :</br>
   	--> Here We link `stylec.css` CSS File.</br></br>
  3) `{% include "nav.html" %}` :</br>
   	--> Here `nav.html` is the Navigation Menu File Name.</br></br>
   5) `{% block content %}
    {% endblock content %}` : </br>
	--> {% block content %}{% endblock content %} is used to create a section in a Django template where child templates can insert their own content when extending a base template.
  </br></br>
  
<img width="1920" height="1080" alt="Screenshot 2025-11-15 130431" src="https://github.com/user-attachments/assets/f03a8a8e-032b-4082-b2e3-9be141dbf056" />
  
</br></br>

- Go TO `nav.html`
- Write all nevigation code in that file.</br></br>

<img width="1920" height="1080" alt="Screenshot 2025-11-15 132038" src="https://github.com/user-attachments/assets/81cd2893-3b16-477d-8ed7-872ef7f76dd4" />


</br></br>

DOne..!




