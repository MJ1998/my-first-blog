source myvenv/bin/activate
deactivate

django-admin startproject mysite .              creates web app named mysite

python manage.py migrate                        django sets up
python manage.py runserver                      to start web browser
[Starting development server at http://127.0.0.1:8000/]]


python manage.py startapp blog                  to create our application blog for our django model
[after making model]
python manage.py makemigrations blog            tells django that there are some changes in our model
[django gets signified and it prepares a migration file]
python manage.py migrate blog                   migrates the migration file prepared by django

http://127.0.0.1:8000/admin/                    takes you to the admin page in our web app

[python manage.py createsuperuser]


git status
git add --all .
git commit -m "My Django Girls app, first commit"

[  $ git remote add origin https://github.com/<your-github-username>/my-first-blog.git  ]==>probably one time command

git push [-u origin master]


web app deployment(pythonanywhere
[involves configuration of web app in my github, then creation of superuser) ==>> webapp folder in dashboard contains my web app


python manage.py shell



sql type queries

Post.objects.all()
from django.contrib.auth.models import User
User.objects.all()
me=User.objects.get(username='mj1')
Post.objects.create(author = me,title = "?asfv", text = "asdf")

from django.utils import timezone
post = Post.objects.get(title="Title4")
Post.objects.filter(published_date__lte=timezone.now()
Post.objects.order_by('created_date')
Post.objects.order_by('-created_date')
Post.objects.filter(published_date__lte=timezone.now()).order_by('published_date')