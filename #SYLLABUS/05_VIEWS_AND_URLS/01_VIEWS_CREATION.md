<h2> ----- VIEWS CREATION ----- </h2>

- Go To App `ecom`
- Go To `views.py`

1) HttpResponse

`from django.http import HttpResponse`

`def home(request):` </br>
`    return HttpResponse("Hello! Welcome to my Homepage")`</br>

➡ When user opens: http://localhost:8000/Homepage
They will see: Hello! Welcome to my Homepage

Why We Use HttpResponse?
- It sends plain text or HTML to the browser
- It is the most basic way to return data

We Can Return HTML Also
def about(request):
    return HttpResponse("<h1>About Page</h1><p>This is my website.</p>")
Returning Variables
python
Copy code
def greet(request):
    name = "Unik"
    return HttpResponse(f"Hello {name}") </br>

- Add `from django.http import HttpResponse`
- Create Function ( Function is Also Called as Views )
- Chech Following Code and Create Function Like That ->

<img width="1920" height="1080" alt="01_VIEWS PY" src="https://github.com/user-attachments/assets/3fa33fe2-a51a-41c5-8adc-7041366c8ea9" />
