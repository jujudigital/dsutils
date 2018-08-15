# dsutils

A small suite of utility scripts to help with day to day structured development of DroidScript (DS) projects.

# Changes since last release
Refer to the [change log](./CHANGELOG.md)

# Import/Export SPK scripts
DS SPKs are essentially zip archives and if they've been exported from DS then they are structured like this:

```
ProjectName.spk
    |-[ProjectName]
        |-ProjectName.js.txt
        |-AnotherScript.js.txt
        .
        .
        .
        |-LastFile.js.txt
```

Note the .txt extensions added to permit email sharing.

Personally I like to add some structure around my projects and pop them into Git repos, so having a means to easily import and export them to and from my project space is really helpful.


# importspk
This little CLI utility unpacks the SPK archive and ipmorts in into the relevant source folder in your structured repo based project.

## Installation
To use as a CLI utility then add the script to your `/usr/bin` directory to make it available anywhere in your filesystem.

## Example
```
importspk <ProjectName> </path/to/ProjectName.spk> </path/to/target/directory/>

```
## Adhoc use
If you don't want to install it then you can use it on an adhoc like this:
```
bash /path/to/importspk <ProjectName> /path/to/ProjectName.spk /path/to/ProjectName/src/
```


# exportspk
I use this one for exporting an SPK from my Git repos. It performs a git archive operation and creates an SPK with the name given from the src folder on a given branch.

I normally include this script in my repo project under a ./build folder. It will export the resulting SPK to a ./dist folder.

```
bash /path/to/exportspk </path/to/src> <ProjectName> < gitBranchName>
```

# exportplugin
If you're developing JavaScript only plugins for DS then they are exported to a zip. This is a modifed version of _exportspk_.

Like the SPK exporter I normally include this script in my repo project under a ./build folder. It will export the resulting SPK to a ./dist folder.

## usage
```
bash /path/to/exportspk </path/to/src> <PluginName> <gitBranchName>
```
