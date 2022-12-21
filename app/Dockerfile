FROM node as base

#Stage development
FROM base as development
WORKDIR /app
COPY . .
RUN npm install

#Stage production
FROM base as production
WORKDIR /app
COPY --from=development /app .
RUN npm install --production
CMD ["npm", "start"]