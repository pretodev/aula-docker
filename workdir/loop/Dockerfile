FROM ubuntu:22.04

RUN apt update
RUN apt install -y curl gnupg build-essential
RUN curl -fsSL https://deb.nodesource.com/setup_22.x -o nodesource_setup.sh
RUN bash nodesource_setup.sh
RUN apt install -y nodejs

WORKDIR /app

COPY index.js ./

CMD ["node", "index.js"]