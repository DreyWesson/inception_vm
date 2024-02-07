FROM alpine:3.18

RUN apk update && apk upgrade && apk add --no-cache nginx

WORKDIR /usr/share/nginx/html

COPY requirements/bonus/website/conf/new_portfolio-master/package.json .
COPY requirements/bonus/website/conf/new_portfolio-master/package-lock.json .

RUN apk add --no-cache nodejs npm 

COPY requirements/bonus/website/conf/default.conf /etc/nginx/http.d/default.conf

COPY requirements/bonus/website/conf/new_portfolio-master/dist /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
