#-------------------------------------------------------------------------------------------------------------
# Copyright (c) Microsoft Corporation. All rights reserved.
# Licensed under the MIT License. See https://go.microsoft.com/fwlink/?linkid=2090316 for license information.
#-------------------------------------------------------------------------------------------------------------

FROM ubuntu:22.04

ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get -y install --no-install-recommends \
	apt-utils \
	git \
	procps \
	ssh \
	python3-pygments \
	python3-pkg-resources \
	tex-gyre \
	curl \
	procps \
	texlive-latex-base \
	texlive-extra-utils \
	texlive-latex-extra \
	texlive-science \
	texlive-lang-polish \
	texlive-bibtex-extra \
	biber \
	chktex \
	latexmk \
	make \
	python3 \
	inkscape \
	biber

# latexindent modules
RUN curl -L http://cpanmin.us | perl - App::cpanminus \
    && cpanm Log::Dispatch::File \
    && cpanm YAML::Tiny \
    && cpanm File::HomeDir \
    && cpanm Unicode::GCString

# Clean up
RUN apt-get autoremove -y \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*

ENV DEBIAN_FRONTEND=dialog \
    LANG=C.UTF-8 \
    LC_ALL=C.UTF-8
