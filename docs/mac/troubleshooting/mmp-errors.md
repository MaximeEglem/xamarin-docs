---
title: "Xamarin.Mac error messages (mmp)"
description: "An errors reference guide for mmp."
ms.topic: article
ms.prod: xamarin
ms.assetid: 5B26339F-A202-4E41-9229-D0BC9E77868E
ms.technology: xamarin-mac
author: bradumbaugh
ms.author: brumbaug
ms.date: 03/27/2018
---

# Xamarin.Mac error messages (mmp)

## MM0xxx: mmp error messages

E.g. parameters, environment, missing tools.

<a name="MM0000" />

#### MM0000: Unexpected error - Please file a bug report at http://bugzilla.xamarin.com

An unexpected error condition occurred. Please [file a bug report](https://bugzilla.xamarin.com/enter_bug.cgi?product=Xamarin.Mac) with as much information as possible, including:

* Full build logs, with maximum verbosity (e.g. `-v -v -v -v` in the **Additional mmp arguments**);
* A minimal test case that reproduce the error; and
* All version informations

The easiest way to get exact version information is to use the **Xamarin Studio** menu, **About Xamarin Studio** item, **Show Details** button and copy/paste the version informations (you can use the **Copy Information** button).

<a name="MM0001" />

#### MM0001: This version of Xamarin.Mac requires Mono {0} (the current Mono version is {1}). Please update the Mono.framework from http://mono-project.com/Downloads

<a name="MM0003" />

#### MM0003: Application name '{0}.exe' conflicts with an SDK or product assembly (.dll) name.

<a name="MM0007" />

#### MM0007: The root assembly '{0}' does not exist

<a name="MM0008" />

#### MM0008: You should provide one root assembly only, found {0} assemblies: '{1}'

<a name="MM0010" />

#### MM0010: Could not parse the command line arguments: {0}

<!-- 0013 is unused -->

<a name="MM0016" />

#### MM0016: The option '{0}' has been deprecated.

<a name="MM0017" />

#### MM0017: You should provide a root assembly

<a name="MM0018" />

#### MM0018: Unknown command line argument: '{0}'

<a name="MM0020" />

#### MM0020: The valid options for '{0}' are '{1}'.

<a name="MM0023" />

#### MM0023: Application name '{0}.exe' conflicts with another user assembly.

<a name="MM0026" />

#### MM0026: Could not parse the command line argument '{0}': {1}

<a name="MM0043" />

#### MM0043: The Boehm garbage collector is not supported. The SGen garbage collector has been selected instead.

<a name="MM0050" />

#### MM0050: You cannot provide a root assembly if --no-root-assembly is passed.

<a name="MM0051" />

#### MM0051: An output directory (--output) is required if --no-root-assembly is passed.

<a name="MM0053" />

#### MM0053: Cannot disable new refcount with the Unified API.

<a name="MM0056" />

#### MM0056: Cannot find Xcode in any of our default locations. Please install Xcode, or pass a custom path using --sdkroot=<path>

<a name="MM0059" />

#### MM0059: Could not find the currently selected Xcode on the system: {0};

<a name="MM0060" />

#### MM0060: Could not find the currently selected Xcode on the system. 'xcode-select --print-path' returned '{0}', but that directory does not exist.

<a name="MM0068" />

#### MM0068: Invalid value for target framework: {0}.

<a name="MM0071" />

#### MM0071: Unknown platform: *. This usually indicates a bug in Xamarin.Mac; please file a bug report at https://bugzilla.xamarin.com with a test case.

This usually indicates a bug in Xamarin.Mac; please file a bug report at [https://bugzilla.xamarin.com](https://bugzilla.xamarin.com/enter_bug.cgi?product=Xamarin.Mac) with a test case.

<a name="MM0079" />

#### MM0079: Internal Error - No executable was copied into the app bundle. Please contact 'support@xamarin.com'

<a name="MM0080" />

#### MM0080: Disabling NewRefCount, --new-refcount:false, is deprecated.

<!-- 0088 used by mtouch -->
<!-- 0089 used by mtouch -->

<a name="MM0091" />

#### MM0091: This version of Xamarin.Mac requires the * SDK (shipped with Xcode *). Either upgrade Xcode to get the required header files or use the dynamic registrar or set the managed linker behaviour to Link Platform or Link Framework SDKs Only (to try to avoid the new APIs).

Xamarin.Mac requires the header files, from the SDK version specified in the error message, to build your application with the static registrar.. The recommended way to fix this error is to upgrade Xcode to get the required SDK, this will include all the required header files. If you have multiple versions of Xcode installed, or want to use an Xcode in a non-default location, make sure to set the correct Xcode location in your IDE's preferences.

One potential, alternative solution, is to enable the managed linker. This will remove unused API including, in most cases, the new API where the header files are missing (or incomplete). However this will not work if your project uses API that was introduced in a newer SDK than the one your Xcode provides.

A second potential, alternative solution, is use the dynamic registrar instead. This will impose a startup cost by dynamically registering types but remove the header file requirement. 

A last-straw solution would be to use an older version of Xamarin.Mac, one that supports the SDK your project requires.

<a name="MM0097" />

#### MM0097: machine.config file '{0}' can not be found.

<a name="MM0098" />

#### MM0098: AOT compilation is only available on Unified

<a name="MM0099" />

#### MM0099: Internal error {0}. Please file a bug report with a test case (http://bugzilla.xamarin.com).

<a name="MM0114" />

#### MM0114: Hybrid AOT compilation requires all assemblies to be AOT compiled.

## MM1xxx: file copy / symlinks (project related)

<a name="MM1034" />

#### MM1034: Could not create symlink '{file}' -> '{target}': error {number}

### MM14xx: Product assemblies

<a name="MM1401" />

#### MM1401: The required '{0}' assembly is missing from the references

<a name="MM1402" />

#### MM1402: The assembly '{0}' is not compatible with this tool

<a name="MM1403" />

#### MM1403: {0} '{1}' could not be found. Target framework '{0}' is unusable to package the application.

<a name="MM1404" />

#### MM1404: Target framework '{0}' is invalid.

<a name="MM1405" />

#### MM1405: useFullXamMacFramework must always target framework .NET 4.5, not '{0}' which is invalid

<a name="MM1406" />

#### MM1406: Target framework '{0}' is invalid when targetting Xamarin.Mac 4.5 .NET framwork.

<a name="MM1407" />

#### MM1407: Mismatch between Xamarin.Mac reference '{0}' and target framework selected '{1}'.

### MM15xx: Assembly gathering (not requiring linker) errors

<a name="MM1501" />

#### MM1501: Can not resolve reference: {0}

### MachO.cs

<a name="MM1600" />

#### MM1600: Not a Mach-O dynamic library (unknown header '0x{0}'): {1}.

<a name="MM1601" />

#### MM1601: Not a static library (unknown header '{0}'): {1}.

<a name="MM1602" />

#### MM1602: Not a Mach-O dynamic library (unknown header '0x{0}'): {1}.

<a name="MM1603" />

#### MM1603: Unknown format for fat entry at position {0} in {1}.

<a name="MM1604" />

#### MM1604: File of type {0} is not a MachO file ({1}).

## MM2xxx: Linker

### MM20xx: Linker (general) errors

<a name="MM2001" />

#### MM2001: Could not link assemblies

<a name="MM2002" />

#### MM2002: Can not resolve reference: {0}

<a name="MM2003" />

#### MM2003: Option '{0}' will be ignored since linking is disabled

<a name="MM2004" />

#### MM2004: Extra linker definitions file '{0}' could not be located.

<a name="MM2005" />

#### MM2005: Definitions from '{0}' could not be parsed.

<a name="MM2006" />

#### MM2006: Native library '{0}' was referenced but could not be found.

<a name="MM2007" />

#### MM2007: Xamarin.Mac Unified API against a full .NET profile does not support linking. Pass the -nolink flag.

<a name="MM2009" />

#### MM2009: Referenced by {0}.{1}     ** This message is related to MM2006 **

<a name="MM2010" />

#### MM2010: Unknown HttpMessageHandler `{0}`. Valid values are HttpClientHandler (default), CFNetworkHandler or NSUrlSessionHandler

<a name="MM2011" />

#### MM2011: Unknown TLSProvider `{0}.  Valid values are default or appletls

<a name="MM2012" />

#### MM2012: Only first {0} of {1} "Referenced by" warnings shown. ** This message related to 2009 **

<a name="MM2013" />

#### MM2013: Failed to resolve the reference to "{0}", referenced in "{1}". The app will not include the referenced assembly, and may fail at runtime.

<a name="MM2014" />

#### MM2014: Xamarin.Mac Extensions do not support linking. Request for linking will be ignored. ** This message is obsolete in XM 3.6+ **

<!-- 2015 used by mtouch -->

<a name="MM2016" />

#### MM2016: Invalid TlsProvider `{0}` option. The only valid value `{1}` will be used.

<a name="MM2017" />

#### MM2017: Could not process XML description: {0}

<a name="MM202x" />

#### MM202x: Binding Optimizer failed processing `...`.

<a name="MM2100" />

#### MM2100: Xamarin.Mac Classic API does not support Platform Linking.

<a name="MM2103" />

#### MM2103: Error processing assembly '\*': *

An unexpected error occured when processing an assembly.

The assembly causing the issue is named in the error message. In order to fix this issue the assembly will need to be provided in a [bug report](https://bugzilla.xamarin.com) along with a complete build log with verbosity enabled (i.e. `-v -v -v -v` in the **Additional mtouch arguments**).

<a name="MM2104" />

#### MM2104: Unable to link assembly '{0}' as it is mixed-mode.

Mixed-mode assemblies can not be processed by the linker.

See https://msdn.microsoft.com/en-us/library/x0w2664k.aspx for more information on mixed-mode assemblies.

## MM3xxx: AOT

### MM30xx: AOT (general) errors

<a name="MM3001" />

#### MM3001: Could not AOT the assembly '{0}'

<!-- 3002 used by mtouch -->
<!-- 3003 used by mtouch -->
<!-- 3004 used by mtouch -->
<!-- 3005 used by mtouch -->
<!-- 3006 used by mtouch -->
<!-- 3007 used by mtouch -->
<!-- 3008 used by mtouch -->

<a name="MM3009" />

#### MM3009: AOT of '{0}' was requested but was not found

<a name="MM3010" />

#### MM3010: Exclusion of AOT of '{0}' was requested but was not found

## MM4xxx: code generation

### MM40xx: driver.m

<a name="MM4001" />

#### MM4001: The main template could not be expanded to `{0}`.

### MM41xx: registrar

<a name="MM4134" />

#### MM4134: Your application is using the '{0}' framework, which isn't included in the MacOS SDK you're using to build your app (this framework was introduced in OSX {2}, while you're building with the MacOS {1} SDK.) This configuration is not supported with the static registrar (pass --registrar:dynamic as an additional mmp argument in your project's Mac Build option to select). Alternatively select a newer SDK in your app's Mac Build options.

## MM5xxx: GCC and toolchain

### MM51xx: compilation

<a name="MM5101" />

#### MM5101: Missing '{0}' compiler. Please install Xcode 'Command-Line Tools' component.

<!-- 5102 used by mtouch -->

<a name="MM5103" />

#### MM5103: Failed to compile. Error code - {0}. Please file a bug report at http://bugzilla.xamarin.com

<!-- 5104 used by mtouch -->

### MM52xx: linking

<a name="MM5202" />

#### MM5202: Mono.framework MDK is missing. Please install the MDK for your Mono.framework version from http://mono-project.com/Downloads

<a name="MM5203" />

#### MM5203: Can't find libxammac.a, likely because of a corrupted Xamarin.Mac installation. Please reinstall Xamarin.Mac.

<a name="MM5204" />

#### MM5204: Invalid architecture. x86_64 is only supported on non-Classic profiles.

<a name="MM5205" />

#### MM5205: Invalid architecture '{0}'. Valid architectures are i386 and x86_64 (when --profile=mobile).

<a name="MM5218" />

#### MM5218: Can't ignore the dynamic symbol {symbol} (--ignore-dynamic-symbol={symbol}) because it was not detected as a dynamic symbol.

See the [equivalent mtouch warning](~/ios/troubleshooting/mtouch-errors.md#MT5218).

<!-- 5206 used by mtouch -->
<!-- 5207 used by mtouch -->
<!-- 5208 used by mtouch -->
<!-- 5209 used by mtouch -->
<!-- 5210 used by mtouch -->
<!-- 5211 used by mtouch -->
<!-- 5212 used by mtouch -->
<!-- 5213 used by mtouch -->
<!-- 5214 used by mtouch -->
<!-- 5215 used by mtouch -->
<!-- 5216 used by mtouch -->
<!-- 5217 used by mtouch -->

### MM53xx: other tools

<a name="MM5301" />

#### MM5301: pkg-config could not be found. Please install the Mono.framework from http://mono-project.com/Downloads

<!-- 5302 used by mtouch -->
<!-- 5303 used by mtouch -->
<!-- 5304 used by mtouch -->

<a name="MM5305" />

#### MM5305: Missing 'otool' tool. Please install Xcode 'Command-Line Tools' component

<a name="MM5306" />

#### MM5306: Missing dependencies. Please install Xcode 'Command-Line Tools' component

<a name="MM5308" />

#### MM5308: Xcode license agreement may not have been accepted.  Please launch Xcode.

<a name="MM5309" />

#### MM5309: Native linking failed with error code 1.  Check build log for details.

<a name="MM5310" />

#### MM5310: install_name_tool failed with an error code '{0}'. Check build log for details.

<!-- MM6xxx: mmp internal tools -->
<!-- MM7xxx: reserved -->

## MM8xxx: runtime

### MM800x: misc

<!-- 8000 used by mtouch -->
<!-- 8001 used by mtouch -->
<!-- 8002 used by mtouch -->
<!-- 8003 used by mtouch -->
<!-- 8004 used by mtouch -->
<!-- 8005 used by mtouch -->
<!-- 8006 used by mtouch -->
<!-- 8007 used by mtouch -->
<!-- 8008 used by mtouch -->
<!-- 8009 used by mtouch -->
<!-- 8010 used by mtouch -->
<!-- 8011 used by mtouch -->
<!-- 8012 used by mtouch -->
<!-- 8013 used by mtouch -->
<!-- 8014 used by mtouch -->
<!-- 8015 used by mtouch -->
<!-- 8016 used by mtouch -->

<a name="MM8017" />

#### MM8017: The Boehm garbage collector is not supported. Please use SGen instead.

