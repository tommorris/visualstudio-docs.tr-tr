---
title: IDebugProperty3::DestroyObjectID | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugProperty3::DestroyObjectID
helpviewer_keywords:
- IDebugProperty3::DestroyObjectID
ms.assetid: bd08f356-cc67-4717-98c9-c3d00cad2040
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 5fdc38d8b337a653b9f8d1481a505dbe8e0cfaa4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugproperty3destroyobjectid"></a>IDebugProperty3::DestroyObjectID
Arayan artık bu özelliği diğer tüm özellikleri benzersiz olarak tanımlamak cares olduğunu gösteren bu özellik ile ilişkilendirilmiş benzersiz kimliği yok eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT DestroyObjectID(  
   void  
);  
```  
  
```csharp  
int DestroyObjectID();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Hata ayıklama altyapısı (Bu zaten bunları benzersiz olarak dahili izlediğinden) bir özellik için benzersiz kimlikler desteklemek gerekiyorsa değil, yalnızca döndürebilir sonra `E_NOTIMPL` bu yöntem için.  
  
 Benzersiz kimlikler çağrısıyla oluşturulur [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md) arayan bu özellik diğer özellikler arasında benzersiz şekilde tanımlanır emin olmak istediğinde yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md)