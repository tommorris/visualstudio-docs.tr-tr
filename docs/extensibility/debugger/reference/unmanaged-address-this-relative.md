---
title: UNMANAGED_ADDRESS_THIS_RELATIVE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: UNMANAGED_ADDRESS_THIS_RELATIVE
helpviewer_keywords: UNMANAGED_ADDRESS_THIS_RELATIVE structure
ms.assetid: e6a91ace-2d47-4ff9-aefb-8d8b68eab0b2
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 694a41033392ccd359ddc92607652cb1fb0bb905
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="unmanagedaddressthisrelative"></a>UNMANAGED_ADDRESS_THIS_RELATIVE
Bu yapı göreli bir adresi temsil eden bir `this` işaretçisi (`Me` Visual Basic'te).  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef struct _tagUNMANAGED_THIS_RELATIVE {  
   DWORD dwOffset;  
   DWORD dwBitOffset;  
   DWORD dwBitLength;  
} UNMANAGED_ADDRESS_THIS_RELATIVE;  
```  
  
```csharp  
public struct UNMANAGED_THIS_RELATIVE {  
   public uint dwOffset;  
   public uint dwBitOffset;  
   public uint dwBitLength;  
}  
```  
  
## <a name="terms"></a>Koşulları  
 dwOffset  
 Bayt (örneğin, bir sınıf vtable başlangıcı) temel bir konumdan uzaklığı.  
  
 dwBitOffset  
 Temel bir konumdan bit cinsinden uzaklık (her zaman 0 bit alana başvuran sürece).  
  
 dwBitLength  
 Adresini temsil eden bit sayısını (her zaman 0 bit alana başvuran sürece).  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı birleşim içinde yer [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md) ne zaman yapısı `dwKind` alanını `DEBUG_ADDRESS_UNION` yapısı ayarlanmış `ADDRESS_KIND_UNMANAGED_THIS_RELATIVE` (arasında bir değer [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md) numaralandırma).  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimleri](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)