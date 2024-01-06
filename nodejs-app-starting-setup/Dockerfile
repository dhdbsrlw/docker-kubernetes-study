FROM node

WORKDIR /app

# 모든 폴더가 컨테이너 내 app 폴더로 복사된다.
COPY . /app
# = COPY . ./

# 수행하고 싶은 커맨드 (모든 명령어는 working directory 에서 수행된다.)
RUN npm install

EXPOSE 80

# 잘못된 명령어: RUN node server.js
# 이미지는 컨테이너의 '템플릿' 이지 실행시키는 대상이 아니다. 따라서 서버 시작시키는 것을 템플릿 단에 삽입하면 곤란하다.
# RUN 대신 CMD 로 작성하면 이미지를 '생성'하는 단계에서는 위 명령어가 수행되지 않는다.
CMD ["node", "server.js"]
