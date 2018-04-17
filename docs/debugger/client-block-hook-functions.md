---
title: İstemci blok kanca işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.hooks
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- client blocks, validating and reporting data
- debugging [C++], hook functions
- _CrtSetDumpClient function
- client blocks, hook functions
- hooks, client block
ms.assetid: f21c197e-565d-4e3f-9b27-4c018c9b87fc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 711f7de86617f6574427a65c6efcef62c558306b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="client-block-hook-functions"></a>İstemci Blok Kanca İşlevleri
Doğrulama veya depolanan veri içeriğini rapor isteyip istemediğinizi `_CLIENT_BLOCK` engeller, özellikle bu amaç için bir işlev yazabilirsiniz. Yazdığınız işlevi aşağıdakine benzer bir prototip CRTDBG içinde tanımlanan olması gerekir. Y:  
  
```  
void YourClientDump(void *, size_t)  
  
```  
  
 Diğer bir deyişle, kanca işlevini kabul etmelidir bir **void** birlikte ayırma blok başlangıcı işaretçi bir **size_t** ayırma boyutu gösteren değer yazın ve dönmek`void`. Dışında içeriği, kadar olan.  
  
 Kanca işlevini kullanarak yükledikten sonra [_CrtSetDumpClient](/cpp/c-runtime-library/reference/crtsetdumpclient), her zaman çağrılacağı bir `_CLIENT_BLOCK` blok yazılan. Daha sonra [_CrtReportBlockType](/cpp/c-runtime-library/reference/crtreportblocktype) türü veya alt Dökümü alınan blokların hakkında bilgi almak için.  
  
 Geçişi için işlev işaretçisi `_CrtSetDumpClient` türü **_crt_dump_clıent**, CRTDBG içinde tanımlanan. Y:  
  
```  
typedef void (__cdecl *_CRT_DUMP_CLIENT)  
   (void *, size_t);  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama kanca işlevi yazma](../debugger/debug-hook-function-writing.md)   
 [crt_dbg2 örnek](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167)   
 [_CrtReportBlockType](/cpp/c-runtime-library/reference/crtreportblocktype)