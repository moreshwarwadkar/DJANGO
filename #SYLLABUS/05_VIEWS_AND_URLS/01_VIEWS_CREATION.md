<h2> ----- VIEWS CREATION ----- </h2>

1) HttpResponse:

- Go To App : For Ex.`ecom`
- Go To `views.py`
- Write Following Code.

`from django.http import HttpResponse`

`def home(request):` </br>
`    return HttpResponse("Hello! Welcome to my Homepage")`</br>

- Set-Up the url in `urls.py` File.
  
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

2) render():

- Go To App : For Ex.`ecom`
- Go To `views.py`
- Write Following Code.

`from django.shortcuts import render` </br>

`def home(request):`</br>    
`        return render(request,'home.html')` </br></br>

<img width="1920" height="1080" alt="Screenshot 2025-11-19 073748" src="https://github.com/user-attachments/assets/c4887c4b-b9fb-49ef-a1d1-394e0c8e57e5" />

</br></br>
- Here it will display the data which are included in a `home.html`.




1️⃣ from django.shortcuts import render

- You import the render() function from Django’s shortcuts module.
- render() helps you load an HTML template and send it as a response.

2️⃣ def home(request):

- You create a function named home.
- This function will run when someone opens the URL connected to it.
- request contains all details of the user’s browser request.

3️⃣ return render(request, 'home.html')

- You tell Django to load the template file home.html.
- Django combines the HTML with the request.
- Then Django sends the final webpage back to the browser as a response.
