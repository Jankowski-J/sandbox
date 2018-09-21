---
title: Azure Storage SDK for Unreal Engine
description: Azure Storage SDK for Unreal Engine
author: BrianPeek
manager: timheuer
keywords: unreal, azure, storage
ms.topic: article
ms.date: 9/12/2018
ms.author: brpeek
---
# Azure Storage SDK for Unreal Engine

[!include[](../../includes/header.md)]

> [!IMPORTANT]
> This is an experimental Unreal Engine SDK for Azure Storage.  As such, please note that this SDK is not supported and is not provided by the Azure Storage team.  If you run into problems, please let us know using the [GitHub Issues](https://github.com/BrianPeek/TODO) page for this fork.

[![Get the source](../../media/buttons/source2.png)](https://github.com/BrianPeek/TODO)
[![Try it now](../../media/buttons/try2.png)](https://aka.ms/azstorage-unitysdkTODO)

## Requirements

* [Unreal Engine 4.18 (or greater)](https://unrealengine.com/)
  * Previous versions may work but have not been tested.
* [An Azure Storage account (Sign up for free!)](https://aka.ms/azfreegamedev)

## Compatibility

This plugin contains builds of the Azure Storage SDK for Win32 and Win64.  Other platforms will not work.

## Information

The plugin contains the [Azure Storage SDK for C++](TODO) compiled as static libs along with required dependencies.  These libs will be linked against the game when building the project.  There is no specific Unreal API, so you can use the Storage SDK as you would from any other application.  For more information, please see the [Azure Storage docs](TODO).

* [Table](https://docs.microsoft.com/azure/cosmos-db/table-storage-how-to-use-c-plus)
* [Blob](https://docs.microsoft.com/azure/storage/blobs/storage-c-plus-plus-how-to-use-blobs)
* [File](https://docs.microsoft.com/azure/storage/files/storage-c-plus-plus-how-to-use-files)
* [Queue](https://docs.microsoft.com/azure/storage/queues/storage-c-plus-plus-how-to-use-queues)

## Add the Plugin

To add the Azure Storage SDK to your Unreal project, do the following:

1. Download the Plugin package and unzip.
1. Copy the AzureStorage directory from the archive to the Plugins directory in your project.
1. Add the `AzureStorage` module to your game's `PrivateDependencyModuleNames` list by editing the *\*.Build.cs* file for your project:

   ```csharp
   PrivateDependencyModuleNames.AddRange(new string[] { "AzureStorage" });
   ```

> [!NOTE]
> If you are using a non-default Visual C++ compiler, please modify the *AzureStorage.Build.cs* build script.

With the above in place, you should now be able to follow the generic C++ instructions listed above to connect to and use the Azure Storage service.

## Try the Sample

We created a sample using the Unreal puzzle game template which updates Table Storage for every box clicked.  To learn more, see the [sample]().

## How It's Made

If you want to compile this for yourself and create your own plugin, here's how we created this:

1. Clone the [Vcpkg project](https://github.com/Microsoft/vcpkg).
1. When complete, run the `bootstrap-vcpkg.bat` script located in the root directory.
1. Edit the *triplets\x64-windows.cmake* and *triplets\x86-windows.cmake* files to change the last line from `set(VCPKG_LIBRARY_LINKAGE dynamic)` to `set(VCPKG_LIBRARY_LINKAGE static)`.
1. Run vcpkg to build the libraries: `vcpkg install azure-storage-cpp:x64-windows` and `vcpkg install azure-storage-cpp:x86-windows`.
1. Copy the following files to the plugin's Binaries\ThirdParty\Win64 directory:
   * packages\azure-storage-cpp_x64-windows\lib\wastorage.lib
   * packages\cpprestsdk_x64-windows\lib\cpprest_2_10.lib
   * packages\zlib_x64-windows\lib\zlib.lib
   * packages\openssl-windows_x64-windows\lib\libeay32.lib
   * packages\openssl-windows_x64-windows\lib\ssleay32.lib
   * packages\boost-system_x64-windowss\lib\boost_system-vc140-mt.lib
1. Copy the following files to the plugin's Binaries\ThirdParty\Win32 directory:
   * packages\azure-storage-cpp_x86-windows\lib\wastorage.lib
   * packages\cpprestsdk_x86-windows\lib\cpprest_2_10.lib
   * packages\zlib_x86-windows\lib\zlib.lib
   * packages\openssl-windows_x86-windows\lib\libeay32.lib
   * packages\openssl-windows_x86-windows\lib\ssleay32.lib
   * packages\boost-system_x86-windowss\lib\boost_system-vc140-mt.lib
1. Copy the following directories to the plugin's Source\Public directory:
   * packages\azure-storage-cpp_x64-windows\include\was
   * packages\azure-storage-cpp_x64-windows\include\wascore
   * packages\cpprestsdk_x64-windows\include\cpprest
   * packages\cpprestsdk_x64-windows\include\pplx

## Cosmos DB Table API

[Cosmos DB](https://docs.microsoft.com/en-us/azure/cosmos-db/introduction) is Microsoft's globally distributed, multi-model database. One of the data models available for Cosmos DB is [Table API](https://docs.microsoft.com/en-us/azure/cosmos-db/table-introduction). Applications written for Azure Table storage can migrate to Azure Cosmos DB by using the Table API with no code changes and take advantage of premium capabilities. If you have a Cosmos DB database, you can use the Table Storage client SDK we provide to access it from your Unreal Engine game. Check the instructions [here](https://docs.microsoft.com/en-us/azure/cosmos-db/create-table-dotnet#update-your-connection-string) on how to find out your connection string.

## Next Steps

* [Azure Storage Docs](https://aka.ms/TODO)
