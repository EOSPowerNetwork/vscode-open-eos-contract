###############################################################
##########     NO EDITS ARE NEEDED IN THIS FILE    ############
###############################################################

FROM jamesmart/eosio-clsdk:latest

# Args come from the devcontainer.json
ARG GITHUB_ACCOUNT
ARG REPOSITORY_NAME

# Pass the project root name into the container as an environment variable
# If you change this project root, you must also change the workspaceMount in devcontainer.json
ENV PROJROOT="eos"

# Install dependencies
RUN apt-get update \
    && apt-get install -yq   \
        unzip                \
        clang-tidy           \
        clang-format

# Clone the specified github repo
WORKDIR /root
RUN mkdir ${PROJROOT}
WORKDIR /root/${PROJROOT}
RUN git clone https://github.com/${GITHUB_ACCOUNT}/${REPOSITORY_NAME}.git .

# Make the build folder
RUN mkdir build
WORKDIR /root/${PROJROOT}/build
RUN cmake `clsdk-cmake-args` ..
RUN make -j $(nproc)