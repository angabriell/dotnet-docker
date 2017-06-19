FROM dotnet-runtime-deps:gv1

# Installing .NET Core
ENV DOTNET_VERSION 1.1.2
ENV DOTNET_DOWNLOAD_URL https://download.microsoft.com/download/D/7/A/D7A9E4E9-5D25-4F0C-B071-210CB8267943/dotnet-ubuntu.16.04-x64.$DOTNET_VERSION.tar.gz

RUN curl -SL $DOTNET_DOWNLOAD_URL --output dotnet.tar.gz \
	&& mkdir -p /usr/share/dotnet \
	&& tar -zxf dotnet.tar.gz -C /usr/share/dotnet \
	&& rm -f dotnet.tar.gz \
	&& ln -s /usr/share/dotnet/dotnet /usr/bin/dotnet
