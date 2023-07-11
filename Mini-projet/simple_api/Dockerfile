FROM python:2.7-buster AS base

LABEL MAINTAINER="kamgaingrodrigue3@gmail.com"
VOLUME [ "/data" ]
EXPOSE 5000
COPY student_age.py /

FROM base AS build
RUN  apt update -y && apt install python-dev python3-dev libsasl2-dev python-dev libldap2-dev libssl-dev -y

RUN pip install flask==1.1.2 flask_httpauth==4.1.0 flask_simpleldap python-dotenv==0.14.0

#ADD git clone https://github.com/diranetafen/student-list.git /

#RUN cd student-list/

FROM build AS final
CMD ["python", "./student_age.py"]