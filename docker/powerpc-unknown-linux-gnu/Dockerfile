FROM ubuntu:14.04

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    ca-certificates \
    cmake \
    curl \
    gcc \
    libc6-dev \
    make \
    pkg-config && \
    curl -LSfs http://japaric.github.io/trust/install.sh | \
    sh -s -- --git japaric/xargo --tag v0.3.3 --target x86_64-unknown-linux-gnu --to /usr/bin && \
    apt-get purge --auto-remove -y curl

COPY openssl.sh qemu.sh /
RUN apt-get install -y --no-install-recommends \
    g++-powerpc-linux-gnu \
    libc6-dev-powerpc-cross && \
    bash /openssl.sh 1.0.2j linux-ppc powerpc-linux-gnu- && \
    bash /qemu.sh 2.7.1 ppc

ENV CARGO_TARGET_POWERPC_UNKNOWN_LINUX_GNU_LINKER=powerpc-linux-gnu-gcc \
    CC_powerpc_unknown_linux_gnu=powerpc-linux-gnu-gcc \
    CXX_powerpc_unknown_linux_gnu=powerpc-linux-gnu-g++ \
    OPENSSL_DIR=/openssl \
    QEMU_LD_PREFIX=/usr/powerpc-linux-gnu \
    RUST_TEST_THREADS=1
