---
title: BP_FLAGS90 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: BP_FLAGS90 enumeration
ms.assetid: 3e5a06c5-fb30-4b8a-b2d5-4a0570fc80bd
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: dddedfcbfe48f6ef6ceaedcdcfb1d7089307bcd3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="bpflags90"></a>BP_FLAGS90
İsteğe bağlı bayraklar geçerli değerlerini sıralar. İsteğe bağlı bayraklar bir kesme noktası ayarladığınızda ek bilgileri belirtmek için kullanılabilir. Bu numaralandırma genişletir [BP_FLAGS](../../../extensibility/debugger/reference/bp-flags.md) numaralandırması.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_BP_FLAGS90  
{  
   // VS 8.0 values  
   BP90_FLAG_NONE               = 0x0000,  
   BP90_FLAG_MAP_DOCPOSITION    = 0x0001,  
   BP90_FLAG_DONT_STOP          = 0x0002,  
  
   // Values added in VS 9.0  
   BP90_FLAG_TRACEPOINT_CONTINUE = 0x0004,  
};  
typedef DWORD BP_FLAGS90;  
```  
  
```csharp  
public enum enum_BP_FLAGS90  
{  
   // VS 8.0 values  
   BP90_FLAG_NONE                = 0x0000,  
   BP90_FLAG_MAP_DOCPOSITION     = 0x0001,  
   BP90_FLAG_DONT_STOP           = 0x0002,  
  
   // Values added in VS 9.0  
   BP90_FLAG_TRACEPOINT_CONTINUE = 0x0004,  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
 BP90_FLAG_NONE  
 Kesme noktası bayrak belirtir.  
  
 BP90_FLAG_MAP_DOCPOSITION  
 Belge konumu kullanarak hata ayıklama altyapısı (DE) kesme eşlemelisiniz belirtir. Bu, yalnızca Active Server Pages (ASP) gibi komut dosyası odaklı kaynak dosyalarında ayarlamak kesme noktaları için geçerlidir.  
  
 BP90_FLAG_DONT_STOP  
 Kesme noktası hata ayıklama motoru tarafından işlenmesi gerektiğini, ancak hata ayıklama altyapısı sonuçta var. durması gerektiğini değil belirtir; diğer bir deyişle, bir [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md) olay nesnesi gönderilmez. Bu bayrak, öncelikle izleme noktaları ile kullanılmak üzere tasarlanmıştır.  
  
 BP90_FLAG_TRACEPOINT_CONTINUE  
 Sürüm durumu temizlenmiş olup olmadığını belirlemek için yerel hata ayıklama altyapısı tarafından kullanılır. İzleme noktası makro yürütülürse BP90_FLAG_DONT_STOP ayarlanmadığından BP90_FLAG_DONT_STOP farklı.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Msdbg90.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)