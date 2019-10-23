

# ![Linux](../res/linux_med.png) Linux System Prerequisites [2.125.0 or above]

## Supported Distributions and Versions

We support the following OSes, a subset of [the ones .NET Core 2.1 supports](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md):

x64
  - Red Hat Enterprise Linux 6 (see note 1), 7
  - CentOS 6 (see note 1), 7
  - Oracle Linux 7
  - Fedora 30, 29
  - Debian 9
  - Ubuntu 18.04, Ubuntu 16.04
  - Linux Mint 18, 17
  - openSUSE 42.3 or later versions
  - SUSE Enterprise Linux (SLES) 12 SP2 or later versions

ARM32 (see note 2)
  - Debian 9
  - Ubuntu 18.04

> Notes:
> 1. Red Hat Enterprise Linux 6 and CentOS 6 require installing the specialized "rhel.6-x64" agent package
> 2. ARM instruction set [ARMv7](https://en.wikipedia.org/wiki/List_of_ARM_microarchitectures) or above is required, you can get your device's information by executing `uname -a`

## Install .Net Core 2.x Linux Dependencies

The `./config.sh` will check .Net Core 2.x dependencies during agent configuration.  
You might see something like this which indicate a dependency's missing.
```bash
./config.sh
    libunwind.so.8 => not found
    libunwind-x86_64.so.8 => not found
Dependencies is missing for Dotnet Core 2.1
Execute ./bin/installdependencies.sh to install any missing Dotnet Core 2.1 dependencies.
```
You can easily correct the problem by executing `./bin/installdependencies.sh`.  
The `installdependencies.sh` script should install all required dependencies on all supported Linux versions   
> Note: The `installdependencies.sh` script will try to use the default package management mechanism on your Linux flavor (ex. `yum`/`apt-get`/`apt`). You might need to deal with error coming from the package management mechanism related to your setup, like [#1353](https://github.com/Microsoft/vsts-agent/issues/1353)

## Git

If you use git, git >= 2.9.0 is a pre-requisite for Linux agents. To install an up-to-date version, please follow the instructions on [the Git website](https://git-scm.com/download/linux).

## Optionally Java if using TFVC

The agent distributes Team Explorer Everywhere.

But, if you are using TfsVc, install Oracle [Java SE Development Kit](http://www.oracle.com/technetwork/java/javaseproducts/downloads/index.html) (JDK) 1.6+. 
> Notes:  
> 1. Only install JRE is not sufficient.  
> 2. Don't use OpenJDK, use Oracle JDK.  

## [More .Net Core Prerequisites Information](https://docs.microsoft.com/en-us/dotnet/core/linux-prerequisites?tabs=netcore2x)
