---
title: IDebugExpressionEvaluator::SetRegistryRoot | Microsoft Docs
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
- IDebugExpressionEvaluator::SetRegistryRoot
helpviewer_keywords:
- IDebugExpressionEvaluator::SetRegistryRoot method
ms.assetid: 790886d8-1975-4d3c-9a75-cd86c1faf4ca
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bb6b7bde8c0d4da316112828b495a414ba4f1fb0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629959"
---
# <a name="idebugexpressionevaluatorsetregistryroot"></a>IDebugExpressionEvaluator::SetRegistryRoot
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugExpressionEvaluator::SetRegistryRoot](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugexpressionevaluator-setregistryroot).  
  
Bu yöntem, kayıt defteri kökü ayarlar. Yan yana hata ayıklamak için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT SetRegistryRoot (   
   LPCOLESTR ustrRegistryRoot  
);  
```  
  
```csharp  
int SetRegistryRoot(  
   string ustrRegistryRoot  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ustrRegistryRoot`  
 [in] Yeni kayıt defteri kökü.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 İfade değerlendirici ilk örneği işaret yüklendiğinde belirtilen kayıt defteri kökü genellikle ayarlanır ve Visual Studio'nun belirli bir sürümü için kayıt defteri anahtarı için (hkey_local_machıne\software\microsoft\visualstudio\\*X.Y* burada *X.Y* bir sürüm numarası).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)

