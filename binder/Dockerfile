FROM python:3.6
# install the notebook package
RUN pip install --no-cache --upgrade pip && \
    pip install --no-cache notebook

# create user with a home directory
ARG NB_USER
ARG NB_UID
ENV USER ${NB_USER}
ENV HOME /home/${NB_USER}

RUN adduser --disabled-password \
    --gecos "Default user" \
    --uid ${NB_UID} \
    ${NB_USER}
WORKDIR ${HOME}

RUN apt-get install git \
 && cd /root \
 && git clone https://github.com/mapbox/tippecanoe.git tippecanoe \
 && cd /root/tippecanoe \
 && make \
 && make install \
 && cd /root \
 && pip install label-maker pygis

RUN git clone https://github.com/giswqs/label-maker-binder.git /home/${NB_USER}/label-maker-binder \
 && mv /home/${NB_USER}/label-maker-binder/* /home/${NB_USER} \
 && rm -rf /home/${NB_USER}/label-maker-binder \
 && chown -R ${NB_USER} /home/${NB_USER}
# RUN pip install tensorflow keras