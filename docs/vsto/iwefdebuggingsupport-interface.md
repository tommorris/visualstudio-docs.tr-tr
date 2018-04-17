---
title: Iwefdebuggingsupport arabirimi | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 8e8a1bc770ce030902691a8ee4f2634c79cbab9a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="iwefdebuggingsupport-interface"></a>IWefDebuggingSupport Arabirimi
  Visual hata ayıklama için Office uygulamaları kolaylaştırmak için Studio gibi bir hata ayıklama ortamı tarafından uygulanır. Word veya Excel gibi Office uygulamasının Visual Studio'dan bu arabirim alır ve yöntemleri bazı noktalarda arabirimde hata ayıklama oturumu sırasında çağırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[  
    uuid(ccaf1a90-ce1c-4199-9cd6-b40c5c57a671),  
    oleautomation  
]  
interface IWefDebuggingSupport : IUnknown  
{  
    HRESULT SetWefProcessId(  
        [in] DWORD dwProcessId);  
    HRESULT GetAutoInsertExtensions(  
        [out, retval] SAFEARRAY(BSTR)* psaExtensionNames);  
}  
```  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda Iwefdebuggingsupport arabirimi tanımlar yöntemlerini listeler.  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[GetAutoInsertExtensions Metodu](../vsto/getautoinsertextensions-method.md)|Hata ayıklama sırasında otomatik olarak eklenmesini olan Office için uygulamalar hakkındaki bilgileri alır.|  
|[SetWefProcessId Metodu](../vsto/setwefprocessid-method.md)|Web uzantılarının Framework (WEF) içerik çalışacak işlem tanımlayıcısını sağlar.|  
  
  