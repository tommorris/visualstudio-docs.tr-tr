---
title: IEEDataStorage::GetData | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IEEDataStorage::GetData
helpviewer_keywords:
- IEEDataStorage::GetData
ms.assetid: 4d384039-73d4-40b4-ace6-a2474c546397
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: e18b51c20d2eaf324782574bf007ce32fdc6df2e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ieedatastoragegetdata"></a>IEEDataStorage::GetData
Belirtilen sayıda baytı nesnesinden alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetData(  
   ULONG  dataSize,  
   ULONG* sizeGotten,  
   BYTE*  data  
);  
```  
  
```csharp  
int GetData(  
   uint     dataSize,  
   out uint sizeGotten,  
   byte[]   data  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dataSize`  
 [in] Alınacak bayt sayısı ( `data` dizi gerekir tutmak en az bayt sayısı).  
  
 `sizeGotten`  
 [out] Gerçekte alınan bayt sayısını döndürür.  
  
 `data`  
 [içinde out] İstenen veri ile doldurulacak dizisi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Önerilen bu yöntem, tüm veri baytı alma işleminin bayt atlamayı şekilde olduğundan yerel bir diziye almak için kullanılır. Bu durumda, parametre `dataSize` tarafından değeri döndürülen [GetSize](../../../extensibility/debugger/reference/ieedatastorage-getsize.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)   
 [GetSize](../../../extensibility/debugger/reference/ieedatastorage-getsize.md)