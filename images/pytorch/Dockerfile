#FROM pytorch/pytorch:2.4.1-cuda11.8-cudnn9-devel
FROM pytorch/pytorch:2.4.1-cuda12.4-cudnn9-devel

USER root
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    bash \
    ca-certificates \
    curl \
    git \
    jq \
    sudo \
    && rm -rf /var/lib/apt/lists/*

# Make typing unicode characters in the terminal work.
ENV LANG=en_US.UTF-8
# Remove the `ubuntu` user and add a user `coder` so that you're not developing as the `root` user
RUN useradd coder \
    --create-home \
    --shell=/bin/bash \
    --uid=1000 \
    --user-group && \
    echo "coder ALL=(ALL) NOPASSWD:ALL" >>/etc/sudoers.d/nopasswd

USER coder