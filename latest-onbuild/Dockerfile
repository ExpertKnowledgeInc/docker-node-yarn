FROM node:latest

RUN apt-get update && apt-get install -y apt-transport-https

RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add -
RUN echo "deb https://dl.yarnpkg.com/debian/ stable main" |  tee /etc/apt/sources.list.d/yarn.list

RUN apt-get update && apt-get -y install yarn

ENV NODE_PATH /node_modules
ENV PROJECT_PATH /src
ENV PATH $NODE_PATH/.bin:$PATH
ENV NODE_ENV production

RUN mkdir -p $PROJECT_PATH

ONBUILD COPY package.json $PROJECT_PATH
ONBUILD COPY yarn.lock $PROJECT_PATH
ONBUILD RUN ln -s $PROJECT_PATH/package.json /package.json
ONBUILD RUN ln -s $PROJECT_PATH/yarn.lock /yarn.lock
ONBUILD RUN NODE_ENV=dev yarn install

ONBUILD WORKDIR $PROJECT_PATH
ONBUILD COPY . $PROJECT_PATH
