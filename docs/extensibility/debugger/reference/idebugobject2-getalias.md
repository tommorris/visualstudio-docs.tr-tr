---
title: IDebugObject2::GetAlias | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugObject2::GetAlias
helpviewer_keywords: IDebugObject2::GetAlias method
ms.assetid: aa6824d5-c932-42ba-8713-950e7d1fb42f
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cdb6510edcb11df6359066637fd796d142ddae1a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugobject2getalias"></a>IDebugObject2::GetAlias
Bu nesneyle ilişkili diğer adı varsa alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetAlias(  
   IDebugAlias** ppAlias  
);  
```  
  
```csharp  
int GetAlias(  
   out IDebugAlias ppAlias  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppAlias`  
 [out] Döndüren bir [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md) bu nesne için diğer ad temsil eden nesne; Aksi takdirde null değeri döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK verir; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir nesne için bir diğer ad çağrısıyla oluşturulan [CreateAlias](../../../extensibility/debugger/reference/idebugobject2-createalias.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)   
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)