---
title: METADATA_ADDRESS_METHOD | Microsoft Docs
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
- METADATA_ADDRESS_METHOD
helpviewer_keywords:
- METADATA_ADDRESS_METHOD structure
ms.assetid: fc0e5370-1b4f-4867-837f-0d63c4b9dd09
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: be74663ad9e210ec8211c71b2a20eb93c03e9287
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42682108"
---
# <a name="metadataaddressmethod"></a>METADATA_ADDRESS_METHOD
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [METADATA_ADDRESS_METHOD](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/metadata-address-method).  
  
Bu yapı, bir sınıfın yöntemini adresini temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef struct _tagMETADATA_ADDRESS_METHOD {  
   _mdToken tokMethod;  
   DWORD    dwOffset;  
   DWORD    dwVersion;  
} METADATA_ADDRESS_METHOD;  
```  
  
```csharp  
public struct METADATA_ADDRESS_METHOD {  
   public int  tokMethod;  
   public uint dwOffset;  
   public uint dwVersion;  
}  
```  
  
## <a name="terms"></a>Koşulları  
 tokMethod  
 Yöntem kimliği.  
  
 [C++] `_mdToken` olduğu bir `typedef` 32-bit `int`.  
  
 dwOffset  
 Sınıf başlangıç uzaklığı bu yönteme (uzaklığı vtable temsil edebilir).  
  
 Kaynak  
 (Bu değer sembol sağlayıcısı için benzersiz olan) yöntemi sürümü.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı, birleşim içinde parçasıdır [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md) ne zaman yapısı `dwKind` alanını `DEBUG_ADDRESS_UNION` yapısı ayarlandığında `ADDRESS_KIND_METHOD` (arasında bir değer [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md) sabit listesi).  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimler](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)   
 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)

