# PWSH_VERSION is version of PowerShell to download
JRE_VERSION ?= 8u432-b06
# PWSH_ARCHITECTURE can be 'x64' or 'arm64'
JRE_ARCHITECTURE ?= x64
build-JavaRuntimeLayer:
# Download and extract PowerShell binaries. Remove downloaded file
	# ============================
	# Building Java Runtime Layer
	# ============================
	# Downloading Java Runtime binaries and formscanner
	#
	curl -L -o $(ARTIFACTS_DIR)/java-openjdk-jre-$(JRE_VERSION)-$(JRE_ARCHITECTURE).tar.gz https://builds.openlogic.com/downloadJDK/openlogic-openjdk-jre/$(JRE_VERSION)/openlogic-openjdk-jre-${JRE_VERSION}-linux-${JRE_ARCHITECTURE}.tar.gz
	mkdir -p $(ARTIFACTS_DIR)
	
	# Extracting Java Runtime binaries and formscanner
	tar zxf $(ARTIFACTS_DIR)/java-openjdk-jre-$(JRE_VERSION)-$(JRE_ARCHITECTURE).tar.gz -C $(ARTIFACTS_DIR)

	# Remove downloaded files and move extracted files to ARTIFACTS_DIR
	rm $(ARTIFACTS_DIR)/java-openjdk-jre-$(JRE_VERSION)-$(JRE_ARCHITECTURE).tar.gz
	mv $(ARTIFACTS_DIR)/openlogic-openjdk-jre-$(JRE_VERSION)-linux-$(JRE_ARCHITECTURE) $(ARTIFACTS_DIR)/java

	# Make PowerShell binary executable
	chmod +x $(ARTIFACTS_DIR)/java/bin/java