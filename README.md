# docker_project_hello-python-flask

- Creating a simple Python Flask Application
- Creating a docker image
- Pushing image to dockerhub


### Create index.py file

```py
from flask import Flask
helloworld = Flask(__name__)
@helloworld.route("/")
def run():
    return "{\"message\":\"Hey there python\"}"

if __name__ == "__main__":
    helloworld.run(host="0.0.0.0", port=int("3000"), debug=True)
```

#### Create index.py file
```txt
flask
```

#### Create index.py file
```sh
FROM python:3-alpine3.15
WORKDIR /app
COPY . /app
RUN pip install -r requirements.txt
EXPOSE 3000
CMD python ./index.py
```

#### Command to build the image
```sh
docker build -t franson14/hello-python-flask:0.0.1.RELEASE .
```

#### Command to push the image to docker hub
```sh
docker push franson14/hello-python-flask:0.0.1.RELEASE
```

#### Command to run the image
```sh
docker run -d -p 3000:3000 franson14/hello-python-flask:0.0.1.RELEASE
```

#### Open in browser
<img width="819" alt="Screenshot 2023-12-09 at 14 46 05" src="https://github.com/frank-goa/docker_project_hello-python-flask/assets/137857643/6f3ffa48-4d32-4f22-836a-d4dab95c5da7">
