# dl_tf_env
 **Description:** Builds Docker Images for Working on GPU-Accelerated Tensorflow Projects Using JupyterLab
 
**Docker Instructions**
```
docker pull axd465/dl_tf_env:tagname
docker run -it --rm --gpus all -u root -p 8888:8888 axd465/dl_tf_env:tagname
```
