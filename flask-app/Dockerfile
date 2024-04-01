FROM python:2.7-alpine3.11

WORKDIR /app

RUN apk update && apk add ca-certificates && rm -rf /var/cache/apk/*

ADD http://api.internal.netfree.link/ca/netfree-ca.crt /usr/local/share/ca-certificates/netfree-ca.crt

RUN update-ca-certificates

ENV NODE_EXTRA_CA_CERTS /etc/ssl/certs/ca-certificates.crt
ENV NODE_EXTRA_CA_CERTS /etc/ssl/certs/ca-certificates.crt
ENV REQUESTS_CA_BUNDLE /etc/ssl/certs/ca-certificates.crt
ENV SSL_CERT_FILE /etc/ssl/certs/ca-certificates.crt

RUN pip config set global.cert /usr/lib/ssl/certs/ca-certificates.crt

COPY requirements.txt .
COPY package*.json .

RUN pip install -r requirements.txt

RUN apk add --update nodejs npm

RUN npm install

COPY . .

RUN npm run build

EXPOSE 5000

CMD ["python","./app.py"]