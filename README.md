# GitVersioningDemo

1. Get Assembly Product Version and show it on home page
2. Install NerdBank.GitVersioning 
	```
	// global
	dotnet tool install -g nbgv
	// or as tool
	dotnet tool install --tool-path . nbgv
	```
	For this example i'm installing it globally.
3. Initialize nvgb into your repo.
	```
	nbgv install
	```