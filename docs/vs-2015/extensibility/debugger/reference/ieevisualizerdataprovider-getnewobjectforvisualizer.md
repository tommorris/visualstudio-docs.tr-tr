---
title: IEEVisualizerDataProvider::GetNewObjectForVisualizer | Microsoft Docs
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
- IEEVisualizerDataProvider::GetNewObjectForVisualizer
helpviewer_keywords:
- IEEVisualizerDataProvider::GetNewObjectForVisualizer method
ms.assetid: a898d549-4898-4fde-aad1-e8bb89129652
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f344033e719a06cba084bedcda2a495bd48a70a6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42696618"
---
# <a name="ieevisualizerdataprovidergetnewobjectforvisualizer"></a>IEEVisualizerDataProvider::GetNewObjectForVisualizer
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IEEVisualizerDataProvider::GetNewObjectForVisualizer](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ieevisualizerdataprovider-getnewobjectforvisualizer).  
  
Bu yöntem, yeni bir nesne için Görselleştirici alır. Bu yöntem, varolan nesneyi her zaman yeni bir nesne oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetNewObjectForVisualizer(  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int GetNewObjectForVisualizer(  
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppObject`  
 [out] Yeni nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `This method` Nesne şu anda temsil eder ve sonuç yeni bir nesne olarak döndüren yeniden değerlendirir. Varolan nesne değerlendirmesinin sonucu olarak güncelleştirilecektir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)   
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)

