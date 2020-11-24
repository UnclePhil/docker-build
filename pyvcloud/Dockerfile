ARG SRC_IMG="python:3.8-slim"
FROM ${SRC_IMG}

## set some additional label
LABEL source="${SRC_IMG}"
LABEL owner="koenigphil@gmail.com"

## install
RUN apt -y update && \
apt -y install bash jq wget curl && \ 
pip install --no-cache-dir pyvmomi pyvcloud

ENV PS1="DkPyvmomi: $$(whoami):$$(pwd) $$" 
WORKDIR /root
CMD ["bash"]
