FROM mcr.microsoft.com/dotnet/sdk:6.0 as build-env
WORKDIR /app
COPY Myproject/*.csproj ./Myproject/
RUN dotnet restore --locked-mode Myproject
COPY Myproject/. ./Myproject/
RUN dotnet publish --no-restore -c Release -o bin Myproject
FROM mcr.microsoft.com/dotnet/aspnet:6.0 as runtime-env
LABEL org.opencontainers.image.source https://github.com/<org>/<reponame>
WORKDIR /app
COPY --from=build-env /app/bin/ ./
EXPOSE 3000
ENTRYPOINT ["dotnet", ”Myproject.dll"]