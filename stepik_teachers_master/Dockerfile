from python:3.8.3-alpine

RUN mkdir -p /stepik_teachers
COPY . /stepik_teachers
WORKDIR /stepik_teachers

ENV FLASK_APP app.py

RUN pip install --upgrade pip && pip install -r requirements.txt
CMD ["flask", "run","--host", "0.0.0.0", "--port", "8888"]