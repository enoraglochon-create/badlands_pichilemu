FROM badlandsmodel/badlands:latest

USER root
RUN apt-get update && apt-get install -y git

USER jovyan
COPY requirements.txt /tmp/
RUN pip install -r /tmp/requirements.txt
