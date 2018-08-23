---
title: IPropertyProxyEESide::CreateReplacementObject | Microsoft Docs
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
- IPropertyProxyEESide::CreateReplacementObject
helpviewer_keywords:
- IPropertyProxyEESide::CreateReplacementObject
ms.assetid: 0cfe79b8-c3f1-48b0-a225-e39dee2c92fe
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 048fe0e60422d5d787424256009ef585a133c914
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631120"
---
# <a name="ipropertyproxyeesidecreatereplacementobject"></a>IPropertyProxyEESide::CreateReplacementObject
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IPropertyProxyEESide::CreateReplacementObject](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ipropertyproxyeeside-createreplacementobject).  
  
İfade değerlendirici (EE) için belirli bir veri nesnesinin bir kopyasını oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT CreateReplacementObject(  
   IEEDataStorage*  dataIn,  
   IEEDataStorage** dataOut  
);  
```  
  
```csharp  
int CreateReplacementObject(  
   IEEDataStorage     dataIn,  
   out IEEDataStorage dataOut  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dataIn`  
 [in] Bir [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) kopyalanacak verileri tutan nesne.  
  
 `dataOut`  
 [out] Yeni bir `IEEDataStorage` nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem verilen bir [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) bayt dizisini temsil eden nesne. Bu gelen veri nesnesi tarafından EE genellikle uygulanmadı. Ancak, bu yöntem tarafından döndürülen nesne EE uygulama sağlayan EE tarafından her zaman gerçekleştirilir `IEEDataStorage` ne olursa olsun sınıfı isteniyorsa üzerinde arabirimi.  
  
 Veri gelen tarafından sağlanan Not `IEEDataStorage` nesne giden aynı verileri olmalıdır `IEEDataStorage` nesne.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)

