FROM ikeyasu/opengl:ubuntu16.04

ENV DEBIAN_FRONTEND oninteractive

# Create a working directory
WORKDIR /opt

# Install requirements
COPY ./requirements.txt .
RUN pip3 install --upgrade pip
RUN pip3 install chainer==6.3.0 cupy-cuda90==6.3.0
RUN pip install -r requirements.txt

# Install Minecraft needed libraries
RUN apt-get update && apt-get install -y \
    openjdk-8-jdk \
    libglu1-mesa-dev \
    freeglut3-dev \
    mesa-common-dev \
    mesa-utils \
    lxterminal \
    xvfb \
    xorg-dev \
 && apt-get clean && rm -rf /var/cache/apt/archives/* /var/lib/apt/lists/*

ENV APP "tail -f /dev/null"
# ENV APP "lxterminal -e 'bash -c /opt/dddqn.sh'"
