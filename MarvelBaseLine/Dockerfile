FROM mcr.microsoft.com/dotnet/core/aspnet:2.1-stretch-slim AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/core/sdk:2.1-stretch AS build
WORKDIR /src
COPY ["MarvelBaseLine/MarvelBaseLine.csproj", "MarvelBaseLine/"]
RUN dotnet restore "MarvelBaseLine/MarvelBaseLine.csproj"
COPY . .
WORKDIR "/src/MarvelBaseLine"

RUN dotnet publish "MarvelBaseLine.csproj" -c Debug --no-restore -o /app

WORKDIR /app
ENTRYPOINT ["dotnet", "MarvelBaseLine.dll"]
