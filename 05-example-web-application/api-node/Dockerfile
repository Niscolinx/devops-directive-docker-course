FROM node:gallium-alpine3.18

WORKDIR /usr/src/app

ENV NODE_ENV=production

COPY package*.json ./

RUN --mount=type=cache,target=/user/src/app/.npm \
    npm set cache /user/src/app/.npm && \
    npm ci --only=production

USER nodejs

COPY --chown=nodejs:nodejs ./src .

EXPOSE 3000

CMD ["node", "index.js"]

