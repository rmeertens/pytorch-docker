FROM nvidia/cuda:8.0-cudnn5-devel

RUN apt-get update \
  && apt-get install -y python3-pip python3-dev \
  && cd /usr/local/bin \
  && ln -s /usr/bin/python3 python \
  && pip3 install --upgrade pip


RUN pip3 install jupyter
RUN pip3 install torch torchvision
RUN pip3 install matplotlib
RUN apt-get install -y git

COPY jupyter_notebook_config.py /root/.jupyter/
COPY run_jupyter.sh /
RUN chmod +x /run_jupyter.sh

WORKDIR "/notebooks" 
CMD ["/run_jupyter.sh"]

