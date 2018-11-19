# Flask Blog Tutorial Implementation

Complete Replication of Flask Tutorial
---

Tutorial Resources:
- [Youtube](https://www.youtube.com/watch?v=MwZwr5Tvyxo&list=PL-osiE80TeTs4UjLw5MM6OjgkjFeUxCYH)
- [Github](https://github.com/CoreyMSchafer/code_snippets/tree/master/Python/Flask_Blog)

### Environment Setup and Installation

```bash
$ conda create --name flask-blog-tutorial --file requirements.conda.txt
$ conda/source activate flask-blog-tutorial
$ pip install -r requirements.pip.txt

$ conda install -c conda-forge flask-sqlalchemy
$ conda install -c conda-forge flask-bcrypt
$ conda install -c conda-forge flask-mail
```

### Database Setup

- [Flask-SQLAlchemy needs and app context to operate](https://stackoverflow.com/questions/24060553/creating-a-database-outside-the-application-context)
- Make sure that the `DB URI` and `secret` are being set up correctly first in
`ashishflaskblog/config.py`.

```
>>> from ashishflaskblog import db
>>> from ashishflaskblog import create_app
>>> app = create_app()
>>> ctx = app.app_context()
>>> ctx.push()
>>> db.create_all()  # creates db instance
>>> ctx.pop()
```

##### Create a secret
```
$ python
>>> import secrets
>>> secrets.token_hex()
```

### Run Flask Application

```bash
export FLASK_APP=run.py
export FLASK_ENV=development
flask run
```

### Mail Setup

- Make sure to setup EMAIL_USER and EMAIL_PASS environment variables for
 `ashishflaskblog/config.py`.

Mail Issues:

Q. SMTP Authentication Error.

A. If you're using googlemail, [here](https://stackoverflow.com/questions/26852128/smtpauthenticationerror-when-sending-mail-using-gmail-and-python) is a solution.

### Install SCSS (full instructions [here](https://sass-lang.com/install))

- `npm install -g sass`

Run the scss command:

- `sass --watch scss/main.scss:ashishflaskblog/static/main.css`

### Important Topics
- Application Factory
    - Flask Blueprint
