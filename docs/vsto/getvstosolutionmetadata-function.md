---
title: "GetVstoSolutionMetadata işlevi | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
ms.assetid: e8195838-fb9f-42b2-bb76-7ae3753f7751
caps.latest.revision: "6"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e0d0a3975acc272f9c4727e6a7b35aff7f698866
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="getvstosolutionmetadata-function"></a>GetVstoSolutionMetadata İşlevi
  Bu API Office altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT WINAPI GetVstoSolutionMetadata(  
    LPCWSTR lpwszSolutionMetadataKey,  
    ISolutionMetadata** ppSolutionInfo  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*lpwszSolutionMetadataKey*|Kullanmayın.|  
|*ppSolutionInfo*|Kullanmayın.|  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa, döndürür **S_OK**. İşlev başarısız olursa bir hata kodu döndürür.  
  
  