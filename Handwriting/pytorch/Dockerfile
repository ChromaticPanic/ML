FROM nvcr.io/nvidia/pytorch:24.08-py3
WORKDIR /pytorch

RUN apt update
RUN apt install -y screen ffmpeg

RUN /usr/bin/python3 -m pip install --upgrade pip
COPY ["requirements.txt", "/pytorch/"]

RUN pip install -r requirements.txt

EXPOSE 8888

CMD ["jupyter", "lab", "--port=8888", "--notebook-dir=/data", "--no-browser", "--ip=0.0.0.0", "--allow-root"]