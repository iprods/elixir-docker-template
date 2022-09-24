# Base image
FROM node:16.17-alpine

# Add dependencies which are needed by the client but not part of the ARM images
RUN apk --update --no-cache add \
  python3 \
  make \
  g++ \
  && npm install -g npm@latest

# Set working directory
WORKDIR /app

# Add `/app/node_modules/.bin` to $PATH
ENV PATH /app/node_modules/.bin:$PATH

# Start app
CMD ["sh"]

