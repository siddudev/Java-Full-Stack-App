FROM node:21-alpine AS stage1
WORKDIR /frontend
COPY . .
RUN npm install
RUN npm run build

FROM nginx
COPY --from=stage1 /frontend/build /usr/share/nginx/html
