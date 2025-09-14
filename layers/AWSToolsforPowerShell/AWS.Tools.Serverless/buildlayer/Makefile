build-PwshAWSToolsLayer:
	# Download AWSToolsLayer module binaries
	curl -L -o $(ARTIFACTS_DIR)/AWS.Tools.zip https://sdk-for-net.amazonwebservices.com/ps/v4/latest/AWS.Tools.zip
	mkdir -p $(ARTIFACTS_DIR)/modules

# Extract Entire AWS.Tools modules
#	unzip $(ARTIFACTS_DIR)/AWS.Tools.zip -d $(ARTIFACTS_DIR)/modules

# Extract select AWS.Tools modules (AWS.Tools.Common required)
	unzip $(ARTIFACTS_DIR)/AWS.Tools.zip 'AWS.Tools.Common/**/*' -d $(ARTIFACTS_DIR)/modules/
	unzip $(ARTIFACTS_DIR)/AWS.Tools.zip 'AWS.Tools.S3/**/*' -d $(ARTIFACTS_DIR)/modules/
	unzip $(ARTIFACTS_DIR)/AWS.Tools.zip 'AWS.Tools.SQS/**/*' -d $(ARTIFACTS_DIR)/modules/	
	unzip $(ARTIFACTS_DIR)/AWS.Tools.zip 'AWS.Tools.DynamoDBv2/**/*' -d $(ARTIFACTS_DIR)/modules/	
	unzip $(ARTIFACTS_DIR)/AWS.Tools.zip 'AWS.Tools.SimpleSystemsManagement/**/*' -d $(ARTIFACTS_DIR)/modules/
    #unzip $(ARTIFACTS_DIR)/AWS.Tools.zip 'AWS.Tools.SimpleEmail/**/*' -d $(ARTIFACTS_DIR)/modules/

	rm $(ARTIFACTS_DIR)/AWS.Tools.zip
