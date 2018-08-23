---
title: BP_LOCATION_CODE_STRING | Microsoft Docs
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
- BP_LOCATION_CODE_STRING
helpviewer_keywords:
- BP_LOCATION_CODE_STRING structure
ms.assetid: a4cd71c6-5052-45fe-907b-ebc6ca1df2e4
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1f9ffbf5cf307957f297a73e91dc4319dae1b473
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42685789"
---
# <a name="bplocationcodestring"></a>BP_LOCATION_CODE_STRING
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [BP_LOCATION_CODE_STRING](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/bp-location-code-string).  
  
Tümleşik geliştirme ortamından (IDE) kullanıcının girebileceği bir dizesini kod kesme noktaları ayarlamak için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
typedef struct _BP_LOCATION_CODE_STRING {   
   BSTR bstrContext;  
   BSTR bstrCodeExpr;  
} BP_LOCATION_CODE_STRING;  
```  
  
## <a name="members"></a>Üyeler  
 `bstrContext`  
 Kod içinde kesme, genellikle bir yöntem veya işlev adı olarak görülen bir çağrı yığınında bağlamı.  
  
 `bstrCodeExpr`  
 Kodu kesme noktası tanımlamak için kullanıcının yazdığı bir dize.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı üyesidir [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) yapısı bir birleşimin parçası olarak.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimler](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)

