---
title: IDebugStackFrame2::GetPhysicalStackRange | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugStackFrame2::GetPhysicalStackRange
helpviewer_keywords: IDebugStackFrame2::GetPhysicalStackRange
ms.assetid: 2f6992e2-ac1c-433f-83b7-a7f83a4ce63d
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e90137ada43a127dc3c7eac3c98620f3a846d024
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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