---
title: IntelliSenseHostFlags | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IntellisenseHostFlags
helpviewer_keywords:
- IntelliSense, IntellisenseHostFlags enumeration
- IntellisenseHostFlags enumeration
ms.assetid: 0930640b-eb84-48ef-a8f7-d4268f55c99c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 582dc76bfd8b76ffa4d3664ab3e28f95fe2cef50
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2018
ms.locfileid: "39500020"
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
  
### <a name="parameters"></a>Parametreler  
  
|Üyeler|Açıklama|  
|-------------|-----------------|  
|`IHF_READONLYCONTEXT`|Bağlamı arabelleğine salt okunur.|  
|`IHF_NOSEPARATESUBJECT`|Konu metin yok. Bağlamı arabelleğine IntelliSense hedef içerir (gelir `!IHF_READONLYCONTEXT`).|  
|`IHF_SINGLELINESUBJECT`|Konu metnini çok-satırı özelliğine sahip değil.|  
|`IHF_FORCECOMMITTOCONTEXT`|Aynı `CanCommitIntoReadOnlyBuffer`.|  
|`IHF_OVERTYPE`|(Konu veya bağlam) düzenleme, üzerine yazma modunda yapılmalıdır.|  
  
## <a name="requirements"></a>Gereksinimler  
 SingleFileeditor.idl  
  
## <a name="see-also"></a>Ayrıca bkz.  
 <xref:Microsoft.VisualStudio.TextManager.Interop>