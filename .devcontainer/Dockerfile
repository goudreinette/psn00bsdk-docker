FROM --platform=linux/amd64 ubuntu

RUN apt update
RUN apt install cmake wget unzip --yes

# RUN apt-get install -y libc6-amd64-cross libc6++-amd64-cross
# RUN ln -s /usr/x86_64-linux-gnu/lib64/ /lib64
# ENV LD_LIBRARY_PATH="$LD_LIBRARY_PATH:/lib64:/usr/x86_64-linux-gnu/lib"

RUN wget https://github.com/Lameguy64/PSn00bSDK/releases/download/v0.24/PSn00bSDK-0.24-Linux.zip
RUN unzip PSn00bSDK-0.24-Linux.zip -d /opt/
RUN mv /opt/PSn00bSDK-0.24-Linux /opt/psn00bsdk


ENV PSN00BSDK_LIBS=/opt/psn00bsdk/lib/libpsn00b

ENV PATH=/opt/psn00bsdk/bin:$PATH
RUN echo 'export "PATH=$PATH:/opt/psn00bsdk/bin"' >> /etc/profile

# ENV DOCKER_CONTAINER=true

# RUN git clone https://github.com/raylib4Consoles/raylib -b raylib4Consoles
# RUN git clone https://github.com/DragonMinded/libdragon.git -b unstable

# RUN cd /libdragon && make
# RUN cd /libdragon && make install
# RUN cd /libdragon/tools && make install

# #RUN cp ./scripts/raylib4Nintendo64.mk $N64_INST/include
# COPY raylib4Nintendo64.mk /n64_toolchain/include
# RUN cd /raylib/src && make PLATFORM=PLATFORM_NINTENDO64
# RUN cd /raylib/src && make PLATFORM=PLATFORM_NINTENDO64 install