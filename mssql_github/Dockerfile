FROM python:3.7

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

RUN apt-get update && \
    apt-get -y upgrade && \
    DEBIAN_FRONTEND=noninteractive apt-get -y install \
        git && \
    apt-get clean

RUN svn export --force https://github.com/LCBRU/mssql_github/trunk/ /usr/src/app/

RUN mkdir -p /var/data
WORKDIR /var/data

RUN git clone git@github.com:LCBRU/mssql_github.git

RUN pip install --no-cache-dir -r requirements.txt

CMD [ "python", "-u", "/usr/src/app/uhl_reports.py" ]