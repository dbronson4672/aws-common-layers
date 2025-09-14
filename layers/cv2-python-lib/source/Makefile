build-CV2PythonLayer:
	# Update the system and pip
	dnf update -y
	# pip install --upgrade pip

	echo "Creating artifacts directory"
	mkdir -p "$(ARTIFACTS_DIR)/python"

	# Install the required packages
	# Use --target to install packages in the ./python directory
	# ReportLab

	pip install --target $(ARTIFACTS_DIR)/python opencv-python-headless
	pip install --target $(ARTIFACTS_DIR)/python numpy
	pip install --target $(ARTIFACTS_DIR)/python reportlab
	pip install --target $(ARTIFACTS_DIR)/python requests
	