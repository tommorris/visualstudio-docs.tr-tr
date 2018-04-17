---
title: İleti Numaralandırıcı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- message enumerator
- source control plug-ins, message enumeration
ms.assetid: 4a4faa0d-d352-40ea-a21d-c09ea286a8e1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bc945908ac61a0eaa4df49c76725b2291686eac3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="message-enumerator"></a>İleti Numaralandırıcı
Aşağıdaki bayraklar için kullanılan `TEXTOUTPROC` IDE çağırdığında sağlayan bir geri çağırma işlevidir işlevi [SccOpenProject](../extensibility/sccopenproject-function.md) (bkz [LPTEXTOUTPROC](../extensibility/lptextoutproc.md) geri çağırma hakkında ayrıntılı bilgi için işlev).  
  
 İşlemi iptal etmek için IDE sorulursa iptal iletilerinden birini alabilirsiniz. Bu durumda, kaynak denetim eklentisi kullanır `SCC_MSG_STARTCANCEL` görüntülemek için IDE sorulacak **iptal** düğmesi. Bundan sonra herhangi bir kümesi normal iletiler gönderilebilir. Bu döndürür varsa `SCC_MSG_RTN_CANCEL`, eklenti işlemi sonlandırılıyor ve döndürür. Ayrıca eklenti yoklar `SCC_MSG_DOCANCEL` düzenli aralıklarla kullanıcı işlemi iptal etti belirlemek için. Tüm işlemler yapılır ya da kullanıcı iptal etti, eklenti gönderir `SCC_MSG_STOPCANCEL`. `SCC_MSG_INFO`, SCC_MSG_WARNING, ve SCC_MSG_ERROR türleri, iletileri kaydırma listesinde görüntülenen iletileri için kullanılır. `SCC_MSG_STATUS` metin bir durum çubuğu veya geçici görüntü alanında gösterilmesi gerekir olduğunu gösteren özel bir türüdür. Listeden kalıcı olarak kalmaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
enum {   
   SCC_MSG_RTN_CANCEL = -1,   
   SCC_MSG_RTN_OK = 0,   
   SCC_MSG_INFO = 1   
   SCC_MSG_WARNING,   
   SCC_MSG_ERROR,   
   SCC_MSG_STATUS,   
   SCC_MSG_DOCANCEL,   
   SCC_MSG_STARTCANCEL,   
   SCC_MSG_STOPCANCEL   
};  
```  
  
## <a name="members"></a>Üyeler  
 SCC_MSG_RTN_CANCEL  
 Belirtmek için geri dönüş iptal edin.  
  
 SCC_MSG_RTN_OK  
 Devam etmek için geri aramasından döndür.  
  
 SCC_MSG_INFO  
 Bilgilendirme iletisidir.  
  
 SCC_MSG_WARNING  
 İleti bir uyarıdır.  
  
 SCC_MSG_ERROR  
 İleti bir hatadır.  
  
 SCC_MSG_STATUS  
 İleti için durum çubuğunu amaçlanmıştır.  
  
 SCC_MSG_DOCANCEL  
 Herhangi bir metin; IDE verir `SCC_MSG_RTN_OK` veya `SCC_MSG_RTN_CANCEL`.  
  
 SCC_MSG_STARTCANCEL  
 İptal döngü başlatır.  
  
 SCC_MSG_STOPCANCEL  
 İptal döngü durur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim Eklentileri](../extensibility/source-control-plug-ins.md)   
 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)