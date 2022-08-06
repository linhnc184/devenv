FROM node:16

ENV NODE_ENV=development

COPY ["package.json", "package-lock.json*", "./"]

RUN npm install

COPY . .

CMD ["node", "start"]
