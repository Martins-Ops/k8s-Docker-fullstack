FROM node:8

RUN mkdir -p /home/app

# set default dir so that next commands executes in /home/app dir
WORKDIR /home/app

COPY . /home/app

# will execute npm install in /home/app because of WORKDIR
RUN npm install

EXPOSE 5000

CMD ["npm", "start"]
