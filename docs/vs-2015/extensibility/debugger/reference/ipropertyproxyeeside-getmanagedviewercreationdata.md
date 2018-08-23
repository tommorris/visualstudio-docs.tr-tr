---
title: IPropertyProxyEESide::GetManagedViewerCreationData | Microsoft Docs
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
- IPropertyProxyEESide::GetManagedViewerCreationData
helpviewer_keywords:
- IPropertyProxyEESide::GetManagedViewerCreationData
ms.assetid: c4eb4d60-8816-4d52-bc8d-dffd4f066499
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 90087bfad956427ef3ff59fd7ffdc8b92c9f5687
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687704"
---
# <a name="ipropertyproxyeesidegetmanagedviewercreationdata"></a>IPropertyProxyEESide::GetManagedViewerCreationData
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IPropertyProxyEESide::GetManagedViewerCreationData](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ipropertyproxyeeside-getmanagedviewercreationdata).  
  
Bu Görüntüleyici bir örneğini oluşturmak için bu özellik türü Görüntüleyicisi hakkında bilgi alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT GetManagedViewerCreationData(  
   BSTR*                  assemName,  
   IEEDataStorage**       assemBytes,  
   IEEDataStorage**       assemPdb,  
   BSTR*                  className,  
   ASSEMBLYLOCRESOLUTION* alr,  
   BOOL*                  replacementOk  
);  
```  
  
```csharp  
int GetManagedViewerCreationData(  
   out string                     assemName,  
   out IEEDataStorage             assemBytes,  
   out IEEDataStorage             assemPdb,  
   out string                     className,  
   out enum_ASSEMBLYLOCRESOLUTION alr,  
   out int                        replacementOk  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `assemName`  
 [out] Bu nesne bulunduran derlemenin adını döndürür.  
  
 `assemBytes`  
 [out] Döndürür bir [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) (Bu, bir null değer yok bayt mevcutsa) bu nesnenin derleme baytları içeren nesne.  
  
 `assemPdb`  
 [out] Döndürür bir `IEEDataStorage` sembolü içeren bir nesne, bu nesne için (Bu, bir null değer hiçbir sembol deposu varsa) bilgileri depolar.  
  
 `className`  
 [out] Bu nesneyi içeren sınıf adını döndürür.  
  
 `alr`  
 [out] Bir değer döndürür [ASSEMBLYLOCRESOLUTION](../../../extensibility/debugger/reference/assemblylocresolution.md) derleme konumunu belirten sabit listesi.  
  
 `replacementOk`  
 [out] Sıfır olmayan döndürür (`TRUE`) bu nesnenin değeri değiştirilebilir; sıfır (`FALSE`) nesne salt okunur ise.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem, tür görselleştiricilerde, yönetilen bir Görüntüleyici örneklemek için kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [ASSEMBLYLOCRESOLUTION](../../../extensibility/debugger/reference/assemblylocresolution.md)   
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)

