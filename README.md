# To-Do Django App

A to-do list in Django. Create tasks, tick them off, edit them, delete them.

## Running it

```bash
cd simple
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

Then open http://127.0.0.1:8000/.

## The model

One model, which is the whole data layer:

```python
class Task(models.Model):
    title    = models.CharField(max_length=200)
    complete = models.BooleanField(default=False)
    created  = models.DateTimeField(auto_now_add=True)
```

## A note on versions

`requirements.txt` pins Django 3.1.6, which reached end of life in December
2021 and no longer receives security fixes. It is pinned deliberately — it is
what the app was written against and what it is known to run on. If you intend
to actually deploy this rather than read it, upgrade to a supported Django
first and expect to touch the URL and view imports.

## Licence

MIT.
