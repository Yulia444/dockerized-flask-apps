from python:3.8.3-slim-buster

RUN mkdir -p /flask-food-delivery/
WORKDIR /flask-food-delivery/
COPY . /flask-food-delivery/

ENV SECRET_KEY my_secret_string

RUN pip install --upgrade pip && pip install -r requirements.txt
RUN pip install python-dotenv && pip install psycopg2-binary

CMD ["flask", "run", "--host", "0.0.0.0", "--port", "8884"]