FROM node:20 AS builder
WORKDIR /opt/server
COPY package.json .
COPY *.js .
RUN npm install


FROM node:20-alpine3.22
EXPOSE 8080
ENV DB_HOST="mysql"
RUN addgroup -S expense && adduser -S expense -G expense && \
    mkdir /opt/server && \
    chown -R expense:expense /opt/server
WORKDIR /opt/server
COPY --from=builder /opt/server /opt/server
USER expense
CMD ["node", "index.js"] 

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