---
title: Azure Storage SDK for Unreal Engine
description: Azure Storage SDK for Unreal Engine
author: BrianPeek
manager: timheuer
keywords: unreal, azure, storage
ms.topic: article
ms.date: 9/12/2018
ms.author: brpeek
#ms.devlang: 
#ms.prod:
#ms.technology:
#ms.service:
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

The plugin contains the Azure Storage SDK for C++ compiled as static libs along with required dependencies.  These libs will be linked against the game you're building your project.  There is no specific API or procedure for use with Unreal.  For more information, please see the standard Azure Storage docs on how to use the SDK and service.

* Table
* Blob
* File
* Queue

## Add the Plugin

To add the Azure Storage SDK to your project, do the following:

1. download
1. add module
1. write code

## Try the Sample

We created a sample using the Unreal puzzle game template which updates Table Storage for every box clicked.  To learn more, see the sample.

## How It's Made

If you want to compile this for yourself and create your own plugin, here's how we created this:

1. vcpkg
1. stuff
1. more stuff

## Cosmos DB Table API

[Cosmos DB](https://docs.microsoft.com/en-us/azure/cosmos-db/introduction) is Microsoft's globally distributed, multi-model database. One of the data models available for Cosmos DB is [Table API](https://docs.microsoft.com/en-us/azure/cosmos-db/table-introduction). Applications written for Azure Table storage can migrate to Azure Cosmos DB by using the Table API with no code changes and take advantage of premium capabilities. If you have a Cosmos DB database, you can use the Table Storage client SDK we provide to access it from your Unreal Engine game. Check the instructions [here](https://docs.microsoft.com/en-us/azure/cosmos-db/create-table-dotnet#update-your-connection-string) on how to find out your connection string.

## Next Steps

* [Azure Storage Docs](https://aka.ms/TODO)
