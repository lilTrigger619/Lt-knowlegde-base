 # Shopp project backend documentation

---

**Table of content**
1. [Installation](#installation)
1. [RunProject](#run-project)
1. [End points](#url-end-points)
1. [About](#about)

---

## Installation.

### Requirements.
- Terminal
- Python3
- python3-pip
- venv (python3 module)

### Steps.
1. clone this repo.
` git clone http://blahblah.com `

1. Start a virtualenv (make sure you have already installed this python module)
` python3 -m venv env`

1. Activate the virtual env.
` source ./env/bin/activate `

1. install all required modules.
` cd ./prject2backend/ && python3 -m pip install -r ./requirements.txt `

1. The Project is now successfully installed locally. To run the project continue to the next section on [how to run the project](#run-project)

You can deactivate the env by runing the following in your terminal
` deactivate `



---



## Run project.

Please make sure you have followed all the instructions to install the project locally on your machine.

1. Activate the virtual env.
` source ./env/bin/activate `

2. Create a database by making all migrations
```sh
python3 manage.py makemigrations # prepare to create the database
python3 manage.py migrate # create the database
```

3. Run `python3 manage.py runserver`

4. You can now access the endpoints using the default
  ` http:localhost:8000 `

To use all the necessary endpoints you can continue to the [Enpoints](#endpoints) of this documentation.

---

## Url endpoints.

---

## About.

