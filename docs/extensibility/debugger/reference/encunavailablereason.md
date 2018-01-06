---
title: EncUnavailableReason | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: EncUnavailableReason
helpviewer_keywords: EncUnavailableReason enumeration
ms.assetid: c10aa4c0-d7e0-4de1-b8ff-7e050985eb12
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: c057b01c07bd3a2ae9466dc394676fe553fe14d0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="encunavailablereason"></a>EncUnavailableReason
`This is for internal use only!`Nedenleri temsil eder, **Düzenle ve devam et** kullanılabilir değil.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum tagEncUnavailableReason {  
   ENCUN_NONE,  
   ENCUN_INTEROP,  
   ENCUN_SQLCLR,  
   ENCUN_MINIDUMP,  
   ENCUN_EMBEDDED,  
   ENCUN_ATTACH,  
   ENCUN_WIN64  
};  
typedef enum tagEncUnavailableReason EncUnavailableReason;  
```  
  
```csharp  
public enum EncUnavailableReason {  
   ENCUN_NONE,  
   ENCUN_INTEROP,  
   ENCUN_SQLCLR,  
   ENCUN_MINIDUMP,  
   ENCUN_EMBEDDED,  
   ENCUN_ATTACH,  
   ENCUN_WIN64  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
 ENCUN_NONE  
 Belirli neden neden Düzenle ve devam et kullanılabilir değil.  
  
 ENCUN_INTEROP  
 Düzenle ve devam et kullanılamaz bir birlikte çalışabilirlik çağrısı sırasında.  
  
 ENCUN_SQLCLR  
 Düzenle ve devam et kullanılamaz ortak dil çalışma zamanı (CLR) kullanan bir SQL yordam çağrısı sırasında.  
  
 ENCUN_MINIDUMP  
 Düzenle ve devam et kullanılamaz bir mini döküm işlenirken hata oluştu.  
  
 ENCUN_EMBEDDED  
 Düzenle ve devam et kullanılamaz katıştırılmış kod işlerken.  
  
 ENCUN_ATTACH  
 Düzenle ve devam et olduğundan kullanılamaz oturumu için eklendiğinden başlatılmamış tarafından hata ayıklayıcı.  
  
 ENCUN_WIN64  
 Düzenle ve devam et kullanılamaz 64-bit Windows kod işlenirken hata oluştu.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu numaralandırma iç kullanım için göre Only'dir [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]. [GetENCAvailableState](../../../extensibility/debugger/reference/idebugprocess3-getencavailablestate.md) ve [DisableENC](../../../extensibility/debugger/reference/idebugprocess3-disableenc.md) özel bir bağlantı noktası sağlayıcı tarafından uygulanan yöntemleri her zaman döndürmelidir `E_NOTIMPL`.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.idl  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DisableENC](../../../extensibility/debugger/reference/idebugprocess3-disableenc.md)   
 [GetENCAvailableState](../../../extensibility/debugger/reference/idebugprocess3-getencavailablestate.md)