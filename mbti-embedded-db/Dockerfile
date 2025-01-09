# node를 설치한다. 

# FROM 베이스 이미지를 설정한다.
ARG NODE_VERSION
FROM node:${NODE_VERSION}

# 소스코드를 다운로드한다.
# COPY [복사할 경로] [붙여넣기할 경로]
COPY . /app 

# 소스코드의 최상위 디렉토리로 이동한다.
WORKDIR /app

# 소스코드를 실행할 때 필요한 파일을 다운로드한다. (npm ci)
# \ : 줄바꿈 , && : and 한번에 명령어 쓸때 주로 사용.
RUN npm ci && \ 
npm run build 

# 소스코드 빌드한다. (npm run build)
## RUN npm run build

# 환경 변수를 정의한다. (port)
ENV PORT=3000

# 서버를 실행한다. (npm run start)
# JSON 배열로 설정 , 컨테이너가 실행될때 사용되는 명령어를 정의..
ENTRYPOINT ["npm" , "run" , "start"]

# docker 빌드 [옵션] [빌드 컨텍스트]

# docker buildx build \
#  -t hanheepark/mbti:embedded-db \
#  -t hanheepark/mbti \
#  --build-arg NODE_VERSION=20.15.1 \
#  -f ./Dockerfile \
#  --pull \
#  . 