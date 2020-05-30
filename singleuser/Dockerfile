ARG DOCKER_NOTEBOOK_IMAGE
FROM $DOCKER_NOTEBOOK_IMAGE
ARG JUPYTERHUB_VERSION
ARG NB_USER=jovyan
ARG NB_UID=1000
ARG NB_GID=100
USER root
ENV DEBIAN_FRONTEND=noninteractive
USER 1000
WORKDIR /home/jovyan
ARG PYTHON_VERSION=default
RUN mkdir /home/$NB_USER/work && fix-permissions /home/$NB_USER
RUN python3 -m pip install --no-cache jupyterhub==$JUPYTERHUB_VERSION
RUN python3 -m pip install --no-cache numpy==1.18.4
RUN python3 -m pip install --no-cache pandas==1.0.4 `matplotlib==3.2.1`
RUN python3 -m pip install --no-cache seaborn==0.10.1 scipy==1.4.1 scikit-learn==0.23.1
RUN python3 -m pip install --no-cache tensorflow-gpu==2.2.0
RUN python3 -m pip install --no-cache opencv-python==4.2.0.34 nltk==3.5 statsmodels==0.11.1
RUN python3 -m pip install --no-cache pydotplus==2.0.2 beautifulsoup4==4.9.1
COPY README.md /home/jovyan/work/README.md
# RUN cp -r /tf/notebooks /home/jovyan/work/tf/notebooks