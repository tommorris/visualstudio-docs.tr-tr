---
title: NATIVE_ADDRESS | Microsoft Docs
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
- NATIVE_ADDRESS
helpviewer_keywords:
- NATIVE_ADDRESS structure
ms.assetid: 7a0cd085-bfc8-45cc-a3d4-4459070e207a
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 361bfb482f441dc464196adc28d041f986d9684f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691113"
---
# <a name="nativeaddress"></a>NATIVE_ADDRESS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [NATIVE_ADDRESS](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/native-address).  
  
Bu yapı, yerel bir adresi temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef struct _tagNATIVE_ADDRESS {  
   DWORD unknown;  
} NATIVE_ADDRESS;  
```  
  
```csharp  
public struct NATIVE_ADDRESS {  
   public uint unknown;  
}  
```  
  
## <a name="terms"></a>Koşulları  
 Bilinmiyor  
 Yerel Adres (çalışma zamanı ve işletim sistemi bu anlamını bağlıdır).  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı, birleşim içinde parçasıdır [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md) ne zaman yapısı `dwKind` alanını `DEBUG_ADDRESS_UNION` yapısı ayarlandığında `ADDRESS_KIND_NATIVE` (arasında bir değer [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md) sabit listesi).  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimler](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)

