---
title: BP_PASSCOUNT_STYLE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BP_PASSCOUNT_STYLE
helpviewer_keywords: BP_PASSCOUNT_STYLE structure
ms.assetid: 0a647047-e2d5-4724-a0b8-68108425ecad
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 58baa5aca9ef5bddf5d7060fdc88022952bc9ce3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="bppasscountstyle"></a>BP_PASSCOUNT_STYLE
Tetiklenecek kesme neden kesme noktası geçişi sayısı ile ilişkilendirilen koşulu belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_BP_PASSCOUNT_STYLE {   
   BP_PASSCOUNT_NONE             = 0x0000,  
   BP_PASSCOUNT_EQUAL            = 0x0001,  
   BP_PASSCOUNT_EQUAL_OR_GREATER = 0x0002,  
   BP_PASSCOUNT_MOD              = 0x0003  
};  
typedef DWORD BP_PASSCOUNT_STYLE;  
```  
  
```csharp  
public enum enum_BP_PASSCOUNT_STYLE {   
   BP_PASSCOUNT_NONE             = 0x0000,  
   BP_PASSCOUNT_EQUAL            = 0x0001,  
   BP_PASSCOUNT_EQUAL_OR_GREATER = 0x0002,  
   BP_PASSCOUNT_MOD              = 0x0003  
};  
```  
  
## <a name="members"></a>Üyeler  
 BP_PASSCOUNT_NONE  
 Hiçbir kesme noktası geçişi sayısı stilini belirtir.  
  
 BP_PASSCOUNT_EQUAL  
 Eşit kesme noktası geçişi sayısı stilini ayarlar. Kesme noktası isabet sayısı geçişi sayısı eşit olduğunda kesme ateşlenir.  
  
 BP_PASSCOUNT_EQUAL_OR_GREATER  
 Eşit veya daha büyük kesme noktası geçişi sayısı stilini ayarlar. Kesme noktası isabet sayısı eşit veya geçişi sayısından büyük olduğunda kesme ateşlenir.  
  
 BP_PASSCOUNT_MOD  
 Belirtir bir modül geçiş sayısı. Örneğin, geçiş sayısı türü ise `BP_PASSCOUNT_MOD` ve geçişi sayısı değeri 4, isabet sayısı 4 olan her zaman kesme noktası etkinleşir.  
  
## <a name="remarks"></a>Açıklamalar  
 İçin kullanılan `stylePassCount` üyesi [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md) sırayla üyesi olan yapısı [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) ve [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) yapıları.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)