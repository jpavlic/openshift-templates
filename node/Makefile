build:
	docker build -t "jpavlic/node-os" -f Dockerfile .

.PHONY:test
test:
	docker build -t "jpavlic/node-os-candidate" -f Dockerfile .
	sh test/run
