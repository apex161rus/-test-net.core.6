#See https://aka.ms/containerfastmode to understand how Visual Studio uses this Dockerfile to build your images for faster debugging.

FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /src
COPY ["сайт test net.core.6/сайт test net.core.6.csproj", "сайт test net.core.6/"]
RUN dotnet restore "сайт test net.core.6/сайт test net.core.6.csproj"
COPY . .
WORKDIR "/src/сайт test net.core.6"
RUN dotnet build "сайт test net.core.6.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "сайт test net.core.6.csproj" -c Release -o /app/publish /p:UseAppHost=false

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "сайт test net.core.6.dll"]
