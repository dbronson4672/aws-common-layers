build-PillowPythonLayer:
	# Update the system and pip
	dnf update -y
	pip install --upgrade pip

	echo "Creating artifacts directory"
	mkdir -p "$(ARTIFACTS_DIR)/python"

	# Install the required packages
	# Use --target to install packages in the ./python directory

	pip install --target $(ARTIFACTS_DIR)/python Pillow