FROM jupyter/scipy-notebook:latest
MAINTAINER unclephil <koenigphil@gmail.com>

RUN conda install --quiet --yes -c conda-forge jupyter_contrib_nbextensions && \
conda install --quiet --yes jupyter_dashboards -c conda-forge && \
conda install --quiet --yes nbconvert -c conda-forge && \
conda install --quiet --yes -c conda-forge elasticsearch && \
jupyter nbextension enable hide_input_all/main && \
jupyter nbextension enable toc2/main && \
jupyter nbextension enable move_selected_cells/main && \
jupyter nbextension enable table_beautifier/main && \
jupyter nbextension enable init_cell/main && \
jupyter nbextension enable python-markdown/main
