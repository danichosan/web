# web
from flask import Flask

from flask import url_for

import random

app = Flask(__name__)

 

@app.route("/")

def hello_world():

    url_rastgele = '/rastgele_gercek'
    url_about = '/daniel'
    url_coin = '/flip_coin'
    return f'''
    
    <a href={url_about}>About Daniel!</a>

    <a href={url_rastgele}>Rastgele bir gerçeği görüntüle!</a>'

    <a href={url_coin}>Yazı tura!</a>'

    '''
   

 

@app.route("/rastgele_gercek")

def daniel():

    gercekler = ['Qusai', 'Daniel', 'Alperen', 'Ali Mete', 'Deniz']

    return f'<h1> Kazanan isim: {random.choice(gercekler)}</h1>'


@app.route("/daniel")
def hello():
    return '''
    
    <h1>Hello my name is Daniel!<h1>
    <h2> My favorite foods are pizza and pasta<h2>
    <h2> If you want to know more about me click the link down below<h2>
    <h3>https://blogs.mtdv.me/articles/ZcS9n2l8Xn<h3>
    
    '''


@app.route("/flip_coin")
def flip_coin():
    flip = random.randint(0,1)
    if flip == 0:
        return "HEADS"
    else:
        return "TAILS"




app.run(debug=True)

