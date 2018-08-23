---
title: IntelliSenseHostFlags | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IntellisenseHostFlags
helpviewer_keywords:
- IntelliSense, IntellisenseHostFlags enumeration
- IntellisenseHostFlags enumeration
ms.assetid: 0930640b-eb84-48ef-a8f7-d4268f55c99c
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ef0e800cbe2d101fa9ce44367ef54fb1834a7fd4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630123"
---
# <a name="intellisensehostflags"></a>IntelliSenseHostFlags
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IntelliSenseHostFlags](https://docs.microsoft.com/visualstudio/extensibility/intellisensehostflags).  
  
IntelliSense konak bayrakları belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
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
|`IHF_READONLYCONTEXT`|Bağlamı arabelleğine salt okunur.|  
|`IHF_NOSEPARATESUBJECT`|Konu metin yok. Bağlamı arabelleğine IntelliSense hedef içerir (gelir `!IHF_READONLYCONTEXT`).|  
|`IHF_SINGLELINESUBJECT`|Konu metnini çok-satırı özelliğine sahip değil.|  
|`IHF_FORCECOMMITTOCONTEXT`|Aynı `CanCommitIntoReadOnlyBuffer`.|  
|`IHF_OVERTYPE`|(Konu veya bağlam) düzenleme, üzerine yazma modunda yapılmalıdır.|  
  
## <a name="requirements"></a>Gereksinimler  
 SingleFileeditor.idl  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.TextManager.Interop>

