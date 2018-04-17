---
title: IDebugStackFrame2::GetPhysicalStackRange | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugStackFrame2::GetPhysicalStackRange
helpviewer_keywords:
- IDebugStackFrame2::GetPhysicalStackRange
ms.assetid: 2f6992e2-ac1c-433f-83b7-a7f83a4ce63d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: be53b50bc21d81c60f7131e8ed437ecb2ac2f16c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugstackframe2getphysicalstackrange"></a>IDebugStackFrame2::GetPhysicalStackRange
Yığın çerçevesi ile ilişkili fiziksel adres aralığını makine bağımlı bir gösterimini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetPhysicalStackRange (   
   UINT64* paddrMin,  
   UINT64* paddrMax  
);  
```  
  
```csharp  
int GetPhysicalStackRange (   
   out ulong paddrMin,  
   out ulong paddrMax  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `paddrMin`  
 [out] Bu yığın çerçevesi ile ilişkili en düşük fiziksel adresini döndürür.  
  
 `paddrMax`  
 [out] Bu yığın çerçevesi ile ilişkili en yüksek fiziksel adresini döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından döndürülen bilgi yığın çerçeveleri sıralamak için oturumu hata ayıklama Yöneticisi (SDM) tarafından kullanılır.  
  
 Bu çağrı yığını aşağı, yani büyür olduğundan, yeni yığın çerçeveleri giderek daha düşük bellek adreslerde eklenir varsayılır. Bir çalışma zamanı mimarisi Bu varsayım eşleşen fiziksel yığını aralıkları sağlamanız gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)