FROM congying/ubuntu-dev:14.04

MAINTAINER Congying <congying1112@gmail.com>




RUN apt-get install -y libfontconfig1 mesa-common-dev

RUN cd /tmp && wget http://download.qt.io/official_releases/qt/5.7/5.7.0/qt-opensource-linux-x64-5.7.0.run



RUN apt-get install -y libeigen3-dev libsuitesparse-dev
RUN apt-get install -y libqglviewer-dev

RUN cd /tmp && chmod +x qt-opensource-linux-x64-5.7.0.run
RUN apt-get install -y xorg openbox
RUN cd /tmp && ./qt-opensource-linux-x64-5.7.0.run



RUN apt-get install -y unzip
RUN cd /tmp && wget -O g2o.zip https://github.com/RainerKuemmerle/g2o/archive/master.zip && unzip g2o.zip
RUN apt-get remove -y unzip

RUN cd /tmp/g2o && mkdir build && cd build && cmake .. && make
RUN cd /tmp/g2o/build && make install