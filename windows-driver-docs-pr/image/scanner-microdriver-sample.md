---
title: Scanner Microdriver Sample
author: windows-driver-content
description: Scanner Microdriver Sample
ms.assetid: 1b50d057-1585-4f2d-b3dc-0d5cad5533ba
ms.author: windowsdriverdev
ms.date: 04/20/2017
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-devices
---

# Scanner Microdriver Sample


## <a href="" id="ddk-scanner-microdriver-sample-si"></a>


The *microdrv* directory in the WDK contains a sample WIA microdriver for a scanner. A microdriver is easier to develop than a full WIA minidriver, but provides only basic functionality. See [Developing a WIA Scanner Driver](developing-a-wia-scanner-driver.md) for microdriver restrictions. This sample shows how to write a WIA microdriver for a flatbed scanner. This sample driver can be used as a starting point for your development, but your driver should access the scanner hardware through one of the kernel-mode drivers provided with Windows.

 

 




