from flask import Flask
from flask import request
import subprocess
import socket
app = Flask(__name__)
@app.route('/', methods = ['POST', 'GET'])
def seedFunc():
    if request.method == 'GET':
        return socket.gethostname();
    if request.method == 'POST':
        stress_test = subprocess.popen(["sudo","python3","stress_cpu.py"]);

if __name__ == "__main__":
    app.run()