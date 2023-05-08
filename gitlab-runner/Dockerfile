FROM gitlab/gitlab-runner:latest
RUN mkdir -p /srv/nginx/html && chmod -R 777 /srv/nginx
RUN sed -i.bak -e "s/http:\/\/archive\.ubuntu\.com/http:\/\/jp\.archive\.ubuntu\.com/g" /etc/apt/sources.list
RUN apt-get update && apt-get install -y --no-install-recommends \
    bison \
    cmake \
    flex \
    g++ \
    git \
    graphviz \
    # for libiconv
    libc6  \
    make \
    python3 \
    python3-distutils \
    rsync \
    vim \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*
RUN git clone https://github.com/google/googletest.git && \
    cd googletest && \
    cmake -S . -B build && \
    cd build && \
    make && make install && \
    cd .. && \
    rm -rf googletest
RUN git clone https://github.com/nmoa/doxygen.git && \
    cd doxygen && \
    cmake -S . -B build && \
    cd build && \
    make && make install && \
    cd .. && \
    rm -rf doxygen
RUN wget https://bootstrap.pypa.io/get-pip.py && \
    python3 get-pip.py
RUN python3 -m pip install gcovr
