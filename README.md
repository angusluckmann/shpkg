# shpkg

## General project information

Name: shpkg

Description: A simple package manager made out of linux shell scripts

Original Author: Angus Luckmann

License: MIT

## Use cases and benefits

This is a simple package manager entirely composed out of shell scripts.

Because it is written as a set of simple shell scripts (sh NOT bash), you can easily modify it and make it work for any purpose.

You can (with some restrictions) use it to:

- Manage dotfiles
- Manage wine-bottles
- Manage game-addons
- Maybe manage updates and software-installations on gentoo-installs
- Prototype potential next-level package-management concepts for linux
- Understand package-managers in popular linux distributions at a basic level
- Manage or any other kind of files on your hard-drive
- etc.

## Downsides

The package manager also has some downsides and weaknesses though. They include:

- Limited safety (the package manager might unwantedly delete importent files in case of untested edge cases or bugs, so backup your data!)
- Limited internet-support (it mostly works with offline-repos and so-called "repo-packs")
- Limited update capabilites (you have to manually uninstall and reinstall a package)
- No support for source-packages that can be compiled using the package-manager
- No support for more than one repository at once
- I might have forgotten something...

Besides that, it's a pretty solid and usable package manager

## General concept

The package manager generally works with 4 kinds of data:

- **Package files:** A package file is a simple file that holds data that can be installe
- **Repositories:** A package repository is a collection of package files combined with some information about them
- **Repopacks:** A repopack is a repository compressed into a single archive
- **Package database:** A simple folder containing information about the installed packages within a certain system or folder

**Note:** In common linux distributions, the dependencies of a package are saved in the package file. This package manager manages dependencies at the repo-level.

## Configuration

At the start of the file "shpkg" you find a bunch of configuration-options allowing you to configure the package managers behaviour:

- **TOOL_NAME:** The name of the main tool binary (by default "shpkg"). If you change the filename of the main binaries filename, change this variable with it.
- **TOOL_BINARY:** The name of the secondary tool binaries (by default "shpkg-add", "shpkg-del", "shpkg-help", etc.). If you change the filenames of these secondary files, make sure they all have the same name and change this variable with them as well.
- **TOOL_VERSION:** Change the version output of "shpkg --version" here
- **TOOL_DIR:** The directory containing the secondary tool files ((by default "shpkg-add", "shpkg-del", "shpkg-help", etc.). Defaults to an auto-detection of the main-tool-binaries-path. Don't change this variable unless you know what you are doing.
- **FILE_EXTENSIONS_PKG:** The file extension for package files without a dot (defaults to "pkf")
- **FILE_EXTENSIONS_REPO_PKG:** The file extension for repopacks without a dot (default to "rpk")
- **INSTALLROOT:** The place to install the contents of the used packages
- **PACKAGEDB_SUBFOLDER:** The subfolder within the $INSTALLROOT to hold the package database (see above)
- **PACKAGEDB:** Absolute path to the package database folder
- **REPODIR:** Folder for the main (and only) package repository.

That's it!

## Usage

**Warning: Do NOT call the package manager from another file than the main binary (shpkg).**

The usage of shpkg is simple.

1. Create a repository (or rename the folder "repo-example" to "repo")
2. Start using the "shpkg" tool
3. Get familiar with the whole thing
4. Start making custom modifications
5. Enjoy your custom-configured, personal package manager :)

## Contribution

I'm not that familiar with GitHubs contribution mechanics. But if you have good ideas or other contributions to make, feel free to contact me or feature this project somewhere.
