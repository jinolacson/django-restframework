# Re activating our existing virtual environment

So we are almost done with the tutorial, we will try to remove active environment and re-activate it once again.

1. Remove existing environment.

```
dev-mentor@devmentor-PC-MK34LEZCBEAD:~/Downloads/tutorial$ pipenv --rm
Removing virtualenv (/home/dev-mentor/.local/share/virtualenvs/tutorial-kIS-RzCH)…
```

2. Then `pipenv install` to re-install and or `pipenv install --dev` (to install dev dependencies)
, since we dont have `[dev-packages]` in our `Pipfile`, we just use `pipenv install` .

```
dev-mentor@devmentor-PC-MK34LEZCBEAD:~/Downloads/tutorial$ pipenv install
Creating a virtualenv for this project…
Pipfile: /home/dev-mentor/Downloads/tutorial/Pipfile
Using /usr/bin/python3.6 (3.6.8) to create virtualenv…
⠏ Creating virtual environment...Already using interpreter /usr/bin/python3.6
Using base prefix '/usr'
New python executable in /home/dev-mentor/.local/share/virtualenvs/tutorial-kIS-RzCH/bin/python3.6
Also creating executable in /home/dev-mentor/.local/share/virtualenvs/tutorial-kIS-RzCH/bin/python
Installing setuptools, pip, wheel...
done.
Running virtualenv with interpreter /usr/bin/python3.6

✔ Successfully created virtual environment! 
Virtualenv location: /home/dev-mentor/.local/share/virtualenvs/tutorial-kIS-RzCH
Installing dependencies from Pipfile.lock (622a82)…
  🐍   ▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉ 21/21 — 00:00:08
To activate this project's virtualenv, run pipenv shell.
Alternatively, run a command inside the virtualenv with pipenv run.

```

3. Re-activate virtual environment.

```
dev-mentor@devmentor-PC-MK34LEZCBEAD:~/Downloads/tutorial$ pipenv shell
Launching subshell in virtual environment…
 . /home/dev-mentor/.local/share/virtualenvs/tutorial-kIS-RzCH/bin/activate
dev-mentor@devmentor-PC-MK34LEZCBEAD:~/Downloads/tutorial$  . /home/dev-mentor/.local/share/virtualenvs/tutorial-kIS-RzCH/bin/activate
(tutorial) dev-mentor@devmentor-PC-MK34LEZCBEAD:~/Downloads/tutorial$ 
```

4. Serve Django with specific port `python manage.py runserver 5000`

```
(tutorial) dev-mentor@devmentor-PC-MK34LEZCBEAD:~/Downloads/tutorial$ python manage.py runserver 5000
Watching for file changes with StatReloader
Performing system checks...

System check identified no issues (0 silenced).
October 09, 2019 - 06:47:21
Django version 2.2.6, using settings 'api.settings'
Starting development server at http://127.0.0.1:5000/
Quit the server with CONTROL-C.
```

5. Done.

### Resource

[Pipenv: Python Development Workflow for Humans](https://github.com/pypa/pipenv).

# Next

[Documenting api with Rest Swagger](https://github.com/boomcamp/django-restframework/tree/step6-rest-swagger)

