---
title: IDebugBinder3::FindAlias | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugBinder3::FindAlias
helpviewer_keywords:
- IDebugBinder3::FindAlias method
ms.assetid: b8333701-2718-4983-8513-0875fb7cb730
caps.latest.revision: 10
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: b88ae0da5f90da45d33ec56169665e9c8430846c
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="idebugbinder3findalias"></a>IDebugBinder3::FindAlias
Bu yöntem bir adı verilen bir diğer ad bulur. Bu, tüm diğer adlar programa arar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT FindAlias(  
   LPCOLESTR     pcstrName,  
   IDebugAlias** ppAlias  
);  
```  
  
```csharp  
int FindAlias(  
   string          pcstrName,  
   out IDebugAlias ppAlias  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pcstrName`  
 [in] Bulmak için diğer adı.  
  
 `ppAlias`  
 [out] Diğer adı (varsa) kalıyor temsil ettiği [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md) arabirimi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi halde döndürür `S_FALSE` (diğer ad bulunmazsa) veya bir hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağırmadan önce null hedef nesnesini başlatır; ardından bir null değer daha sonra diğer adı bulundu olup olmadığını belirlemek test eder.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)   
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)