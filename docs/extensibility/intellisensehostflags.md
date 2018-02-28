---
title: IntelliSenseHostFlags | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IntellisenseHostFlags
helpviewer_keywords:
- IntelliSense, IntellisenseHostFlags enumeration
- IntellisenseHostFlags enumeration
ms.assetid: 0930640b-eb84-48ef-a8f7-d4268f55c99c
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 36cf7ba40deba4bd133f2c4baf92c310665ed275
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="intellisensehostflags"></a>IntelliSenseHostFlags
IntelliSense konak bayrakları belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum IntellisenseHostFlags  
{  
    IHF_READONLYCONTEXT      = 0x00000001  
    IHF_NOSEPARATESUBJECT    = 0x00000002  
    IHF_SINGLELINESUBJECT    = 0x00000004  
    IHF_FORCECOMMITTOCONTEXT = 0x00000008  
    IHF_OVERTYPE             = 0x00000010  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Üyeler|Açıklama|  
|-------------|-----------------|  
|`IHF_READONLYCONTEXT`|Bağlamı arabelleğine salt okunurdur.|  
|`IHF_NOSEPARATESUBJECT`|Konu metin yok. Bağlamı arabelleğine IntelliSense hedef içerir (gelir `!IHF_READONLYCONTEXT`).|  
|`IHF_SINGLELINESUBJECT`|Konu metni çok-satırı yeteneğine sahip değil.|  
|`IHF_FORCECOMMITTOCONTEXT`|Aynı `CanCommitIntoReadOnlyBuffer`.|  
|`IHF_OVERTYPE`|(Konu veya bağlam) düzenleme üzerine yazma modunda yapılması gerekir.|  
  
## <a name="requirements"></a>Gereksinimler  
 SingleFileeditor.idl  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.TextManager.Interop>