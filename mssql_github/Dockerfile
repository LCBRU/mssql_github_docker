FROM python:3.6

LABEL maintainer="rabramley@gmail.com"

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

ADD .git* /root/
RUN chmod 600 /root/.git-credentials

RUN git clone https://github.com/LCBRU/mssql_github.git /usr/src/app/

RUN pip install --no-cache-dir -r requirements.txt

CMD [ "python", "-u", "/usr/src/app/run.py"]
