FROM openmicroscopy/omero-server:5.6

USER root
RUN wget https://raw.githubusercontent.com/ome/omero-figure/master/omero_figure/scripts/omero/figure_scripts/Figure_To_Pdf.py -O /opt/omero/server/OMERO.server/lib/scripts/omero/figure_scripts/Figure_To_Pdf.py
RUN /opt/omero/server/venv3/bin/pip install reportlab markdown

USER omero-server
