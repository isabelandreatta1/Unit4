
### [HL] Homework

Create a form for registration of user including as much information as you can think of. Some ideas include: phone number, birthday, email, address, gender, favorite programming language, etc. 

**1. First page when I connect** 

![](https://github.com/isabelandreatta1/Unit4/blob/main/images/Form1.png)

**2. Link to register page when I click the button**

![](https://github.com/isabelandreatta1/Unit4/blob/main/images/Form2.png)

**3. Forms when flled out**

![](https://github.com/isabelandreatta1/Unit4/blob/main/images/Form3.png)

**4. Error occurs once I press submit** 

![](https://github.com/isabelandreatta1/Unit4/blob/main/images/Form4.png)

**app.py Code** 

```py 
from flask import Flask, render_template, redirect

# create variable for application, flask is a class
# the application which will contain our home page is called __name__
# this variable contains name of file that will run
from flask_wtf import FlaskForm
from wtforms import StringField, PasswordField, SubmitField, RadioField, SelectField, IntegerField
from wtforms.validators import DataRequired, Email, NumberRange, Length

app = Flask(__name__)
#this is the seed for the forms secret code
app.config['SECRET_KEY'] = 'my_secret'


class Submitfield(object):
    pass

class loginForm(FlaskForm):
    username = StringField('Username',validators=[DataRequired()])
    password = PasswordField('Password', validators=[DataRequired()])
    submit = SubmitField('Login')

class registerForm(FlaskForm):
    username = StringField('Username', validators=[DataRequired()])
    email = StringField('Email', validators=[DataRequired(), Email()])
    sex = RadioField('Gender', choices=[('value','Male'), ('value_two','Female'), ('value_three','Other')])
    birthmonth = SelectField("Birthday Month", choices=['January','February','March','April','May','June','July',
                                                        'August','September','October','November', 'December'])
    birthYear = IntegerField('Year of birth', validators=[NumberRange(min=1910,max=2021)])
    password = PasswordField("Password", validators=[DataRequired(), Length(min= 6, max=40)])
    submitRegister = SubmitField('Register')

# this defines the route, when you enter server with a slash, you land here
@app.route('/profile')
def hello_world():
    return 'Hello! I am Isabel, also known as the The Creator of this page'

@app.route('/register', methods=['GET', 'POST'])
def register():
    form = registerForm()
    if form.validate_on_submit():
        print("it worked!")
        return redirect('/success')
    return render_template('register.html', form=form)

@app.route('/login', methods=['GET','POST'])
def login():
    form = loginForm()
    if form.validate_on_submit():
        print(f"Hello {form.username.data} your password is {form.password.data}")
        return redirect('/user')
    return render_template('login.html', form=form)

@app.route('/success')
def successRegister():
    return render_template('SuccessRegister.html')

@app.route('/')
def welcome():
    return render_template('welcome.html')

@app.route('/user')
def user():
    title = 'Welcome page'
    user = {'name': 'Joe', 'email':'joe@email.com'}
    return render_template('user.html',title=title, user=user)

# the name of the application is main by default
if __name__ == '__main__':
    app.run()
    
```

**Register HTML Code** 
```html
{% extends 'base.html' %}
{% block content %}
    <h1 id = title_user>Register</h1>
    <form action="" method="post">

        <div style="height: 100px; font-size:15px; width: 400px; left:100px">
            {{ form.csrf_token }}
            <p>
                {{ form.username.label }} {{ form.username() }}<br>
                <br>
                {{ form.email.label }} {{ form.email() }}

            <p>
                {{ form.sex.label }} {{ form.sex() }}
            </p>
            <p>
                {{ form.birthmonth.label }}{{ form.birthmonth() }}
            </p>
            <p>
                {{ form.birthYear.label }}{{ form.birthYear() }}
            </p>
            <p>
                {{ form.password.label }}{{ form.password() }}
            </p>
            <p>
                {{ form.submitRegister }}
            </p>

        </div>
    </form>

{% endblock %}
```
