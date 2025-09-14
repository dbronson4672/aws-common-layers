V = 1
GS_TAG ?= gs10051
GS_VERSION ?= 10.05.1

build-GhostscriptLayer:
	# Download and extract PowerShell binaries. Remove downloaded file
	dnf update -y
	dnf install -y findutils wget make gcc zip tar
	
	export GS_TAG=gs10040
	export GS_TAG=$(GS_TAG)
	export GS_VERSION=$(GS_VERSION)
	
	mkdir -p /usr/local/src/ghostscript
	cd /usr/local/src/ghostscript && wget https://github.com/ArtifexSoftware/ghostpdl-downloads/releases/download/$(GS_TAG)/ghostscript-$(GS_VERSION).tar.gz 
	
	cd /usr/local/src/ghostscript && tar -xvf ghostscript-$(GS_VERSION).tar.gz

	# find /usr/local/src/ghostscript -ls
	# pwd

	cd /usr/local/src/ghostscript/ghostscript-$(GS_VERSION) && ./configure --without-luratech
	cd /usr/local/src/ghostscript/ghostscript-$(GS_VERSION) && make
	cd /usr/local/src/ghostscript/ghostscript-$(GS_VERSION) && make install
	
	/usr/local/bin/gs --version

	mkdir -p $(ARTIFACTS_DIR)/bin
	cp /usr/local/bin/gs $(ARTIFACTS_DIR)/bin
	
	# mkdir -p $(ARTIFACTS_DIR)/lib
	# cp /usr/local/lib/libgs.so $(ARTIFACTS_DIR)/lib
	