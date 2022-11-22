## MAC instuction:
### brew install
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
dotnet sln add (ls -r **\*.csproj)
```

#### building
```shell
dotnet build
```