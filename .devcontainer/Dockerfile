FROM ros:melodic

ARG distro=melodic

ENV DEBIAN_FRONTEND=noninteractive

# Builder dependencies installation
RUN apt-get update \
    && apt-get install -qq -y --no-install-recommends \
    build-essential \
    git \
    libssl-dev \
    libusb-1.0-0-dev \
    pkg-config \
    libgtk-3-dev \
    libglfw3-dev \
    libgl1-mesa-dev \
    libglu1-mesa-dev \    
    curl \	
    libusb-1.0-0 \
    udev \
    apt-transport-https \
    ca-certificates \
    curl \
    wget \
    swig \
    software-properties-common \
    && rm -rf /var/lib/apt/lists/*

RUN wget https://github.com/Kitware/CMake/releases/download/v3.28.4/cmake-3.28.4-linux-x86_64.sh \
    -O cmake.sh && \
    chmod +x cmake.sh && \
    ./cmake.sh --skip-license --exclude-subdir --prefix=/usr/local && \
    rm cmake.sh
    
RUN echo "source /opt/ros/$distro/setup.bash" >> /etc/bash.bashrc

# ENV DEBIAN_FRONTEND=noninteractive
# RUN apt-get update \
#    && apt-get -y install --no-install-recommends  ros-foxy-xacro ros-foxy-gazebo-ros ros-foxy-rviz2 ros-foxy-joint-state-publisher-gui\
#    #
#    # Clean up
#    && apt-get autoremove -y \
#    && apt-get clean -y \
#    && rm -rf /var/lib/apt/lists/*
# ENV DEBIAN_FRONTEND=dialog  