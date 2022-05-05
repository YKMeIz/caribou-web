# caribou-web

Caribou Project is used to search and display Pixiv illustration.

### Prepare for Production

Please be aware that you may want to modify source if you plan to put this project into your production. For example, changing site favicon, names, etc.

Illustration information are fetched by APIs which is in same host and served by backend server in a separate repository [caribou-next](https://github.com/YKMeIz/caribou-next). It is required to bundle [caribou-web](https://github.com/YKMeIz/caribou-web) and [caribou-next](https://github.com/YKMeIz/caribou-next) together.

The API fetch functions in source code looks like:
```javascript
fetch(`//${window.location.hostname}/${this.$route.params.pixiv_id}.json`)
```

### Production Setup

1. Project setup
```
npm install
```
> Requires Node version <= 18.1.0

2. Compiles and hot-reloads for development
```
npm run serve
```

3. Compiles for production
```
npm run build
```
The compiled files are located in `./dist` folder.

4. Copy `./dist` folder into [caribou-next](https://github.com/YKMeIz/caribou-next) repository folder.
```
cp -r ./dist ~/somewhere/to/caribou-next/
```

5. Compile backend server
```
go build -o caribou-bin main.go
```

6. Run production service
```
caribou-bin
```
> `caribou-bin` and `./dist` folder must be in same folder.

### Production Scenario

The website may run as a virtual host served by docker container instance.

Here is a sample of Dockerfile:
```dockerfile
FROM golang:alpine

RUN apk add --no-cache tzdata

WORKDIR /
COPY ./caribou-bin .
ADD ./dist/ ./dist/

EXPOSE 9090/tcp

ENTRYPOINT ["/caribou-bin"]
```
