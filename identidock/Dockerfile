FROM python:3.7

RUN groupadd -r uwsgi && useradd -r -g uwsgi uwsgi
RUN pip install -i https://mirrors.aliyun.com/pypi/simple/ \
         Flask==1.1.2 uWSGI==2.0.18 requests==2.23 redis==3.4.1
WORKDIR /app
COPY app /app
COPY cmd.sh /
RUN chmod +x /cmd.sh

EXPOSE 9090 9191
USER uwsgi

CMD ["/cmd.sh"]
