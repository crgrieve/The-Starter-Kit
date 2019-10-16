# 7.6-Starter-Kit

This Github project is used to manage the final build of the Starter Kit and is _not_ meant to be used as the Starter Kit content source.

_TODO_: We need to merge this repo: https://github.com/umbraco/Starterkit-TheUmbracoCommunity into this one and remove the CSS/JS one; they should exist in this one only.

You can find the Starter Kit as the default option in Umbraco 7.6.4+, as well as in the package repository on Our Umbraco.

Default Back Office user is:

* Email: mail@me.com
* Password: 1234567890

Get in touch if you wish to have access to this Umbraco Cloud project, which contains the master content for the Starter Kit:
https://umbraco-starter-kit.s1.umbraco.io

Alternatively, if you are doing development for the Starter Kit, you can launch the website project contained in this repo.

# Building the package

The build script is: /build/build.ps1 
Run it in the powershell cli: `.\build\build.ps1`

The build number is located in the `/build/build.xml` file.

The package output will be `/build/Releases/(VersionNumber)/Umbraco.SampleSite_4.0.0.zip` (but this should be the correct version you are building!)

# Maintaining the package

If changes are made to the package, the package manifest file will need to be updated:

* Save the package in the back office - this will update the /App_Data/packages/created/createdPackages.config
* Publish the package in the back office and press the download button to download the .zip file
* Open the zip file and find the package.xml file. Copy its contents to the /build/packageManifest.xml file. Alternatively, you can manually edit the /build/packageManifest.xml file, if you know what needs to be changed.

**Important!** You must manually include any cshtml files that are used by macros, just selecting the macro isn't enough. This is due to how the 
powershell build process works (this is not normally needed for creating packages normally in the back office)