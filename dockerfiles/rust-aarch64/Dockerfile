FROM ubuntu:24.04

RUN apt-get update && \
    apt-get install -y \
        build-essential \
        curl \
        git \
        clang \
        libclang-dev \
        gcc-aarch64-linux-gnu \
        g++-aarch64-linux-gnu \
        pkg-config \
        ca-certificates && \
    rm -rf /var/lib/apt/lists/*

RUN curl https://sh.rustup.rs -sSf | sh -s -- -y

ENV PATH="/root/.cargo/bin:${PATH}"

RUN rustup target add aarch64-unknown-linux-gnu
