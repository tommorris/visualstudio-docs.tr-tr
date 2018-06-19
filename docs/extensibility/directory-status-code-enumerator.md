---
title: Dizin durum kodu Numaralandırıcı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- directory status code enumerator
- source control plug-ins, directory status enumeration
ms.assetid: 616026b5-f529-40ef-90c1-1836e116d797
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 539dc4c2ea7b33ce88465f1d8f6651dc890c8e45
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31126090"
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