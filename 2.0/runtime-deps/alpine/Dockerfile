FROM alpine:edge

RUN echo http://dl-cdn.alpinelinux.org/alpine/edge/testing >> /etc/apk/repositories
RUN apk update
RUN apk --no-cache add ca-certificates \
	&& update-ca-certificates
# .NET Core dependencies
RUN apk --no-cache add \
	libc6-compat \
	libcurl \
	libgcc \
	krb5-libs \
	icu-libs \
	lttng-ust-dev \
	libssl1.0 \
	libstdc++ \
	libunwind \
	libuuid \
	zlib \
	curl
