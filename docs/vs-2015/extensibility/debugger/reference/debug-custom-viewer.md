---
title: DEBUG_CUSTOM_VIEWER | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- DEBUG_CUSTOM_VIEWER
helpviewer_keywords:
- DEBUG_CUSTOM_VIEWER structure
ms.assetid: 8e0ef3f0-0107-48e8-a037-6e52b4c4ed9d
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8e706a787f679bb4ada85631626719e55e949b94
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629978"
---
# <a name="debugcustomviewer"></a>DEBUG_CUSTOM_VIEWER
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [DEBUG_CUSTOM_VIEWER](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/debug-custom-viewer).  
  
Özel bir Görüntüleyici tanımlayan bir yapı Görselleştirici yazın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef struct tagDEBUG_CUSTOM_VIEWER {  
   DWORD dwID;  
   BSTR  bstrMenuName;  
   BSTR  bstrDescription;  
   GUID  guidLang;  
   GUID  guidVendor;  
   BSTR  bstrMetric;  
} DEBUG_CUSTOM_VIEWER;  
```  
  
```csharp  
public struct DEBUG_CUSTOM_VIEWER {  
   public uint   dwID;  
   public string bstrMenuName;  
   public string bstrDescription;  
   public Guid   guidLang;  
   public Guid   guidVendor;  
   public string bstrMetric;  
};  
```  
  
## <a name="members"></a>Üyeler  
 dwID  
 Birden çok İzleyici mi tarafından uygulanan görselleştiricileri ayırt etmek için bir kimlik `GUID`.  
  
 bstrMenuName  
 Açılan menüde görüntülenen metin.  
  
 bstrDescription  
 (Bir null değer kullanılmazsa olmalıdır) tür görselleştiricisi ve özel Görüntüleyici açıklaması.  
  
 guidLang  
 Sağlayan bir ifade değerlendiricisi dili.  
  
 guidVendor  
 Satıcısına sağlayan bir ifade değerlendiricisi.  
  
 bstrMetric  
 Ölçüm hangi tür görselleştiricisi ve özel Görüntüleyici `CLSID` depolanır.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapının bir liste için bir çağrı tarafından döndürülen [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) yöntemi (ve uzantısı tarafından [GetCustomViewerList](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md) yöntemi).  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimler](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md)   
 [GetCustomViewerList](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md)

