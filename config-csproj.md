```
  <ItemGroup>
    <EmbeddedResource Remove="ClientApp\node_modules\**" />
    <None Remove="ClientApp\node_modules\**" />
    <Compile Remove="ClientApp\node_modules\**" />
    <Content Remove="ClientApp\node_modules\**" />
    <EmbeddedResource Remove="ClientApp\.git\**" />
    <None Remove="ClientApp\.git\**" />
    <Compile Remove="ClientApp\.git\**" />
    <Content Remove="ClientApp\.git\**" />
    <None Remove="ClientApp\package-lock.json" />
    <Compile Remove="ClientApp\package-lock.json" />
    <Content Remove="ClientApp\package-lock.json" />
    <EmbeddedResource Remove="ClientApp\dist\**" />
    <None Remove="ClientApp\dist\**" />
    <Compile Remove="ClientApp\dist\**" />
    <Content Remove="ClientApp\dist\**" />
  </ItemGroup>
```
