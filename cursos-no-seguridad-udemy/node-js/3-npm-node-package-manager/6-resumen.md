# 6 - Resumen

* Every Node application has a package.json file that includes metadata about the

  application. This includes the name of the application, its version, dependencies,

  etc.

* We use NPM to download and install 3rd-party packages from NPM registry:
* All the installed packages and their dependencies are stored under

  node\_modules folders. This folder should be excluded from the source control.

* Node packages follow semantic versioning: major.minor.patch
* Useful NPM commands are:

  // Install a package

  **npm i** 

  // Install a specific version of a package

  **npm i &lt;packageName&gt;@**

  // ~~~~Install a package as a development dependency

  **npm i  —save-dev**

  // Uninstall a package

  **npm un** 

  // List installed packages

  **npm list —depth=0**

  // View outdated packages

  **npm outdated**

  // Update packages

  **npm update**

* To install/uninstall packages globally, use -g flag.



