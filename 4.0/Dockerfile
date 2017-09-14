FROM debian:stretch

ENV LLVM_VERSION 4.0

RUN apt-get update && apt-get install -y gnupg wget

RUN wget -qO - http://apt.llvm.org/llvm-snapshot.gpg.key | apt-key add - \
    && echo "deb http://apt.llvm.org/stretch/ llvm-toolchain-stretch-${LLVM_VERSION} main" >> /etc/apt/sources.list.d/llvm.list \
    && echo "deb-src http://apt.llvm.org/stretch/ llvm-toolchain-stretch-${LLVM_VERSION} main" >> /etc/apt/sources.list.d/llvm.list

RUN apt-get update && apt-get install -y \
    clang-${LLVM_VERSION}

RUN apt-get clean && rm -rf /var/lib/apt/lists/*

ENV CC clang-${LLVM_VERSION}
ENV CXX clang++-${LLVM_VERSION}