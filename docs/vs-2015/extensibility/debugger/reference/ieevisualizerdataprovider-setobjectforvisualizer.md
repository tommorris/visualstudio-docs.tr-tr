---
title: IEEVisualizerDataProvider::SetObjectForVisualizer | Microsoft Docs
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
- IEEVisualizerDataProvider::SetObjectForVisualizer
helpviewer_keywords:
- IEEVisualizerDataProvider::SetObjectForVisualizer method
ms.assetid: 40dad2be-57ff-4f74-9d82-c48039c125c4
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f0fdb66e3bae4e485109a4a5d6a8e808d27ffeed
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692554"
---
# <a name="ieevisualizerdataprovidersetobjectforvisualizer"></a>IEEVisualizerDataProvider::SetObjectForVisualizer
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IEEVisualizerDataProvider::SetObjectForVisualizer](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ieevisualizerdataprovider-setobjectforvisualizer).  
  
Bu yöntem Görselleştirici temsil eden nesneyi değiştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT SetObjectForVisualizer(  
   IDebugObject*  pNewObject,  
   BSTR*          error,  
   IDebugObject** pException  
);  
```  
  
```csharp  
int SetObjectForVisualizer(  
   IDebugObject     pNewObject,  
   out string       error,  
   out IDebugObject pException  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pNewObject`  
 [in] Ayarlanacağı nesne.  
  
 `error`  
 [out] Bu dize, nesne ayarlanırken bir hata oluştu, hata iletisi tutar.  
  
 `pException`  
 [out] Bir hata varsa, bu nesne, özel durum bilgilerini tutar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu, nasıl hata bilgileri döndürülür belirlemek için en fazla uygulayan olur. Ancak, bir hata olduğunda bu yöntem her zaman bir özel durum nesnesi döndürmelidir bu nedenle bir özel durum nesnesi var. bilmek döndürüldü, görmek için Görünüm, bir hata oluştu. yalnızca bazı çağıranlar olabilir mümkündür. Çağıranın olun ister durumunda hata dizesi ayrıca sağlanan bunu kullanın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)   
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)

