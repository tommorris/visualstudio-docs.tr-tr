---
title: Dosya durumu kod numaralandırıcısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- named constants, SccStatus enumerator
- source control plug-ins, file status enumeration
- SccStatus enumerator
- file status code enumerator
ms.assetid: 5c37876b-c83c-4ca1-837b-57cd465a879a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0b51e20c18562c1c0e6c23968577dd58eadfe59e
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2018
ms.locfileid: "39498174"
---
# <a name="file-status-code-enumerator"></a>Dosya durumu kod numaralandırıcısı
`SccStatus` Numaralandırıcı kaynak denetimi sisteminizden bir dosya durumunu belirten adlandırılmış sabit değerleri içerir. Bu sabit listesi tarafından kullanılan [Sccqueryınfo](../extensibility/sccqueryinfo-function.md) ve `POPLISTFUNC` geri çağırma işlevi (bkz [POPLISTFUNC](../extensibility/poplistfunc.md) Ayrıntılar için).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
enum SccStatus {  
   SCC_STATUS_INVALID          = -1L,  
   SCC_STATUS_NOTCONTROLLED    = 0x0000L,  
   SCC_STATUS_CONTROLLED       = 0x0001L,  
   SCC_STATUS_CHECKEDOUT       = 0x0002L,  
   SCC_STATUS_OUTOTHER         = 0x0004L,  
   SCC_STATUS_OUTEXCLUSIVE     = 0x0008L,  
   SCC_STATUS_OUTMULTIPLE      = 0x0010L,  
   SCC_STATUS_OUTOFDATE        = 0x0020L,  
   SCC_STATUS_DELETED          = 0x0040L,  
   SCC_STATUS_LOCKED           = 0x0080L,  
   SCC_STATUS_MERGED           = 0x0100L,  
   SCC_STATUS_SHARED           = 0x0200L,  
   SCC_STATUS_PINNED           = 0x0400L,  
   SCC_STATUS_MODIFIED         = 0x0800L,  
   SCC_STATUS_OUTBYUSER        = 0x1000L  
   SCC_STATUS_NOMERGE          = 0x2000L  
   SCC_STATUS_RESERVED_1       = 0x4000L  
   SCC_STATUS_RESERVED_2       = 0x8000L  
};  
```  
  
## <a name="members"></a>Üyeler  
 SCC_STATUS_INVALID  
 Durumu alınamadı; üzerinde güvenmeyin.  
  
 SCC_STATUS_NOTCONTROLLED  
 Dosya kaynak denetimi altında değil.  
  
 SCC_STATUS_CONTROLLED  
 Kaynak denetimi altında dosyasıdır.  
  
 SCC_STATUS_CHECKEDOUT  
 Yerel diskte geçerli bir kullanıcı tarafından kullanıma alınmış.  
  
 SCC_STATUS_OUTOTHER  
 Dosya başka bir kullanıcı tarafından kullanıma alındı.  
  
 SCC_STATUS_OUTEXCLUSIVE  
 Dosya özel olarak kullanıma.  
  
 SCC_STATUS_OUTMULTIPLE  
 Dosya birden fazla kullanıcı tarafından kullanıma alındı.  
  
 SCC_STATUS_OUTOFDATE  
 Dosyanın en son değil.  
  
 SCC_STATUS_DELETED  
 Dosyayı projeden silindi.  
  
 SCC_STATUS_LOCKED  
 Dosya kilitli; Daha fazla sürüm izin verilir.  
  
 SCC_STATUS_MERGED  
 Dosya birleştirilmiş ancak henüz sabit/doğrulandı.  
  
 SCC_STATUS_SHARED  
 Dosya, projeler arasında paylaşılır.  
  
 SCC_STATUS_PINNED  
 Açık bir sürüm için paylaşılan bir dosya.  
  
 SCC_STATUS_MODIFIED  
 Dosya değişiklik/ayrılmış/ihlal olmuştur.  
  
 SCC_STATUS_OUTBYUSER  
 Dosya geçerli bir kullanıcı tarafından kullanıma alındı.  
  
 SCC_STATUS_NOMERGE  
 Dosya hiçbir zaman ile birleştirilebilir ve GET önce kaydedilmemiş.  
  
 SCC_STATUS_RESERVED_1  
 İç kullanım için ayrılmıştır.  
  
 SCC_STATUS_RESERVED_2  
 İç kullanım için ayrılmıştır.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Kaynak denetimi eklentileri](../extensibility/source-control-plug-ins.md)   
 [Sccqueryınfo](../extensibility/sccqueryinfo-function.md)   
 [POPLISTFUNC](../extensibility/poplistfunc.md)