FROM nginx   
COPY code /usr/share/nginx/html
RUN rm -rf /etc/nginx/conf.d/default.conf
RUN rm -rf /etc/nginx/nginx.conf
COPY nginx.conf /etc/nginx/nginx.conf
#COPY expense.conf /etc/nginx/conf.d/expense.conf
