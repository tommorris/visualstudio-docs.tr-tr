---
title: IDebugClassField::EnumBaseClasses | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugClassField::EnumBaseClasses
helpviewer_keywords:
- IDebugClassField::EnumBaseClasses method
ms.assetid: 78749674-ef75-46d3-a1f4-ff33afd90e32
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 3f62f570b489427b59aefe8153692ab8f9fc2181
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugclassfieldenumbaseclasses"></a>IDebugClassField::EnumBaseClasses
Bu sınıfın temel sınıflar için bir numaralandırıcı oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT EnumBaseClasses(   
   IEnumDebugFields** ppEnum  
);  
```  
  
```csharp  
int EnumBaseClasses(  
   out IEnumDebugFields ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppEnum`  
 [out] Döndürür bir [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) temel sınıflar listesini temsil eden nesne. Hiçbir temel sınıflar yoksa null değeri döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK döndürür, temel sınıf ise S_SH_NO_BASE_CLASSES verir (ve `ppEnum` parametresi null bir değere ayarlanırsa); Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Numaralandırıcı nesnesi temel sınıflarda çoğu uzak taban sınıfı için en yakın (veya en çok türetilen) temel sınıf sırasına göre belirtilir. Örneğin, C++ sınıfları verilen:  
  
```  
class Root { }  
class Level1 : Root { }  
class Level2 : Level1 { }  
class MyClass : Level2 { }  
```  
  
 Numaralandırma sırasını temel sınıflar döndürecektir `Level2`, `Level1`, `Root`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)