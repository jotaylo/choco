﻿# New Command (choco new)

Chocolatey will generate package specification files for a new package.

## Usage

    choco new <name> [<options/switches>] [<property=value> <propertyN=valueN>]

Possible properties to pass:
    packageversion
    maintainername
    maintainerrepo
    installertype
    url
    url64
    silentargs

**NOTE:** Starting in 0.9.10, you can pass arbitrary property value pairs
 through to templates. This really unlocks your ability to create
 packages automatically!

**NOTE:** [Chocolatey for Business](https://chocolatey.org/compare) can create complete packages by just
 pointing the new command to native installers!

**NOTE:** [Chocolatey for Business](https://chocolatey.org/compare) can also download and internalize remote
 resources from existing packages so that existing packages can be used 
 without being tied to the internet.
 This is called automatic recompile.

## Examples

    choco new bob
    choco new bob -a --version 1.2.0 maintainername="'This guy'"
    choco new bob silentargs="'/S'" url="'https://somewhere/out/there.msi'"
    choco new bob --outputdirectory Packages


## Options and Switches

**NOTE:** Options and switches apply to all items passed, so if you are
 running a command like install that allows installing multiple
 packages, and you use `--version=1.0.0`, it is going to look for and
 try to install version 1.0.0 of every package passed. So please split
 out multiple package calls when wanting to pass specific options.

Includes [[default options/switches|CommandsReference#default-options-and-switches]] (included below for completeness).

~~~

 -?, --help, -h
     Prints out the help menu.

 -d, --debug
     Debug - Show debug messaging.

 -v, --verbose
     Verbose - Show verbose messaging.

     --acceptlicense, --accept-license
     AcceptLicense - Accept license dialogs automatically. Reserved for 
       future use.

 -y, --yes, --confirm
     Confirm all prompts - Chooses affirmative answer instead of prompting. 
       Implies --accept-license

 -f, --force
     Force - force the behavior. Do not use force during normal operation - 
       it subverts some of the smart behavior for commands.

     --noop, --whatif, --what-if
     NoOp / WhatIf - Don't actually do anything.

 -r, --limitoutput, --limit-output
     LimitOutput - Limit the output to essential information

     --timeout, --execution-timeout=VALUE
     CommandExecutionTimeout (in seconds) - The time to allow a command to 
       finish before timing out. Overrides the default execution timeout in the 
       configuration of 2700 seconds.

 -c, --cache, --cachelocation, --cache-location=VALUE
     CacheLocation - Location for download cache, defaults to %TEMP% or value 
       in chocolatey.config file.

     --allowunofficial, --allow-unofficial, --allowunofficialbuild, --allow-unofficial-build
     AllowUnofficialBuild - When not using the official build you must set 
       this flag for choco to continue.

     --failstderr, --failonstderr, --fail-on-stderr, --fail-on-standard-error, --fail-on-error-output
     FailOnStandardError - Fail on standard error output (stderr), typically 
       received when running external commands during install providers. This 
       overrides the feature failOnStandardError.

     --use-system-powershell
     UseSystemPowerShell - Execute PowerShell using an external process 
       instead of the built-in PowerShell host. Should only be used when 
       internal host is failing. Available in 0.9.10+.

 -a, --auto, --automaticpackage
     AutomaticPackage - Generate automatic package instead of normal. 
       Defaults to false

 -t, --template, --template-name=VALUE
     TemplateName - Use a named template in 
       C:\ProgramData\chocolatey\templates\templatename instead of built-in 
       template. Available in 0.9.9.9+. Manage templates as packages in 0.9.10+.

     --name=VALUE
     Name [Required]- the name of the package. Can be passed as first 
       parameter without "--name=".

     --version=VALUE
     Version - the version of the package. Can also be passed as the property 
       PackageVersion=somevalue

     --maintainer=VALUE
     Maintainer - the name of the maintainer. Can also be passed as the 
       property MaintainerName=somevalue

     --outputdirectory=VALUE
     OutputDirectory - Specifies the directory for the created Chocolatey 
       package file. If not specified, uses the current directory. Available in 
       0.9.10+.

     --built-in, --built-in-template, --originaltemplate, --original-template, --use-original-template, --use-built-in-template
     BuiltInTemplate - Use the original built-in template instead of any 
       override. Available in 0.9.10+.

     --file, --url=VALUE
     Inspect a file (native installer, zip, patch/upgrade file, or remote url 
       to download first) to to completely create a package with proper silent 
       arguments! Can be 32-bit or 64-bit architecture.  Available in Business 
       editions only (licensed version 1.4.0+, url/zip starting in 1.6.0). See 
       https://chocolatey.org/docs/features-create-packages-from-installers 

     --file64, --url64=VALUE
     Optional - used when specifying both a 32-bit and a 64-bit file. Can be 
       an installer or a zip, or remote url to download. Available in Business 
       editions only (licensed version 1.6.0+).

     --keepremote, --originallocation, --original-location, --useoriginallocation, --use-original-location, --useoriginalfileslocation, --use-original-files-location
     Use Original Files Location - when using file or url, use the original 
       location in packaging. Available in Business editions only (licensed 
       version 1.6.0+).

     --checksum, --downloadchecksum, --download-checksum=VALUE
     Download Checksum - checksum to verify File/Url with. Defaults to empty. 
       Available in Business editions only (licensed version 1.7.0+).

     --checksum64, --checksumx64, --downloadchecksumx64, --download-checksum-x64=VALUE
     Download Checksum 64-bit - checksum to verify File64/Url64 with. 
       Defaults to empty. Available in Business editions only (licensed version 
       1.7.0+).

     --checksumtype, --checksum-type, --downloadchecksumtype, --download-checksum-type=VALUE
     Download Checksum Type - checksum type for File/Url (and optional 
       separate 64-bit files when specifying both). Used in conjunction with 
       Download Checksum and Download Checksum 64-bit. Available values are 
       'md5', 'sha1', 'sha256' or 'sha512'. Defaults to 'sha256'.  Available in 
       Business editions only (licensed version 1.7.0+).

     --pauseonerror, --pause-on-error
     Pause on Error - Pause when there is an error with creating the package. 
       Available in Business editions only (licensed version 1.7.0+).

     --buildpackage, --build-package
     Build Package - Attempt to compile the package after creating it. 
       Available in Business editions only (licensed version 1.7.0+).

~~~

[[Command Reference|CommandsReference]]


***NOTE:*** This documentation has been automatically generated from `choco new -h`. 

