#GO parmeters

TAG=1.0
NAMES=httpserver
HUB=eff4858/httpserver

build:
	@echo "build httpserver."
	@mkdir -p bin
	@GOOS=linux GOARCH=amd64 go build -o bin/httpserver

tag: build
	@echo "build httpserver images."
	@docker build -t ${HUB}:${TAG} .

push: tag
	@echo "push httpserver hub."
	@docker push ${HUB}:${TAG}

#启动容器
start:
	@echo "run container."
	@docker run -d --rm --name httpserver ${HUB}:${TAG}

#通过showip.sh脚本执行nsenter命令显示容器ip
show:
	@bash showip.sh
