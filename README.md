```bash
docker build -t slim/my-first-go-docker-app .
docker run --rm -it -p 8080:8080 slim/my-first-go-docker-app

heroku container:login

heroku container:push web --app enigmatic-beach-81231

heroku open --app enigmatic-beach-81231

heroku auth:token

docker login --username=_ --password=${YOUR_TOKEN} registry.heroku.com

docker build -t registry.heroku.com/enigmatic-beach-81231/web .
docker push registry.heroku.com/enigmatic-beach-81231/web
```

MacBook-Pro:src slim$ heroku create
Creating app... done, ⬢ enigmatic-beach-81231
https://enigmatic-beach-81231.herokuapp.com/ | https://git.heroku.com/enigmatic-beach-81231.git


heroku container:push web --app ${YOUR_APP_NAME}
heroku container:push web --app enigmatic-beach-81231
heroku open --app enigmatic-beach-81231

 heroku container:push web --app enigmatic-beach-81231
=== Building web (..............Heroku-Docker-Go/howtorundockerherokugo/zzsrc/Dockerfile)
Sending build context to Docker daemon  4.096kB
Step 1/7 : FROM golang:alpine AS build-env
---> cb1c8647572c
Step 2/7 : ADD . /src
---> 30ace4e076b3
Step 3/7 : RUN cd /src && go build -o goapp
---> Running in f2000a176405
Removing intermediate container f2000a176405
---> c2335b1a1d59
Step 4/7 : FROM alpine
---> caf27325b298
Step 5/7 : WORKDIR /app
---> Using cache
---> 33384b38c03a
Step 6/7 : COPY --from=build-env /src/goapp /app/
---> Using cache
---> 3b91f55af1a4
Step 7/7 : CMD ./goapp
---> Using cache
---> 8a678878edf7
Successfully built 8a678878edf7
Successfully tagged registry.heroku.com/enigmatic-beach-81231/web:latest
=== Pushing web ( Microservices/Docker/Heroku-Docker-Go/howtorundockerherokugo/zzsrc/Dockerfile)
The push refers to repository [registry.heroku.com/enigmatic-beach-81231/web]
9a0f627cc587: Pushed 
2c35a191944d: Pushed 
503e53e365f3: Pushed 
latest: digest: sha256:d4ed211513534eaf05341978bdc38993f4d6632576a4fe2c28fe1f159c52b3f9 size: 945
Your image has been successfully pushed. You can now release it with the 'container:release' command.

