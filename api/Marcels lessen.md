## Marcel's aantekeningen

Upgrade source code naar aspnet core 2.1

daarna: dotnet publish

starten via docker:
*docker run --rm -it -v D:\Sources\cursus\api\bin\Debug\netcoreapp2.1\publish:/publish-p 8080:80 microsoft/dotnet:2.1-aspnetcore-runtime*


Na het aanmaken van de Dockerfile kun je de container aanmaken met het volgende commando:

*docker build -t cursus/generator .*

daarna kun je de container starten met het commando:

*docker run -p:8080:80 cursus/generator*


Om te ontwikkelen op je windows machine, maar daarna te runnen in een Linux container doe je het volgende:

docker run --rm -it -v D:\Sources\cursus\api\ /src -p 8081:80 microsoft/dotnet:2.1-sdk


Start dotnet in de background:

dotnet run &

en weer terug naar de foreground:

fg

Dockerfile aangepast aan builden in de container.
Dit betekent: eerst kopieren, dan dotnet restore dotnet publish

Commando :

docker build -t marpos/generator .

om deze te runnen:

docker run --rm -it -p 8080:80 marpos/generator:latest 

