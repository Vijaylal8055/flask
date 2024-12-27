#flask
Flask & task on Flask
#FLASK:It's the interface between front-end & back-end.
API-Application Programming Interface
app=Flask(__name__)
@app.route('/')
def index():
 return 'Hello World'
if__name__=='__main__':
 app.run(debug=True) #Starts the debugger
Output:
 Hello World

from flask import Flask,redirect,url_for
app=Flask(__name__)
@app.route('/')
def index():
 return "Hello World"
@app.route('/home')
def home():
 return "i am in home page"
@app.route('/page')
def page():
 return "i am in second page"
@app.route('/second')
def second():
 return "i am in second station"
#@app.route('/marks/<marks>')
@app.route('/marks/<int:marks>')
#@app.route('/marks/<float:marks>')
def marks(marks):
 print(type(marks))
 if marks>35:
 #return redirect("http://127.0.0.1:5000/home")
 return redirect(url_for("home"))
 else:
 #return redirect(" http://127.0.0.1:5000/page")
 return redirect(url_for("page"))

#return "marks"
app.run(use_reloader=True)

#Leap year-Task
from flask import Flask,redirect,url_for
app=Flask(__name__)
@app.route('/leapyear')
def leapyear():
 return "this is a leapyear"
@app.route('/normalyear')
def normalyear():
 return "this is a normalyear"
@app.route('/year/<int:year>')
def year(year):
 if year%4==0:
 return redirect(url_for("leapyear"))
 else:
 return redirect(url_for("normalyear"))
 
app.run(use_reloader=True)



