NAME="zimbra"
VERSION=latest
BUILD=`date '+%Y-%m-%d_%H:%M:%S'`


build:
	echo build: \"$(BUILD)\" > ./build.yaml
	docker build --tag=$(NAME):$(VERSION) . | tee docker-build.log 
	docker tag $(NAME):$(VERSION) $(NAME):latest

clean:
	rm -rf build.yaml docker-build.log

