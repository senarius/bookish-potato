## MAC instuction:
### brew install
- step 1 
```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
- step 2 
```shell
export PATH="/opt/homebrew/bin:$PATH"
```
- step 3 
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
- for creation Solution File ```shelldotnet new sln -o {ProjectName}```