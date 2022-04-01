## Dependencies

* Python 3.10.3
* Node >= 17.4.0


## Full install

1. Install dependencies

```
brew install nvm
brew install pyenv
brew install redis
nvm install 17
pyenv install 3.10
```

2. Install python packages

```
pip install gunicorn
pip install uvicorn
```

3. Install dependencies, in 3 terminals

```
cd inventory
pip install -r requirements.txt
cp .env.example .env
```

```
cd payment
pip install -r requirements.txt
cp .env.example .env
```

```
cd inventory-frontend
npm install
cp .env.example .env
```

4. Run the server, in 3 terminals

```
cd inventory
python3 -m gunicorn -w 4 -k uvicorn.workers.UvicornWorker main:app --reload -b :8002
```

```
cd payment
python3 -m gunicorn -w 4 -k uvicorn.workers.UvicornWorker main:app --reload -b :8003
```

```
cd inventory-frontend
npm start
```


