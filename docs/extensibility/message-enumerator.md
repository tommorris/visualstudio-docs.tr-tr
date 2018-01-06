---
title: "İleti Numaralandırıcı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message enumerator
- source control plug-ins, message enumeration
ms.assetid: 4a4faa0d-d352-40ea-a21d-c09ea286a8e1
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 6a24db9c50bd298f068c23af0b6bad5755ec252d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="message-enumerator"></a>İleti Numaralandırıcı
Aşağıdaki bayraklar için kullanılan `TEXTOUTPROC` IDE çağırdığında sağlayan bir geri çağırma işlevidir işlevi [SccOpenProject](../extensibility/sccopenproject-function.md) (bkz [LPTEXTOUTPROC](../extensibility/lptextoutproc.md) geri çağırma hakkında ayrıntılı bilgi için işlev).  
  
 İşlemi iptal etmek için IDE sorulursa iptal iletilerinden birini alabilirsiniz. Bu durumda, kaynak denetim eklentisi kullanır `SCC_MSG_STARTCANCEL` görüntülemek için IDE sorulacak **iptal** düğmesi. Bundan sonra herhangi bir kümesi normal iletiler gönderilebilir. Bu döndürür varsa `SCC_MSG_RTN_CANCEL`, eklenti işlemi sonlandırılıyor ve döndürür. Ayrıca eklenti yoklar `SCC_MSG_DOCANCEL` düzenli aralıklarla kullanıcı işlemi iptal etti belirlemek için. Tüm işlemler yapılır ya da kullanıcı iptal etti, eklenti gönderir `SCC_MSG_STOPCANCEL`. `SCC_MSG_INFO`, SCC_MSG_WARNING, ve SCC_MSG_ERROR türleri, iletileri kaydırma listesinde görüntülenen iletileri için kullanılır. `SCC_MSG_STATUS`metin bir durum çubuğu veya geçici görüntü alanında gösterilmesi gerekir olduğunu gösteren özel bir türüdür. Listeden kalıcı olarak kalmaz.  
  
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