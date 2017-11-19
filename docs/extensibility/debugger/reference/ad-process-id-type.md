---
title: AD_PROCESS_ID_TYPE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: AD_PROCESS_ID_TYPE
helpviewer_keywords: AD_PROCESS_ID_TYPE enumeration
ms.assetid: 0aab80e9-285a-4697-94ac-c864d42a6aaa
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 75904ef6e06ef7ccd6d126091f8ec0fbe523ac9a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="adprocessidtype"></a>AD_PROCESS_ID_TYPE
Bir işlem kimliği yorumlama belirtir [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) yapısı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
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
 İşlem kimliği sistem tanımlayıcısı değil. Kullanım `ProcessId.dwProcessId` alanını [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) yapısı.  
  
 AD_PROCESS_ID_GUID  
 İşlem kimliği bir GUID değeridir. Kullanım `ProcessId.guidProcessId` alanını `AD_PROCESS_ID` yapısı.  
  
## <a name="remarks"></a>Açıklamalar  
 İçin kullanılan `ProcessIdType` üyesi [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) yapısında bulunan işlem kimliği türünü tanımlamak için yapısı. Yorumlama belirler `ProcessId` yapısında birleşim.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)