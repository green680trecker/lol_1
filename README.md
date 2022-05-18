import sqlite3
from flask import Flask, render_template

app = Flask(__name__)

@app.route('/')
def get_unique_name():
    curso = sqlite3.connect('example.db')
    cur = curso.cursor()
    sql = ('SELECT FirstName from customers Group by FirstName ')
    cur.execute(sql)
    labels = cur.fetchall()
    labels = [i[0] for i in labels]
    curso.close()
    return render_template('index.html', labels=labels)

app.run(debug=True)
