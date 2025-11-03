-----|| Steps To Create App ||-----

1) Open Project
2) Go TO Terminal and Switch To Command Prompt
3) Type: python manage.py startapp DJANGO_APP_NAME
   EX--> python manage.py startapp laptop

   [ After Completing All Steps App Will be Created With The Name of 'laptop' ]
   [ CATEGORIES IS ALSO CALLED AS  DJANGO APPS ]




-----|| Steps TO Create a View ||-----

1) -> from django.http import HttpResponse  [ IMPORT THAT IN A views.py FILE ]
2) -> Create a Function : 

  def home(request):
    return HttpResponse('This is Home Page')

[ FUNCTIONS IS ALSO CALLED AS VIEWS ]

3) -> Go To urls.py
4) from amazon import views

---------- For EX. ----------
[ IN urls.py ]
from mobile import views  [ mobile is a App Name ]

urlpatterns = [
    path('admin/', admin.site.urls),
    path('home',views.home),
    path('about',views.about),
    path('contact',views.contact),
    path('feedback',views.feedback),
    path('disclaimer',views.disclaimer),
]
