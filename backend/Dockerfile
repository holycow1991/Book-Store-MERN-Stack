FROM node:14-alpine as build-base
WORKDIR /usr/src/app
COPY . .
RUN npm i -g

FROM node:14-alpine as development
WORKDIR /usr/src/app

COPY --from=build-base /usr/src/app . 

CMD ["npm", "run", "dev"]

FROM node:14-alpine as production

WORKDIR /usr/src/app

COPY --from=build-base /usr/src/app . 
CMD ["npm", "run", "start"]