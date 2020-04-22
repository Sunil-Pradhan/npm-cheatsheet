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

Install a package:


```
npm install <package name> --save-dev 
```

Example:

```
npm install lodash --save-dev 
```





Install as package as devDependency
