FROM microsoft/dotnet:2.1-sdk as build-env
WORKDIR /api

COPY api.csproj .
RUN dotnet restore

COPY . .
RUN dotnet publish -o /publish

# Build runtime container
FROM microsoft/dotnet:2.1-aspnetcore-runtime
WORKDIR /app
COPY --from=build-env /publish /app
ENTRYPOINT [ "dotnet" , "api.dll"]
