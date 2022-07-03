# Python Notes

## Base Environment

This assumes a clean Ubuntu 20.04 install.
For reference, I used multipass on my M1 macbook air to create a vm:
```
multipass launch 20.04 --cpus 2 --disk 8G --mem 2G --name test-server
```

## Python Environment Setup

venv will be used to create a virtual environment for each project so we don't pollute the system python.
  
### Install venv and some helper utils:
```
sudo apt-get update
sudo apt-get install python3-pip
sudo apt-get install python3-venv
sudo apt-get install tree
```

### Create project dir:
```
mkdir -p ~/workspace/dan_learns_web_dev/test-project-with-venv
```

### Create python virtual environment:
```
cd ~/workspace/dan_learns_web_dev/test-project-with-venv
python3 -m venv ./env
```

### Load python virtual environment:
```
source ./env/bin/activate
```

Note: You can unload python virtual environment with:
```
deactivate
```


## Flask Setup

### Install Flask:
```
pip install Flask
```

### Create the test file: test.py
```
from flask import Flask
app = Flask(__name__)


@app.route("/")
def test():
  return "test response"

```

### Create the run script: run.sh 
```
#!/bin/env bash

export FLASK_APP=test.py
flask run -h 0.0.0.0 -p 5000
```

### Run the app:
```
bash ./run.sh
```

You should see the server start:
```
 * Serving Flask app 'test.py' (lazy loading)
 * Environment: production
   WARNING: This is a development server. Do not use it in a production deployment.
   Use a production WSGI server instead.
 * Debug mode: off
 * Running on all addresses (0.0.0.0)
   WARNING: This is a development server. Do not use it in a production deployment.
 * Running on http://127.0.0.1:5000
 * Running on http://192.168.64.2:5000 (Press CTRL+C to quit)
```

From a browser check you can hit the test server with the IP address shown in the output: http://192.168.64.2:5000/




