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
4. Rebuild your project.
5. execute get-version
	```
	nbgv get-version
	```
	You''ll see similar info below:
	
	Version:                      1.0.1.10901
	AssemblyVersion:              1.0.0.0
	AssemblyInformationalVersion: 1.0.1-beta+2a959231cf
	NuGetPackageVersion:          1.0.1-beta-g2a959231cf
	NpmPackageVersion:            1.0.1-beta.g2a959231cf
	
	Note:
	 **AssemblyInformationalVersion**  =	**semver** + **GitCommitID**(short)
	 Which is what we want to print on our apps homepage.
6. If you run the app on Release mode, you'll see  the AssemblyInformationalVersion on homepage.
7. With this info we can confirm on app what build is running.