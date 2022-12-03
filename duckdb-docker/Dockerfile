FROM python:3.10.8

# Install VIM and Bash completion
RUN apt-get update && apt-get install -y \
    build-essential \
    vim \
    bash-completion \
    git \ 
    curl \
    --no-install-recommends \
    ca-certificates \
    && \
    apt-get clean

# Install Python Requirements
RUN pip3 install -U pip
RUN pip3 install -U wheel
RUN pip3 install -U setuptools
RUN pip install duckdb~=0.6.0
