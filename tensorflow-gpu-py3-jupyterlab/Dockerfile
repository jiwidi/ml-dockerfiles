FROM tensorflow/tensorflow:2.0.1-gpu-py3

RUN python3 -m pip install ipywidgets jupyter jupyterlab
RUN jupyter notebook --generate-config
RUN sed -i "/c.NotebookApp.open_browser/c c.NotebookApp.open_browser = False" /root/.jupyter/jupyter_notebook_config.py \
        && sed -i "/c.NotebookApp.ip/c c.NotebookApp.ip = '*'" /root/.jupyter/jupyter_notebook_config.py \
        && sed -i "/c.NotebookApp.notebook_dir/c c.NotebookApp.notebook_dir = '/root'" /root/.jupyter/jupyter_notebook_config.py \ 
        && sed -i "/c.NotebookApp.password/c c.NotebookApp.password = 'sha1:6196cf499dee:ea0e45876861548226e815f218dbbccd8807e0fb'" /root/.jupyter/jupyter_notebook_config.py

CMD ["jupyter", "lab", "--allow-root"]
