---
title: IDebugAlias::GetICorDebugValue | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugAlias::GetICorDebugValue
helpviewer_keywords: IDebugAlias::GetICorDebugValue method
ms.assetid: b9eb39ee-84af-4ace-9cfe-236b3d48aff5
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 603f24f89463b9eb9f7c67ed3d05662870e41bf3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugaliasgeticordebugvalue"></a>IDebugAlias::GetICorDebugValue
Bu diğer ad ile ilişkili değer temsil eden bir yönetilen kod arabirim alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetICorDebugValue(  
   IUnknown** ppUnk  
);  
```  
  
```csharp  
int GetICorDebugValue(  
   out object ppUnk  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppUnk`  
 [out] `IUnknown` bu diğer ad ile ilişkili değer temsil eden arabirim. Bu arabirim için sorgulanabilir `ICorDebugValue` arabirimi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK verir; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem yalnızca yönetilen değerleri için geçerlidir ( `ICorDebugValue` bir arabirim kullanılabilir [!INCLUDE[dnprdnshort](../../../code-quality/includes/dnprdnshort_md.md)] ve içinde tanımlanan [!INCLUDE[dnprdnshort](../../../code-quality/includes/dnprdnshort_md.md)] cordebug.idl dosyasında SDK).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)