FROM centos:latest
RUN yum install python3  python3-devel   gcc-c++ -y && \
    yum -y install mesa-libGL && \
    python3 -m pip install --upgrade --force-reinstall pip && \
    yum install sudo -y && \
    yum install --assumeyes  python3-pip && \
    pip install keras && \
    pip install tensorflow --no-cache-dir  tensorflow && \
    pip install --upgrade pip tensorflow && \
    pip3 install flask && \
    pip3 install joblib && \
    pip3 install sklearn && \
    pip3 install pillow && \
    pip3 install numpy && \
    pip3 install gevent && \
    pip3 install opencv-contrib-python && \
    mkdir  /pneumonia_detection &&  \
    mkdir  /pneumonia_detection/templates && \
    mkdir  /pneumonia_detection/uploads && \
    mkdir  /pneumonia_detection/static && \
    mkdir  /pneumonia_detection/static/css && \
    mkdir  /pneumonia_detection/static/js && \
    mkdir  /pneumonia_detection/models

COPY  chest_xray.h5    /pneumonia_detection/models
COPY  app.py  /pneumonia_detection
COPY  index.html  /pneumonia_detection/templates
COPY  base.html   /pneumonia_detection/templates
COPY  main.css   /pneumonia_detection/static/css
COPY  main.js   /pneumonia_detection/static/js
EXPOSE  4444
WORKDIR  /pneumonia_detection
CMD export FLASK_APP=app.py
CMD export export LC_ALL=en_US.utf-8
CMD export export LANG=en_US.utf-8
ENTRYPOINT flask  run --host=0.0.0.0    --port=4444
