FROM ubuntu:20.04

ENV TZ=Australia/Melbourne

RUN apt-get -o Acquire::Check-Valid-Until=false -o Acquire::Check-Date=false update -y

RUN DEBIAN_FRONTEND=noninteractive \
    && apt-get install wget -y \
    && apt-get install software-properties-common -y \
    && apt-get install zsh -y \
    && apt-get install tzdata -y \
    && ln -snf /usr/share/zoneinfo/$TZ /etc/localtime \
    && wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb \
    && dpkg -i packages-microsoft-prod.deb \
    && apt-get update -y \
    && apt-get dist-upgrade -y \
    && apt-get install dotnet-sdk-3.1 -y \
    && apt-get install git -y \
    && apt-get install npm -y \
    && apt-get install python3.8 -y \
    && apt-get install python3-pip -y \
    && apt-get install python3-venv -y \
    && npm install -g npm@latest \
    && sh -c "$(wget https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)" \
    && npm install -g azure-functions-core-tools@3 --unsafe-perm true \
    && python3 -m pip install --upgrade pip

EXPOSE 7000