# Code_Refactoring_and_bug_fixing
Code refactor and bug fixing on VS code 
#vs terminal

python -m venv .env_flask
.env_flask
pip install flask
python app.py

#debugging process

from flask import Flask, render_template, request

app = Flask(__name__)

notes = []
@app.route('/', methods=["GET"])
def index():
    note = request.args.get("note")
    notes.append(note)
    return render_template("home.html", notes=notes)


if __name__ == '__main__':
    app.run(debug=True)
