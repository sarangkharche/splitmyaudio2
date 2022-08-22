# base image
FROM python:3.9

# streamlit-specific commands
RUN mkdir -p /root/.streamlit
RUN bash -c 'echo -e "\
[general]\n\
email = \"\"\n\
" > /root/.streamlit/credentials.toml'
RUN bash -c 'echo -e "\
[server]\n\
enableCORS = false\n\
" > /root/.streamlit/config.toml'

RUN apt-get update && apt-get install -y libsndfile1 && apt-get install -y ffmpeg
RUN pip install --upgrade streamlit

# copy over and install packages
COPY ./requirements.txt ./requirements.txt
RUN pip3 install cython
RUN pip3 install -r requirements.txt --no-cache-dir 

# copying everything over
COPY . .

