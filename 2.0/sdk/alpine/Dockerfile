FROM alpine:edge

# Install .NET CLI dependencies
RUN echo http://dl-cdn.alpinelinux.org/alpine/edge/testing >> /etc/apk/repositories
RUN apk update \
	&& apk upgrade \
	&& apk --no-cache add \
		libc6-compat \
		libcurl \
		libgcc \
		krb5-libs \
		icu-libs \
		lttng-ust-dev \
		libressl \
		libressl-dev \
		libssl1.0 \
		libstdc++ \
		libunwind \
		libuuid \
		zlib \
		curl \
		ca-certificates \
	&& update-ca-certificates \
	&& rm -rf /var/cache/apk/*

# Install .NET Core SDK
ENV DOTNET_SDK_VERSION 2.0.0-preview1-005977
ENV DOTNET_SDK_DOWNLOAD_URL https://dotnetcli.blob.core.windows.net/dotnet/Sdk/$DOTNET_SDK_VERSION/dotnet-dev-linux-x64.$DOTNET_SDK_VERSION.tar.gz
#ENV DOTNET_SDK_DOWNLOAD_URL https://download.microsoft.com/download/0/6/5/0656B047-5F2F-4281-A851-F30776F8616D/dotnet-dev-linux-x64.$DOTNET_SDK_VERSION.tar.gz

RUN curl -SL $DOTNET_SDK_DOWNLOAD_URL --output dotnet.tar.gz \
	&& mkdir -p /usr/share/dotnet \
	&& tar -zxf dotnet.tar.gz -C /usr/share/dotnet \
	&& rm dotnet.tar.gz \
	&& ln -s /usr/share/dotnet/dotnet /usr/bin/dotnet

# Return: Segmentation fault (core dumped)
#ENV NUGET_XMLDOC_MODE skip
#RUN mkdir warmup \
#	&& cd warmup \
#	&& dotnet new \
#	&& cd .. \
#	&& rm -rf warmup \
#	&& rm -rf /tmp/NuGetScratch
