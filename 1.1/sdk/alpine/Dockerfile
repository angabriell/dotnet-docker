#FROM gliderlabs/alpine:edge
#FROM alpine:edge
FROM dotnet-runtime-deps:gv1

# Install .NET Core SDK
ENV DOTNET_SDK_VERSION 1.0.4
ENV DOTNET_SDK_DOWNLOAD_URL https://download.microsoft.com/download/E/7/8/E782433E-7737-4E6C-BFBF-290A0A81C3D7/dotnet-dev-ubuntu.16.04-x64.$DOTNET_SDK_VERSION.tar.gz

RUN curl -SL $DOTNET_SDK_DOWNLOAD_URL --output dotnet.tar.gz \
    && mkdir -p /usr/share/dotnet \
    && tar -zxf dotnet.tar.gz -C /usr/share/dotnet \
    && rm dotnet.tar.gz \
    && ln -s /usr/share/dotnet/dotnet /usr/bin/dotnet

# Trigger the population of the local package cache

#ENV NUGET_XMLDOC_MODE skip
#RUN mkdir warmup \
#	&& cd warmup \
#	&& dotnet new \
#	&& cd .. \
#	&& rm -rf warmup \
#	&& rm -rf /tmp/NuGetScratch
