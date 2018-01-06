---
title: "EnsureVSTOComponent işlevi | Microsoft Docs"
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
ms.assetid: e101fcd5-37a2-4b8c-b9ac-a84624298736
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 4b0bb6753e83e6d0f5c871aa193ae9ab95aa8c45
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ensurevstocomponent-function"></a>EnsureVSTOComponent İşlevi
  Bu API Office altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT EnsureVSTOComponent(  
    IVSTProject *pProject  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*pProject*|Kullanmayın.|  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa, döndürür **S_OK**. İşlev başarısız olursa bir hata kodu döndürür.  
  
  