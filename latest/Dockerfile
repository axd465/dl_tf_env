FROM tensorflow/tensorflow:latest-gpu-jupyter

RUN python3 -m pip install -U pip
RUN rm -r /tf
RUN mkdir -p /tf && chmod -R a+rwx /tf/
RUN chmod -R 755 /tmp && chmod -R 755 /var
RUN chmod a+rwx /.local

# For Tensorflow Latest
RUN python3 -m pip install --no-cache-dir -q opencv-python-headless \
    imageio \
    scikit-image \
    scikit-learn \
    pandas \
    seaborn

# Add custom user settings
RUN cd ~
RUN rm -r /root/.jupyter
COPY /.jupyter /root/.jupyter
RUN python3 -m pip install --no-cache-dir -q install jupyterlab

WORKDIR /tf
EXPOSE 8888

CMD ["bash", "-c", "source /etc/bash.bashrc && jupyter lab --notebook-dir=/tf --ip 0.0.0.0 --no-browser --allow-root"]
