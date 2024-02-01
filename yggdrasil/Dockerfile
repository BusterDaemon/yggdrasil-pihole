FROM alpine:edge AS build
WORKDIR /src
RUN apk update && apk upgrade && apk add go git && \
  git clone https://github.com/yggdrasil-network/yggdrasil-go && \
  cd yggdrasil-go && \
  ./build

FROM alpine:edge
WORKDIR /app
COPY --from=build /src/yggdrasil-go/yggdrasil ./
COPY --from=build /src/yggdrasil-go/yggdrasilctl ./
CMD [ "./yggdrasil", "-autoconf" ]
