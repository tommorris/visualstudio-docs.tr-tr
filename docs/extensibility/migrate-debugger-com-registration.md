---
title: "64-bit hata ayıklayıcı COM sınıfı kaydı geçirme | Microsoft Docs"
ms.custom: 
ms.date: 11/10/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45cfcee6-7a68-4d4f-b3f6-e2d8a0fa066a
caps.latest.revision: "1"
author: gregg-miskelly
ms.author: greggm
manager: ghogen
ms.openlocfilehash: 06bfef5f1b4d67cb691a74b953296b1ab057d62f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="migrate-64-bit-debugger-com-class-registration"></a>64-bit hata ayıklayıcı COM sınıfı kayıt geçirme

COM sınıfları (tarafından regasm, regsvr32, kullanarak veya doğrudan kayıt defterine yazma) içinde HKEY_CLASSES_ROOT kaydetmek ve msvsmon.exe (uzaktan hata ayıklayıcı) yüklenen hata ayıklayıcı uzantıları için artık gerek kalmadan bu kayda msvsmon sağlamak mümkündür HKEY_CLASSES_ROOT için yazılacak. Bu, eski .NET hata ayıklayıcı ifade değerlendiricisi veya msvsmon.exe işleminde yüklemek üzere yapılandırılan debug motorları etkiler.

## <a name="msvsmon-comclass-def"></a>msvsmon comclass def

Bu yöntemi kullanmak için msvsmon (InstallDir:\Common7\IDE\Remote Debugger\x64) yanındaki *.msvsmon comclass def.json dosya ekleyin.

Bir yönetilen kaydeder bir örnek msvsmon comclass def dosyası ve bir yerel sınıfı şöyledir:

Dosya adı: MyCompany.MyExample.msvsmon comclass def.json

```json
{
  "managedCOMClasses": [
    {
      "clsid": "{C9F48B25-36ED-4B22-8210-98BC5BE4D1E7}",
      "assemblyName": "MyCompany.MyAssembly",
      "className": "MyCompany.MyNamespace.MyClass"
    }
  ],
  "nativeCOMClasses": [
    {
      "clsid": "{42A476E9-8FA7-44D5-ADFE-216AD371EEC9}",
      "dllPath": "MyExample.dll"
    }
  ]
}
```
