---
title: Freeing Resources
author: windows-driver-content
description: User-mode applications and kernel-mode drivers that are HID clients should always free any resources that are no longer required.
ms.assetid: 19cbc443-cc25-448f-92dc-d9586c1fd5a7
keywords:
- collections WDK HID , free resources
- HID collections WDK , free resources
- freeing HID resources
ms.author: windowsdriverdev
ms.date: 04/20/2017
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-devices
---

# Freeing Resources


User-mode applications and kernel-mode drivers that are HID clients should always free any resources that are no longer required.

## <a href="" id="ddk-freeing-resources-kg"></a>


For example, a user-mode application must call [**SetupDiDestroyDeviceInfoList**](https://msdn.microsoft.com/library/windows/hardware/ff550996) with the handle to the device list that it obtained from [**SetupDiGetClassDevs**](https://msdn.microsoft.com/library/windows/hardware/ff551069) after completing its initialization and connection operations for a HIDClass device. Failure to call **SetupDiDestroyDeviceInfoList** causes a memory leak.

 

 




