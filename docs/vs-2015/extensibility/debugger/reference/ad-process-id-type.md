---
title: AD_PROCESS_ID_TYPE | Microsoft Docs
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
- AD_PROCESS_ID_TYPE
helpviewer_keywords:
- AD_PROCESS_ID_TYPE enumeration
ms.assetid: 0aab80e9-285a-4697-94ac-c864d42a6aaa
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4c9327c84b8cdac8eab1a00b7dd2b665456dcaaa
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42683650"
---
# <a name="adprocessidtype"></a>AD_PROCESS_ID_TYPE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [AD_PROCESS_ID_TYPE](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ad-process-id-type).  
  
Bir işlem kimliği yorumlama belirtir [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) yapısı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
enum enum_AD_PROCESS_ID {  
   AD_PROCESS_ID_SYSTEM = 0,  
   AD_PROCESS_ID_GUID   = 1  
};  
typedef DWORD AD_PROCESS_ID_TYPE;  
```  
  
```csharp  
public enum enum_AD_PROCESS_ID {  
   AD_PROCESS_ID_SYSTEM = 0,  
   AD_PROCESS_ID_GUID   = 1  
};  
```  
  
## <a name="members"></a>Üyeler  
 AD_PROCESS_ID_SYSTEM  
 İşlem, sistem tanımlayıcısı kimliğidir. Kullanım `ProcessId.dwProcessId` alanını [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) yapısı.  
  
 AD_PROCESS_ID_GUID  
 İşlem kimliği bir GUID değeridir. Kullanım `ProcessId.guidProcessId` alanını `AD_PROCESS_ID` yapısı.  
  
## <a name="remarks"></a>Açıklamalar  
 İçin kullanılan `ProcessIdType` üyesi [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) yapısında bulunan işlem kimliği türünü tanımlamak için yapı. Nasıl yorumlanacağını belirler `ProcessId` bileşim yapısı içinde.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sabit listeleri](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)

