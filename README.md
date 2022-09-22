# GitVersioningDemo
## Local Builds
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
5. execute to get-version
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

## Cloud Builds
8. Now time to move our app to the cloud, on azure devops create a new pipeline.
9. Make sure  shallow fetch is disabled or else **nbgv** will fail to execute.
	I find this setting quite tricky and this might save you the time and effort. 
	
	Edit pipeline -> 
	click options (on right handside) ->  
	triggers -> 
	YAML-> 
	Get sources -> 
	untick Shallow fetch -> 
	click Save and Queue
10. Pipeline runs and artifacts should now have the semver.

## Release Version
11. 
	
	   
## Refs
https://github.com/dotnet/Nerdbank.GitVersioning/blob/main/doc/nbgv-cli.md
https://ml-software.ch/posts/versioning-made-easier-with-nerdbank-gitversioning

> Written with [StackEdit](https://stackedit.io/).