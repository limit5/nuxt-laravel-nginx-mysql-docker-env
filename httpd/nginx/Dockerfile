FROM nginx:1.27.0-alpine3.19-slim
# For alpine based image
RUN apk update && apk upgrade \
    && apk add ca-certificates tzdata \
    && rm -rf /var/cache/apk/*

# For ubuntu based image
# RUN apt update && \
#     apt install -y apt-utils \
#     locales && \
#     sed -i -e 's/# zh_TW.UTF-8 UTF-8/zh_TW.UTF-8 UTF-8/g' /etc/locale.gen && \
#     locale-gen zh_TW.UTF-8

ENV LANG=zh_TW.UTF-8
ENV LC_TIME=C
ENV TZ=Asia/Taipei

# For ubuntu based image
# RUN echo "${TZ}" > /etc/timezone \
#     && dpkg-reconfigure -f noninteractive tzdazta
COPY conf/default.conf /etc/nginx/conf.d/default.conf