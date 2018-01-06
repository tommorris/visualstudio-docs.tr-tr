---
title: "Dizin durum kodu Numaralandırıcı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- directory status code enumerator
- source control plug-ins, directory status enumeration
ms.assetid: 616026b5-f529-40ef-90c1-1836e116d797
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a29b9453fa7fd36564fef2956c1d41cc7f29cf07
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="directory-status-code-enumerator"></a>Dizin durum kodu Numaralandırıcı
`SccDirStatus` Numaralandırıcı kaynak denetim sistemi bir dizin durumunu belirtin adlandırılmış sabit değerleri içerir. Bu numaralandırma tarafından kullanılan [SccDirQueryInfo](../extensibility/sccdirqueryinfo-function.md). Bu sürüm kaynak denetim eklentisi API 1.2 sunulmuştur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
enum SccDirStatus {  
   SCC_DIRSTATUS_INVALID       = -1L,  
   SCC_DIRSTATUS_NOTCONTROLLED = 0x0000L,  
   SCC_DIRSTATUS_CONTROLLED    = 0x0001L,  
   SCC_DIRSTATUS_EMPTYPROJ     = 0x0002L  
};  
```  
  
## <a name="members"></a>Üyeler  
 SCC_DIRSTATUS_INVALID  
 Durum edinilemedi; üzerinde kullanmayın.  
  
 SCC_DIRSTATUS_NOTCONTROLLED  
 Dizin kaynak denetimi altında değil.  
  
 SCC_DIRSTATUS_CONTROLLED  
 Kaynak denetimi altında dizindir.  
  
 SCC_DIRSTATUS_EMPTYPROJ  
 Bu dizine karşılık gelen proje boştur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim Eklentileri](../extensibility/source-control-plug-ins.md)   
 [SccDirQueryInfo](../extensibility/sccdirqueryinfo-function.md)