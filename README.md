pip install -r requirements.txt

pip install gunicorn
pip install uvicorn

python3 -m gunicorn -w 4 -k uvicorn.workers.UvicornWorker main:app --reload -b :8000


