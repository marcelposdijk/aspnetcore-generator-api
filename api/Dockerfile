FROM microsoft/dotnet:2.1-sdk
WORKDIR /api
COPY . .

RUN dotnet restore
RUN dotnet publish -o /publish

WORKDIR /publish
ENTRYPOINT [ "dotnet" , "/publish/api.dll"]