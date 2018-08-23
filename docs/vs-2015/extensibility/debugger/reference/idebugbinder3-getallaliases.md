---
title: IDebugBinder3::GetAllAliases | Microsoft Docs
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
- IDebugBinder3::GetAllAliases
helpviewer_keywords:
- IDebugBinder3::GetAllAliases method
ms.assetid: 1f9ab2ee-2ab3-4a61-8b99-95dd7fdf3511
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e88ed8a93d77910d76cefefc0ee97c01f88de15b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693416"
---
# <a name="idebugbinder3getallaliases"></a>IDebugBinder3::GetAllAliases
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugBinder3::GetAllAliases](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugbinder3-getallaliases).  
  
Bu yöntem programın diğer adları listesini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetAllAliases(  
   UINT          uRequest,  
   IDebugAlias** ppAliases,  
   UINT*         puFetched  
);  
```  
  
```csharp  
int GetAllAliases(  
   uint          uRequest,   
   IDebugAlias[] ppAliases,   
   out uint      puFetched  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `uRequest`  
 [in] En fazla sayısını döndürmek için diğer adlar (içine geçirilen dizinin uzunluğunu belirtir `ppAliases`).  
  
 `ppAliases`  
 [out içinde] Diğer adlar ile oturum doldurmak için dizi (Bu bir null değer ise ve `uRequest` 0 ise, döndürülen diğer adlar sayısı tarafından döndürülen `puFetched`).  
  
 `puFetched`  
 [out] Elde ettiğiniz diğer adları sayısını döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)

