FROM jupyter/minimal-notebook:399cbb986c6b as builder

# copy the config file
COPY ./binder/jupyter_notebook_config.py /etc/jupyter/jupyter_notebook_config.py

RUN pip install --no-cache-dir \
        pandas==1.1.5 \
        cvxpy==1.1.7 \
        plotly_express==0.4.1 \
        matplotlib==3.3.3 \
        scipy==1.5.4 && \
        beakerx-all==2.0.1 && \
    fix-permissions /home/$NB_USER

# Basic JupyterLab renderer support
RUN jupyter labextension install jupyterlab-plotly@4.14.1

ENV PYTHONPATH "${PYTHONPATH}:/home/jovyan/python"