<h2> ----- VIEWS CREATION ----- </h2>

1) HttpResponse

- Go To App : For Ex.`ecom`
- Go To `views.py`
- Write Following Code.

`from django.http import HttpResponse`

`def home(request):` </br>
`    return HttpResponse("Hello! Welcome to my Homepage")`</br>

➡ When user opens: http://localhost:8000/Homepage
They will see: Hello! Welcome to my Homepage</br>

<img width="1920" height="1080" alt="Screenshot 2025-11-19 072556" src="https://github.com/user-attachments/assets/aedf9003-021e-46ca-a4ff-f3a7949d9a64" />


</br></br>
Why We Use HttpResponse?
- It sends plain text or HTML to the browser
- It is the most basic way to return data

* We Can Return HTML Also

`def about(request):`</br>
`    return HttpResponse("<h1>About Page</h1><p>This is my website.</p>")`</br>

Returning Variables

`def greet(request):`</br>
`    name = "Unik"`</br>
    `return HttpResponse(f"Hello {name}")` </br></br></br></br>

**------------------------------**</br></br>

2) 
