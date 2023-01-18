# hash:sha256:689956f10ba17ce062d4e5759697070c5df8a93d48667e509969ee498aaab3a2
FROM registry.codeocean.allenneuraldynamics.org/codeocean/jupyterlab:3.0.9-miniconda4.9.2-python3.8-ubuntu20.04

ARG DEBIAN_FRONTEND=noninteractive

ARG GIT_ASKPASS
ARG GIT_ACCESS_TOKEN
COPY git-askpass /

RUN conda install -y \
        jupyterlab==3.5.2 \
    && conda clean -ya

RUN pip install -U --no-cache-dir \
    matplotlib==3.6.3 \
    numpy==1.24.1 \
    nwbwidgets==0.10.0 \
    pandas==1.5.2 \
    pynwb==2.2.0

COPY postInstall /
RUN /postInstall
