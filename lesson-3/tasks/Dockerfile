FROM ubuntu:20.04
LABEL authors="skosovsky"

RUN apt-get update && apt-get install -y vim wget curl git

WORKDIR /home/skosovsky

COPY ./script.sh ./script.sh

RUN touch hello.sh && echo "echo 'Hello from container'" > hello.sh

RUN sh -c "$(wget -O- https://github.com/deluan/zsh-in-docker/releases/download/v1.1.5/zsh-in-docker.sh)" -- \
    -t robbyrussell \
    -p https://github.com/zsh-users/zsh-autosuggestions

ENV ZSH_AUTOSUGGEST_HIGHLIGHT_STYLE="fg=#ff00ff,bg=cyan,bold,underline"

ENTRYPOINT ["zsh"]

CMD ["hello.sh"]