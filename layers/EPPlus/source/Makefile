EPPLUS_VERSION ?= 8.2.0
EPPLUS_INTERFACES_VERSION ?= 8.1.0
NET_VERSION ?= net9.0

build-EPPlusLayer:
	# Download and extract PowerShell binaries. Remove downloaded file

	dnf -y install dotnet

	# mkdir /tmp/testproj
	dotnet new classlib -n testproj -o /tmp
	# cd /tmp/testproj

	# EPPlus Installing
	# ---------------------------
	dotnet add /tmp/testproj.csproj package EPPlus --version $(EPPLUS_VERSION)
	
	# EPPlus.Interfaces Installing
	# ---------------------------
	dotnet add /tmp/testproj.csproj package EPPlus.Interfaces --version $(EPPLUS_INTERFACES_VERSION)
	
	# EPPlus.System.Drawing Installing
	# ---------------------------------
	dotnet add /tmp/testproj.csproj package EPPlus.System.Drawing --version $(EPPLUS_INTERFACES_VERSION)

	mkdir $(ARTIFACTS_DIR)/EPPlus

	# Copying Dll's to the artifacts directory
	# ----------------------------------------

	find /root/.nuget/packages/epplus* -ls
	find /root/.nuget/packages/microsoft.* -ls

	cp  /root/.nuget/packages/epplus*/$(EPPLUS_VERSION)/lib/$(NET_VERSION)/*.dll $(ARTIFACTS_DIR)/EPPlus
	cp  /root/.nuget/packages/epplus*/$(EPPLUS_INTERFACES_VERSION)/lib/$(NET_VERSION)/*.dll $(ARTIFACTS_DIR)/EPPlus
# 	cp  /root/.nuget/packages/microsoft.extensions.*/*/lib/$(NET_VERSION)/*.dll $(ARTIFACTS_DIR)/EPPlus
# 	cp  /root/.nuget/packages/microsoft.io.recyclablememorystream/*/lib/netstandard2.1/*.dll $(ARTIFACTS_DIR)/EPPlus
	find $(ARTIFACTS_DIR)/EPPlus -ls 

	ls -ld $(ARTIFACTS_DIR)/EPPlus/*