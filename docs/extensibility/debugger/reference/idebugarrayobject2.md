---
title: IDebugArrayObject2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugArrayObject2 interface
ms.assetid: be6e504d-4ab3-4141-a61b-0953ee0e038e
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 13e522497a0046ebfc99c60c7c3d771acfd4fbca
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugarrayobject2"></a>IDebugArrayObject2
> [!IMPORTANT]
>  Visual Studio 2015'te ifade değerlendiricisi uygulama bu şekilde kullanım dışıdır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricileri](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Yönetilen dizi nesnesi temsil eder ve bir ifade değerlendiricisi dizisi için temel dizin (alt sınırlarını) belirlemek için (EE) sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugArrayObject2 : IDebugArrayObject  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Bu yönetilen hata ayıklama altyapısı (DE) tarafından uygulanır.  
  
## <a name="methods"></a>Yöntemler  
 Yöntemlere ek olarak [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md) arabirimi, bu arabirimi uygulayan aşağıdaki yöntemleri:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetBaseIndices](../../../extensibility/debugger/reference/idebugarrayobject2-getbaseindices.md)|Dimensions sayısı dizideki verilen her dizin için temel dizinlerini (alt sınırlarını) alır.|  
|[HasBaseIndices](../../../extensibility/debugger/reference/idebugarrayobject2-hasbaseindices.md)|Dizi tanımlanmış temel dizinlerini (alt sınırlarını) olup olmadığını belirler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir ifade değerlendiricisi ayrıştırma ağacına yönetilen diziler temsil etmek için bu arabirimi kullanır.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll