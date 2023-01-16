FROM ubuntu:22.04 AS build

RUN apt-get update && apt-get -y --no-install-recommends install \
    build-essential

WORKDIR /app
COPY . /app

RUN make

FROM ubuntu:22.04
COPY --from=build /app/build/client /usr/bin
#RUN groupadd -r user && useradd -r -g user user
#USER user

ENTRYPOINT [ "/usr/bin/client" ]
