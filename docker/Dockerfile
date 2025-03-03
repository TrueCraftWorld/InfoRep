# Используем официальный образ Ubuntu 20.04
FROM ubuntu:22.04
ENV DEBIAN_FRONTEND=noninteractive
ENV TZ=Europe/Moscow
# Замените на ваш часовой пояс
# Устанавливаем необходимые пакеты
RUN apt-get update && \
    apt-get install -y --no-install-recommends\
    build-essential \
    binutils \
    cmake \
    git \
    python3 \
    python-is-python3 \
    gdb \
    gcc-aarch64-linux-gnu \
    g++-aarch64-linux-gnu \
    binutils-aarch64-linux-gnu \
    && mkdir -p /home/kikorik/QtFolder/ \
    && rm -rf /var/lib/apt/lists/* \
    && ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone \
    && groupadd -g 1000 devgroup \
    && useradd -u 1000 -g devgroup -m -s /bin/bash kikorik



COPY ./Qt5.15.8_armV8_nopulseaudio /home/kikorik/QtFolder/Qt5.15.8_armV8_nopulseaudio
ENV PATH="/home/kikorik/QtFolder/Qt5.15.8_armV8_nopulseaudio/host_qt5_aarch/bin:${PATH}"
# RUN export PATH=/home/kikorik/QtFolder/Qt5.15.8_armV8_nopulseaudio/host_qt5_aarch/bin:$PATH

# USER kikorik
# WORKDIR /home/kikorik/

# Создаем рабочую директорию внутри контейнера (опционально, но рекомендуется)

# Устанавливаем часовой пояс (опционально)

# Команда по умолчанию при запуске контейнера
CMD ["bash"]
