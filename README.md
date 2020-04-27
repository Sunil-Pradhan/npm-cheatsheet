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

<hr>

<a name="npm-ver"></a>
## NPM Versioning

There is a special agreement to set versions of the packages and it's called **semantic versioning**. It is a specification where a version is represented by three numbers that mean the same thing for every developer.

![npm-semantic versioning](/img/npm-semantic%20versioning.png)

* **Patch:** It is used for bug fixes
* **Minor:** New features but compatible with previous version
* **Major:** Introduce non-compatible features or change your project completely 

**Versioning Table**

Parameter | Release Version
------------ | -------------
Exact version          | 5.21.17
Greater than           | >5.21.1
Compatible changes     | ^5.21.8
Minor-level changes    | ~5.21.8


**Version specification in package.json file (helpful when using `npm install` command)**

**Caret (^) symbol:** Stick to the given major version number but when run `npm install` retrieve the latest minor and patch version.

Example: 

![npm-caret-symbol](/img/npm-caret-symbol.png)

**Tilde (~) symbol:** It means, leave the major version and minor version as it is but retrieve the latest version of patch number when run `npm  install` command.

Example: 

![npm-tilde-symbol](/img/npm-tilde-symbol.png)


**Asterisk (*) symbol:** Let's say even if there is a change in the major version number of a package but you want the latest one. In this case you will use an asterisk symbol. 

So, when you specify an asterisk symbol it is going to retrieve the latest version of the package irrespective of the major minor or patch version.

**Example:**

![npm-asterisk-symbol](/img/npm-asterisk-symbol.png)

**No symbol:** You can just have the specific version number in this case npm doesn't install a newer version even though it exists when you run `npm install`.

Example: 

![npm-no-symbol](/img/npm-no-symbol.png)




Install specific version of a package: 

```
npm install <package@version>
```

Example: 

```
npm install lodash@3.3.0 --save
```

Restrict major and minor version but use patch version to latest in a package: 

```
npm install <package@major.minor>
```

Example: 

```
npm install lodash@4.14 --save
```


Install package only with latest major version number: 


```
npm install <package@major>
```

Example: 

```
npm install lodash@4 --save
```


