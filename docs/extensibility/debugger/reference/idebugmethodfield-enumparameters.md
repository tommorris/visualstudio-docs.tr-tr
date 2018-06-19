---
title: IDebugMethodField::EnumParameters | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugMethodField::EnumParameters
helpviewer_keywords:
- IDebugMethodField::EnumParameters method
ms.assetid: d77b1197-deb6-4144-8d1b-8b09949ccfac
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 112b91c2155c28b37b2222a99a45893fcb56e98c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31122203"
---
# <a name="idebugmethodfieldenumparameters"></a>IDebugMethodField::EnumParameters
Yöntem parametreleri için bir numaralandırıcı oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT EnumParameters(   
   IEnumDebugFields** ppParams  
);  
```  
  
```csharp  
int EnumParameters(  
   out IEnumDebugFields ppParams  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppParams`  
 [out] Döndüren bir [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) parametresiz varsa, boş bir değer döndürür; yönteme parametre listesini temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK döndürür veya parametresiz varsa S_FALSE döndürür. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Her öğe bir [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) parametreleri farklı türlerde temsil eden nesne. Çağrı [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) tam olarak ne tür parametresi bir nesneyi temsil ediyor belirlemek için her bir nesne üzerinde yöntemi.  
  
 Bir parametre değişken adını ve türünü içerir. İlk parametre olarak bir sınıf yöntemi genellikle "Bu" işaretçidir.  
  
 Yalnızca bir parametre türlerini gereklidir, çağrı [EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md)