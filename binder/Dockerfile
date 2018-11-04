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

RUN apt-get install git
RUN mkdir /tmp
RUN git clone https://github.com/mapbox/tippecanoe.git /tmp
RUN cd /tmp
RUN make -j
RUN make install
