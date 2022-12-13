FROM node:19-bullseye
SHELL ["/bin/bash", "-couxe", "pipefail"]

USER node

WORKDIR /home/node/

RUN git clone https://github.com/iaincollins/icarus.git ./icarus

WORKDIR /home/node/icarus/

RUN npm install

RUN npm run build:standalone

CMD ./dist/icarus-terminal-service-linux --save-game-dir "${LOG_DIR}"

