FROM ubuntu:16.04
 
RUN apt update && apt install -y \
	emacs \
    xz-utils \
    build-essential \
    curl \
    && rm -rf /var/lib/apt/lists/* \
    && curl -SL http://releases.llvm.org/5.0.1/clang+llvm-5.0.1-x86_64-linux-gnu-ubuntu-16.04.tar.xz \
    | tar -xJC . && \
    mv clang+llvm-5.0.1-x86_64-linux-gnu-ubuntu-16.04 clang_5.0.1 && \
    echo 'export PATH=/clang_5.0.1/bin:$PATH' >> ~/.bashrc && \
    echo 'export LD_LIBRARY_PATH=/clang_5.0.1/lib:LD_LIBRARY_PATH' >> ~/.bashrc
   

CMD [ "/bin/bash" ]