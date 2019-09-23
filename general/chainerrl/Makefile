.PHONY: build rm run bash
CONTAINER_NAME=chainerrl-baselines
CONTAINER_TAG=:v0.0.0
IMAGE_NAME=kumezawa/$(CONTAINER_NAME)$(CONTAINER_TAG)

build:
	docker build -t $(IMAGE_NAME) .

run:
	docker run -it --net host --rm --name $(CONTAINER_NAME) -d -p 6080:6080 -e VNC_PW=${VNC_PW} $(IMAGE_NAME)

rm:
	docker rm -f $(CONTAINER_NAME) || echo

bash:
	docker exec -i -t $(CONTAINER_NAME) bash

