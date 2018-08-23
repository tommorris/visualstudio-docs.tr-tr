---
title: IEEDataStorage::GetSize | Microsoft Docs
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
- IEEDataStorage::GetSize
helpviewer_keywords:
- IEEDataStorage::GetSize
ms.assetid: 33d232c4-1239-4abc-922b-e1bc5b908169
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d4c251224a5718d0f7264804c3130e5ea4a5d05f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692488"
---
# <a name="ieedatastoragegetsize"></a>IEEDataStorage::GetSize
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IEEDataStorage::GetSize](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ieedatastorage-getsize).  
  
Bu nesnede bulunan bayt sayısını döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT GetSize(  
   ULONG* size  
);  
```  
  
```csharp  
int GetSize(  
   out uint size  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `size`  
 [out] Bu nesnede bulunan bayt sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım [GetData](../../../extensibility/debugger/reference/ieedatastorage-getdata.md) gerçek veri baytı almak için yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)   
 [GetData](../../../extensibility/debugger/reference/ieedatastorage-getdata.md)

