# hash:sha256:a1326b8e8df6c33b588c59720f1fbf1faf7b5ea8db69ed7ef84b1ba3284b9e8e
FROM registry.codeocean.allenneuraldynamics.org/codeocean/miniconda3:4.9.2-cuda11.7.0-cudnn8-ubuntu20.04

ARG DEBIAN_FRONTEND=noninteractive

ARG GIT_ASKPASS
ARG GIT_ACCESS_TOKEN
COPY git-askpass /

RUN conda install -y \
        jupyterlab==3.5.2 \
    && conda clean -ya

RUN pip install -U --no-cache-dir \
    matplotlib==3.6.2 \
    numpy==1.24.1 \
    nwbwidgets==0.10.0 \
    pandas==1.5.2 \
    pynwb==2.2.0

COPY postInstall /
RUN /postInstall
