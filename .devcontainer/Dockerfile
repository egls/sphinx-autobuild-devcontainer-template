FROM ubuntu:latest 

# set timezone here so the container build process is not interuppted
ENV TZ=Europe/Zurich
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN apt-get update &&  \
    apt-get install -y git python3 python3-pip graphviz graphviz-doc  texlive-formats-extra \
    texlive-latex-recommended texlive-latex-extra texlive-fonts-recommended latexmk pandoc && \
    pip3 install sphinx sphinx-rtd-theme sphinx-autobuild recommonmark sphinx_markdown_tables sphinxcontrib-plantuml \ 
    sphinx-revealjs git+git://github.com/SuperKogito/sphinxcontrib-pdfembed && \
    apt-get install -y plantuml

CMD sphinx-autobuild -b html --host 0.0.0.0 --port 80 /sphinx-doc/source /sphinx-doc/build