# Step 1
FROM node:10-alpine as build-step
RUN mkdir /frontend
WORKDIR /frontend
COPY package.json /frontend
RUN npm install
COPY . /frontend
RUN npm run build

# Stage 2
FROM nginx:1.17.1-alpine
COPY --from=build-step /frontend/build /usr/share/nginx/html