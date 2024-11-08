.PHONY : push up

IMAGE_NAME := ...
IMAGE_TAG := latest
MOUNT_PATH := /mount
ECR_REPO := ...

push:
	docker system prune
	aws ecr-public get-login-password --region us-east-1 | docker login --username AWS --password-stdin public.ecr.aws/y9d9j4g5
	docker buildx build --no-cache --platform linux/amd64,linux/arm64 -t ${ECR_REPO}/${IMAGE_NAME}:${IMAGE_TAG} --push .
	docker logout public.ecr.aws
up:
	docker run -it --rm ${ECR_REPO}/${IMAGE_NAME}:${IMAGE_TAG}

