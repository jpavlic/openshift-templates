build:
	docker build -t "jpavlic/node-debug-os" -f Dockerfile .

.PHONY:test
test:
	docker build -t "jpavlic/node-debug-os-candidate" -f Dockerfile .
	sh test/run
