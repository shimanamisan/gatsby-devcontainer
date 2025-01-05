FROM node:22.12.0-alpine3.21

RUN apk update && apk upgrade && \
    apk add --no-cache python3 make g++ git yarn bash tzdata sudo && \
    cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
    echo "Asia/Tokyo" > /etc/timezone && \
    yarn global add gatsby-cli && \
    # 不要なキャッシュやファイルを削除
    rm -rf /var/cache/apk/* && \
    # nodeユーザーにroot権限を追加
    echo 'node ALL=(ALL) NOPASSWD: ALL' >> /etc/sudoers

WORKDIR /workspace

# フォアグラウンドプロセスを実行する方法の一つ
CMD ["tail", "-f", "/dev/null"]