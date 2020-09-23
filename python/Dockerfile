FROM jupyter/datascience-notebook

COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

RUN jupyter contrib nbextension install --user && jupyter nbextensions_configurator enable --user
RUN jt -t onedork -f inconsolata -T -N -cellw 90% -tfs 13

COPY ipaexg.ttf  /usr/share/fonts/truetype/ipaexg/
RUN echo 'font.family : IPAexGothic' >> /opt/conda/lib/python3.8/site-packages/matplotlib/mpl-data/matplotlibrc
RUN rm -r /home/jovyan/.config/matplotlib

COPY . .

RUN jupyter serverextension enable --py jupyterlab 
