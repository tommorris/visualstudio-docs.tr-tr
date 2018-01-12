---
title: "GetValidCompatibleFramework işlevi | Microsoft Docs"
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
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 43056033f6d23eb385609ebaf4d448ebdb2424a8
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="getvalidcompatibleframework-function"></a>GetValidCompatibleFramework İşlevi
  Bu API Office altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT WINAPI GetValidCompatibleFramework(  
    LPCWSTR lpwszCompatibleFrameworksXML,  
    BSTR* pbstrValidFrameworkTag  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*lpwszCompatibleFrameworksXML*|Kullanmayın.|  
|*pbstrValidFrameworkTag*|Kullanmayın.|  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa, döndürür **S_OK**. İşlev başarısız olursa bir hata kodu döndürür.  
  
  