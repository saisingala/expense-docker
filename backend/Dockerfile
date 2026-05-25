FROM node:20 AS builder
RUN mkdir /opt/server
WORKDIR /opt/server
COPY package.json .
COPY *.js .
RUN npm install
CMD ["node", "index.js"]

FROM node:20-alpine3.22
EXPOSE 8080
ENV DB_HOST="mysql" 

# before best practices implenmented
# FROM node:20
# EXPOSE 8080
# ENV DB_HOST="mysql" 
# #for host network localhost and bridge n/w mysql
# RUN mkdir /opt/server
# WORKDIR /opt/server
# COPY package.json .
# COPY *.js .
# RUN npm install
# CMD ["node", "index.js"]