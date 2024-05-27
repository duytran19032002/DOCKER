FROM node:20.12.2-alpine3.19
RUN npm install -g @angular/cli@17.3.4
RUN addgroup Jgroup && adduser -S -G Jgroup Juser
RUN mkdir -p /app  
RUN mkdir -p /app/data 
#RUN chmod -R u+rwx /app
#cho phep Juser va ca Jgroup                                                                
WORKDIR /app
COPY package*.json .
RUN  npm install 
COPY . .
RUN chown -R Juser:Jgroup /app
USER Juser
#RUN cd /app
ENV API_PATH=localhost://api.localhost
EXPOSE 4200
#CMD ["npm", "start"]
#ENTRYPOINT [ "npm", "start" ] 
ENTRYPOINT [ "ng","serve","--host","0.0.0.0","--disable-host-check" ]
# angular can cau hinh host dia chi ip thuc te/ react thi khong --> disable host check// co the day entrypoint vao pagekage.json script. start