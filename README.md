<p align="center">
  <img width="480" height="230" src="/img/npm-logo.png">
</p>

<h1 align="center">npm Cheat Sheet</h1>

<p align="center">
A list of terminal commands and flags to help use npm. 
</p>

## Table of Contents

- [Basic npm commands](#basic-command)
- [Package creation](#Pakg-cr)
- [Package management](#Pakg-magt)
- [List packages](#list-packg)
- [npm versioning](#npm-ver)
- [Updating Packages](#update-packg)
- [NPM Prune](#npm-prune)
- [Dependencies and Development Dependencies](#npm-dep-dev)
- [Exploring package information and versions](#npm-pkg-ver)
- [Configure NPM](#npm-config)
- [NPM Script](#npm-script)
- [Custom NPM scripts](#npm-custom-script)
- [Resources](#npm-resources)

<a name="basic-command"></a>

## Basic npm commands

Check version number of npm:

```
npm -version
```

Or use shorthand:

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

Read documentation of any specific package online (official):

```
npm docs <package>
```

Example:

```
npm docs lodash
```

Update npm to latest version:

```
npm install npm@latest -g
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

Or use shorthand:

```
npm init --y
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

**package.json file:**

**Package name -** If you plan to publish your package, the most important things in your package.json are the name and version fields as they will be required. The name and version together form an identifier that is assumed to be completely unique.

Changes to the package should come along with changes to the version. If you do not plan to publish your package, the name and version fields are optional.

**Rules:**

- The name must be less than or equal to 214 characters. This includes the scope for scoped packages.
- The name can not start with a dot or an underscore.
- New packages must not have uppercase letters in the name
- The name ends up being part of a URL, an argument on the command line, and a folder name. Therefore, the name can’t contain any non-URL-safe characters.

**Version -** Version number of your package.

**Description -** It’s a string. This helps people discover your package, as it’s listed in npm search.

**Entry point -** We write a file which includes the main logic of the package/module.

**Test command -** Write test tool name.

**Git repository -** Address of git repo.

**Keywords -** It’s an array of strings. This helps people discover your package as it’s listed in npm search.

**Author -** Name of Author.

**License -** You should specify a license for your package so that people know how they are permitted to use it, and any restrictions you are placing on it.

 <hr>

<a name="Pakg-magt"></a>

## Package management

Install everything in package.json:

```
npm install
```

Or use shorthand:

```
npm i
```

Install a package:

```
npm install <package name>
```

Or use shorthand:

```
npm i <package name>
```

Example:

```
npm install lodash
```

Install a package as devDependency:

```
npm install <package name> --save-dev
```

Or use shorthand:

```
npm install -D <package name>
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

Install a package based on its tag:

```
npm install <package name>@<tag> --save-dev
```

Example:

```
npm install lodash@latest --save-dev
```

Install a package to specific version:

```
npm install <package name>@<version> --save-dev
```

Example:

```
npm install lodash@2.1.1 --save-dev
```

Install a package to exact specific version:

```
npm install <package name>@<version> --save-exact
```

Example:

```
npm install lodash@2.4.1 --save-exact
```

**Flags:**

**-P :** Production (--save-prod)

**-D :** devDependencies (--save-dev)

**-O :** Optional (--save-optional)

**-E :** Save exact

**-g :** Global

**-S :** Save

**--no-save:** Prevents saving to dependencies

<hr>

<a name="list-packg"></a>

## List packages

List locally installed packages (includes all dependencies):

```
npm list
```

Or use shorthand:

```
npm ls
```

Restrict the depth of the tree by 1:

```
npm list --depth 1
```

:bulb: **NOTE:** _It gives you only immediate dependencies of the packages._

<br>
Restrict the depth of the tree by 0:

```
npm list --depth 0
```

:bulb: **NOTE:** _It gives you the list of all the packages and no dependencies for that particular package._

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

- **Patch:** It is used for bug fixes
- **Minor:** New features but compatible with previous version
- **Major:** Introduce non-compatible features or change your project completely

**Versioning Table**

| Parameter           | Release Version |
| ------------------- | --------------- |
| Exact version       | 5.21.17         |
| Greater than        | >5.21.1         |
| Compatible changes  | ^5.21.8         |
| Minor-level changes | ~5.21.8         |

**Version specification in package.json file (helpful when using `npm install` command)**

**Caret (^) symbol:** Stick to the given major version number but when run `npm install` retrieve the latest minor and patch version.

Example:

![npm-caret-symbol](/img/npm-caret-symbol.png)

**Tilde (~) symbol:** It means, leave the major version and minor version as it is but retrieve the latest version of patch number when run `npm install` command.

Example:

![npm-tilde-symbol](/img/npm-tilde-symbol.png)

**Asterisk (\*) symbol:** Let's say even if there is a change in the major version number of a package but you want the latest one. In this case you will use an asterisk symbol.

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

**What is the difference between package.json and package-lock.json?**

![npm-package.json-package-lock.json](/img/npm-package.json-package-lock.json.png)

When you install any package in your project by executing the command

```
npm install <package-name> --save
```

Then it will install the exact latest version of that package in your project and save the dependency in package.json with a carat (^) sign.

Like, if the current version of a package is 5.2.3 then the installed version will be 5.2.3 and the saved dependency will be ^5.2.3.

Carat (^) means it will support any higher version with major version 5 like 5.3.1 and so on. **Here, package-lock.json is created for locking the dependency with the installed version.**

**Purpose of package-lock.json:**

To avoid differences in installed dependencies on different environments and to generate the same results on every environment you should use the package-lock.json file to install dependencies.

Ideally, this file should be on your source control with the package.json file so when you or any other user will clone the project and run the command `npm i`, it will install the exact same version saved in package-lock.json file and you will able to generate the same results as you developed with that particular package.

**Why should you commit package-lock.json with your project source code?**

During deployment, when you again run `npm i` with the same package.json file without the package-lock.json, the installed package might have a higher version now from what you had intended.

Now, what if you wanted to have that particular version for your dependency during deployment which you used at the time of development. This is the need of creating a package-lock.json file and keeping it with the source code. This file is created with the details of the specific version installed in your project.

<hr>

<a name="update-packg"></a>

## Updating Packages

Updates all listed packages to the latest release version:

```
npm update
```

Update specific package:

```
npm update <package> --save
```

Example:

```
npm update lodash --save
```

Update only dev dependencies:

```
npm update --dev --save-dev
```

Update all the packages globally:

```
npm update -g
```

Update specific package globally:

```
npm update -g <package>
```

Example:

```
npm update -g lodash
```

<hr>

<a name="npm-prune"></a>

## NPM Prune

Remove all unused packages(It remove modules not listed in package.json):

```
npm prune
```

More info: [@stackoverflow](https://stackoverflow.com/questions/21417014/npm-command-to-uninstall-or-prune-unused-packages-in-node-js)

<hr>

<a name="npm-dep-dev"></a>

## Dependencies and Development Dependencies

**Dependencies:**

- Installed using `npm install` or `npm install <package>`
- If package A is installed using `npm install <packageA>` and it has dependency on package B then package B will be also installed along with it’s dependencies.

**Development Dependencies:**

- Installed using `npm install`
- Not installed using `npm install -- production`
- If package A is installed using `npm install <packageA>` and it has devDependency on package B than package B will NOT be installed.

Install a package as devDependency:

```
npm install <package name> --save-dev
```

Or use shorthand:

```
npm install -D <package name>
```

Example:

```
npm install lodash --save-dev
```

package.json file contains dependencies and development dependencies. If you execute the `npm install` command then all those dependencies will be installed in case node_modules folder is missing.

On the other hand, if you install with the `production` flag then it will only install dependencies.

```
npm install --production
```

But if the package has its own development dependencies they will be never installed in your project.

:bulb: **TIP:** **Do you add packages as dependency or dev-dependancy?**

The answer is it depends: It depends on the kind of application you are developing.

If you build just a standalone application for the browser you should add all packages as development dependencies. Because Browser does not understand dependencies or dev-dependencies.

But if you build a public package and other packages depend on your package and if you will use some functions from external packages in your compiled code then you will need to add those external packages as dependencies.

All other packages need to go into development dependencies in your project.

<hr>

<a name="npm-pkg-ver"></a>

## Exploring package information and versions

Print information about package:

```
npm view <package>
```

Example:

```
npm view lodash
```

![npm-lodash-version](/img/npm-lodash-version.png)

Print information about package (all version):

```
npm view <package> versions
```

Example:

```
npm view lodash versions
```

![npm-lodash-version-all](/img/npm-lodash-version-all.png)

<hr>

<a name="npm-config"></a>

## Configure NPM

To configure npm:

```
npm config
```

![npm-config](/img/npm-config.png)

_npm gets its config settings from the command line, environment variables, npmrc files, and in some cases, the package.json file._

Display basic configuration list:

```
npm config list
```

Display complete configuration list:

```
npm config list -l
```

Sets the config key to the value:

```
npm config set <key> <value>
```

_If value is omitted, then it sets it to **true**_

**Example:**

Set default author name for all new package creation:

```
npm config set init.author.name ‘your-name’
```

Verify by: `npm init -y`

Get default configuration value:

```
npm config get
```

**Example:**

Get value of default author name:

```
npm config get init.author.name
```

Edit configuration file:

```
npm config edit
```

It will opens up configuration file;

![npm-npmrc-file](/img/npm-npmrc-file.png)

If you see carefully all new edit which you have made it reflects on top of the list.If you want to go with npm inbuilt default values then remove it and save the file.

Edit global configuration file with global values:

```
npm config edit --global
```

Delete configuration value:

```
npm config delete
```

Example:

```
npm config delete init.author.name
```

<hr>

<a name="npm-script"></a>

## NPM Script

NPM scripts allow you easily perform certain operations to execute commands or execute files using npm command.

Popular npm script command:

- `npm start`
- `npm run`
- `npm built`

**npm start:**

**npm start -** This runs an arbitrary command specified in the package’s **“Start”** property of its **“scripts”** object. If no **“start”** property is specified on the **“script”** object, it will run node server.js.

Project directory:

![npm-script-project-directory](/img/npm-script-project-directory.png)

Basically what you would do is to execute node and run index.js

![npm-start-command-hello-sunil](/img/npm-start-command-hello-sunil.png)

So let's write a script that is going to do this for us. Remove the following line from package.json file:

![npm-start-script](/img/npm-start-script.png)

Now add the following line:

![npm-start-script-custom](/img/npm-start-script-custom.png)

Now run `npm start` command:

![npm-start-output](/img/npm-start-output.png)

This comes in handy when you are developing a project. Let's say the project entry point is index.js.

So by having a start command the user doesn't have to worry about what command to run. So someone downloads your project from github and they run - `npm start`.

Your project will automatically execute as you have intended.

Other popular npm inbuilt script command are:

- `npm stop`
- `npm restart`
- `npm test`
- `npm prestart`
- `npm poststart`

**npm prestart:**

Project directory:

![npm-project-folder-npm-prestart](/img/npm-project-folder-npm-prestart.png)

Install colors package as devDependency:

```
npm install colors --save-dev
```

![npm-colors-package](/img/npm-colors-package.png)

Edit package.json file for prestart:

![npm-edit-package-colors](/img/npm-edit-package-colors.png)

Now test prestart script by typing: `npm start`:

![npm-prestart-script-test](/img/npm-prestart-script-test.png)

Edit prestart.js file to see output in red color:

![prestart-js-edit-for-red-color](/img/prestart-js-edit-for-red-color.png)

Now see the final output by typing `npm start`:

![prestart-js-ourput-red-color](/img/prestart-js-ourput-red-color.png)

<hr>

<a name="npm-custom-script"></a>

## Custom NPM scripts

Executes certain script:

```
npm run <script>
```

As alias of:

```
npm run-script <script>
```

**npm run:**

Project directory:

![npm-project-directory-custom-js](/img/npm-project-directory-custom-js.png)

Edit package.json file for custom script:

![edit-package-json-file-for-custom-script](/img/edit-package-json-file-for-custom-script.png)

Now test custom script by typing: `npm start`:

![npm-custom-script](/img/npm-custom-script.png)


**Run NPM scripts simultaneously:**

Install npm-run-all package: 

```
npm i -D npm-run-all
```

![npm-run-all-package-install](/img/npm-run-all-package-install.png)

Project directory:

![npm-run-all-project-directory](/img/npm-run-all-project-directory.png)




<hr>

<a name="npm-resources "></a>

##### Resources

NPM Shorthands: [npmjs-docs](https://docs.npmjs.com/misc/config#shorthands-and-other-cli-niceties)
