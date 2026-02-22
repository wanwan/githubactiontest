# syntax=docker/dockerfile:1

FROM ubuntu:22.04

RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    cmake \
 && rm -rf /var/lib/apt/lists/*

WORKDIR /app

# ソースをコンテナへコピー
COPY . .

RUN rm -rf build CMakeCache.txt CMakeFiles

# out-of-source build
RUN cmake -S . -B build -DCMAKE_BUILD_TYPE=Release \
 && cmake --build build -j \
 && cmake --install build --prefix /out
