<p align="center">
  <img width="480" height="230" src="/img/npm-logo.png">
</p>

<h1 align="center">npm Cheat Sheet</h1>

<p align="center">
A list of terminal commands and flags to help use npm. 
</p>


## Table of Contents
* [Basic npm commands](#basic-command)
* [Package creation](#Pakg-cr)
* [Package management](#Pakg-magt)
* [List packages](#list-packg)
* [npm versioning](#npm-ver)





<a name="basic-command"></a>
## Basic npm commands

Check version number of npm:

```
npm -v
```

Get help on npm:

```
npm help
```

Quick help for specific command:

```
npm <command> -h 
```
Example:

```
npm install -h
```

Search npm documentation and return the result:

```
npm help -search <command>
```
Example:

```
npm help -search install
```
<hr>

<a name="Pakg-cr"></a>
## Package creation

Initialize project and create package.json:

```
npm init
```
:bulb: **Note:** Follow the wizard dilligently.

Initialize project and create package.json file with default values:

```
npm init --yes
```

Set default author name for package.json:

```
npm config set init -author-name ‘your-name’
```

Set default license for package.json: 


```
npm set init -license ‘MIT’
```

Show default author name:


```
npm config get init -author-name
```

Show default license: 


```
npm get init-license
```

Delete default author name: 


```
npm config delete init -author-name
```


Delete default license:


```
npm config delete init -license 
```


 <hr>

<a name="Pakg-magt"></a>
## Package management

Install everything in package.json:


```
npm install
```

or 

```
npm i
```

Install a package:


```
npm install <package name>	
```

Example:

```
npm install lodash
```

Install a package as devDependency:


```
npm install <package name> --save-dev 
```

Example:

```
npm install lodash --save-dev 
```

Uninstalling local packages:

```
npm uninstall <package name> --save 
```

Or

```
npm un <package name> --save
```

Or

```
npm remove <package name> --save 
```

Or

```
npm rm <package name> --save 
```

Example: 

```
npm rm lodash --save
```

Install global packages: 

```
npm install <package name> g
```

Uninstall global packages: 


```
npm uninstall <package name> g
```

Or

```
npm un <package name> g
```

Or

```
npm remove <package name> g 
```

Or

```
npm rm <package name> g 
```

Example: 

```
npm rm lodash g
```

<hr>

<a name="list-packg"></a>
## List packages

List locally installed packages (includes all dependencies): 

```
npm list 
```

Restrict the depth of the tree by 1:  

```
npm list --depth 1
```
:bulb: NOTE: _It gives you only immediate dependencies of the packages._

<br>
Restrict the depth of the tree by 0: 

```
npm list --depth 0
```

:bulb: NOTE: _It gives you the list of all the packages and no dependencies for that particular package._

<br>
List globally installed packages (includes all dependencies):

```
npm list --global
```

Or

```
npm list -g
```

Restrict the depth of the tree by 0 (global packages): 

```
npm list -g --depth 0	
```

Or 

```
npm list --global true --depth 0 
```

<a name="npm-ver"></a>
## npm Versioning

There is a special agreement to set versions of the packages and it's called **semantic versioning**. It is a specification where a version is represented by three numbers that mean the same thing for every developer.


* **Patch:** It is used for bug fixes
* **Minor:** New features but compatible with previous version
* **Major:** Introduce non-compatible features or change your project completely 
