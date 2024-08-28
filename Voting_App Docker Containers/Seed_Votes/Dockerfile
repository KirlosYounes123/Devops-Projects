FROM ubuntu
RUN apt-get update -y && \
    apt-get upgrade -y && \
    apt-get install -y apache2-utils && apt-get install software-properties-common -y && add-apt-repository ppa:deadsnakes/ppa && \
    apt-get install python3.9 -y && \
    rm -rf /var/lib/apt/lists/*
COPY . /seed/
WORKDIR /seed/
RUN python3 /seed/make-data.py
RUN chmod +x /seed/new.sh
CMD /seed/new.sh