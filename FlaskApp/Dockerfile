FROM ubuntu:16.04

RUN apt-get update -y && \
    apt-get install -y python-pip python-dev

# We copy just the requirements.txt first to leverage Docker cache
COPY ./requirements.txt /app/requirements.txt

WORKDIR /FlaskApp

RUN pip install Flask
RUN pip install scikit-learn
RUN pip install scipy
RUN pip install smart-open
RUN pip install tqdm
RUN pip install ConfigParser
RUN pip install pandas
RUN pip install numpy

COPY . /FlaskApp

ENTRYPOINT [ "python" ]

CMD [ "./app.py" ]