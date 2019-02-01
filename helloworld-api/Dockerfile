FROM microsoft/dotnet:latest
COPY bin/Debug/netcoreapp2.2/publish/ /root/
EXPOSE 5000/tcp
ENTRYPOINT dotnet /root/helloworld-api.dll
