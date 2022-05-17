VERSION 0.6

FROM alpine:3.15
WORKDIR /app

all:
  BUILD +test

test:
  BUILD +yamllint

yamllint:
  RUN apk --quiet --no-progress --no-cache add yamllint

  COPY . .

  ARG CI
  IF [ "${CI}" = "true" ]
    RUN yamllint --format=parsable .
  ELSE
    RUN yamllint --format=colored .
  END
