ARG NODE_VERSION
FROM node:${NODE_VERSION}

COPY . /app

WORKDIR /app

RUN npm ci && \ 
npm run build

ENV PORT=3001
ENV DB_HOST=localhost
ENV DB_PORT=3306
ENV DB_NAME=db_mbti
ENV DB_USERNAME=user_mbti
ENV DB_PASSWORD=pw_mbti

ENTRYPOINT ["npm" , "run" , "start"]

# docker buildx build \
#  -t hanheepark/mbti:mysql \
#  -t hanheepark/mbti \
#  --build-arg NODE_VERSION=20.15.1 \
#  -f ./Dockerfile \
#  --pull \
#  . 