---
title: IPropertyProxyEESide::ResolveAssemblyRef | Microsoft Docs
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
- IPropertyProxyEESide::ResolveAssemblyRef
helpviewer_keywords:
- IPropertyProxyEESide::ResolveAssemblyRef
ms.assetid: 662ca0a6-dad0-4c00-a718-bb3bbc5bd9da
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6a3d8b5b41f8503a24d2a6d2643a1cf4c0290624
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686330"
---
# <a name="ipropertyproxyeesideresolveassemblyref"></a>IPropertyProxyEESide::ResolveAssemblyRef
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IPropertyProxyEESide::ResolveAssemblyRef](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ipropertyproxyeeside-resolveassemblyref).  
  
Belirtilen yönetilen bütünleştirilmiş kod başvurusu konumunu belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT ResolveAssemblyRef(  
   BSTR*                  assemName,  
   IEEDataStorage**       assemBytes,  
   IEEDataStorage**       assemPdb,  
   BSTR*                  assemLocation,  
   ASSEMBLYLOCRESOLUTION* alr  
);  
```  
  
```csharp  
int ResolveAssemblyRef(  
   ref string                     assemName,  
   out IEEDataStorage             assemBytes,  
   out IEEDataStorage             assemPdb,  
   out string                     assemLocation,  
   out enum_ASSEMBLYLOCRESOLUTION alr  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `assemName`  
 [in] Çözümlenecek derlemenin adı.  
  
 `assemBytes`  
 [out] Döndürür bir [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) başvuru ile ilişkili derleme baytları içeren nesne.  
  
 `assemPdb`  
 [out] Döndürür bir `IEEDataStorage` sembolü içeren bir nesne, bu başvuru ile ilişkili veri depolayın.  
  
 `assemLocation`  
 [out] Bu başvuru yolu konumunu döndürür.  
  
 `alr`  
 [out] Bir değer döndürür [ASSEMBLYLOCRESOLUTION](../../../extensibility/debugger/reference/assemblylocresolution.md) bu başvurusunun derleme konumunu belirten sabit listesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem, genellikle bir özel ifade değerlendiricisi tarafından uygulanmadı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)   
 [ASSEMBLYLOCRESOLUTION](../../../extensibility/debugger/reference/assemblylocresolution.md)

