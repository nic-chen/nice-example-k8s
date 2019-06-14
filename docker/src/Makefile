BUILD_NAME = nice-example

GO=$(shell which go)
BASE_PATH = $(shell pwd)

.PHONY: build run proto up
build: 
	$(GO) build -o cmd/$(BUILD_NAME) cmd/main.go

run: 
	cd cmd && ./$(BUILD_NAME) -c $(BASE_PATH)/cmd/config.yaml

up: build
	cd cmd && ./$(BUILD_NAME) -c $(BASE_PATH)/cmd/config.yaml

proto:
	for f in proto/**/*.proto; do \
		protoc --go_out=plugins=grpc:. $$f; \
		echo compiled: $$f; \
	done
