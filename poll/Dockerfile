FROM python:3
WORKDIR /app
COPY . .
RUN pip3 install -r requirements.txt
EXPOSE 80
ENV FLASK_APP=app.py
CMD [ "flask", "run", "--host=0.0.0.0", "--port=80" ]