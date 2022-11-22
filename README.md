## MAC instruction:
### brew install (ifyou have a brew skip it)
#### step 1 
```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
#### step 2 
```shell
export PATH="/opt/homebrew/bin:$PATH"
```
#### step 3 
```shell
echo 'export PATH="/opt/homebrew/bin:$PATH"' >> $HOME/.zshrc
```

### dotnet install
```shell
brew install --cask dotnet
```
[sdk versions](https://github.com/isen-ng/homebrew-dotnet-sdk-versions) 
```shell
brew tap isen-ng/dotnet-sdk-versions
```
```shell
brew install --cask dotnet-sdk6-0-400
```
```shell
dotnet --list-sdks
```

### create new project
#### for creating Solution File 
```shell
dotnet new sln -o {ProjectName}
```

```shell
cd {ProjectName}
```
#### inside of solution directory
#### for creating Web Api 
```shell
dotnet new webapi -o {ProjectName}.Api
```

#### for creating Class Library 
```shell
dotnet new classlib -o {ProjectName}.Contracts
```
```shell
dotnet new classlib -o {ProjectName}.Infrastructure
```
```shell
dotnet new classlib -o {ProjectName}.Application
```
```shell
dotnet new classlib -o {ProjectName}.Domain
```

#### creating csproj recursively
```shell
dotnet sln {BuberDinner}.sln add **/*.csproj
```

#### building
```shell
dotnet build
```

#### Adding reference (dependency between projects)
```shell
dotnet add {ProjectName}.Api reference {ProjectName}.Contracts {ProjectName}.Application 
```
#### Adding reference (Infrastructure to Application)
```shell
dotnet add {ProjectName}.Infrastructure reference {ProjectName}.Application 
```
#### Adding reference (Application to Domain)
```shell
dotnet add {ProjectName}.Application reference {ProjectName}.Domain 
```
#### Adding reference (Api to Infrastructure)
```shell
dotnet add {ProjectName}.Api reference {ProjectName}.Infrastructure 
```
#### Adding reference (Api to Infrastructure)
```shell
dotnet run --project {ProjectName}.Api
```
#### install REST client on VS code (optional)
search type: 'rest client' then install

#### create http file inside sln
```shell
{ProjectName}/Requests/Weather/GetForecasts.http
```

#### add value data then save & click on 'send request' on top of freshly pasted link
```shell
GET http://localhost:5147/WeatherForecast
```

#### for addtional info About Clean Arch
- [youtube video](https://www.youtube.com/watch?v=fhM0V2N1GpY)
- [Medium post](https://medium.com/c-sharp-progarmming/building-clean-architecture-application-using-asp-net-core-web-api-and-angular-11-backend-81b57c315dfa)
- [Github](https://github.com/iayti/CleanArchitecture)
- [About Arch itself #1](https://www.c-sharpcorner.com/article/clean-architecture-in-asp-net-core-web-api/)
- [About Arch itself #2](https://www.c-sharpcorner.com/article/clean-architecture-with-asp-net-core-webapi/)

### Additional
#### adding login/register route
```shell
dotnet add BuberDinner.Application/ package Microsoft.Extensions.DependencyInjection.Abstractions
```