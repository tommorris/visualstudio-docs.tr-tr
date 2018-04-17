---
title: IDebugEnumField::GetStringFromValue | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEnumField::GetStringFromValue
helpviewer_keywords:
- IDebugEnumField::GetStringFromValue method
ms.assetid: 5f95fd0c-fdce-497f-9f54-2ad8749494e9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a0b7ac4f7cde93d4637906202f7b4c643750d8e0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugenumfieldgetstringfromvalue"></a>IDebugEnumField::GetStringFromValue
Bu yöntem değerini verilen numaralandırma sabiti adını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetStringFromValue(  
   ULONGLONG value,  
   BSTR*     pbstrValue  
);  
```  
  
```csharp  
int GetStringFromValue(  
   ulong      value,  
   out string pbstrValue  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `value`  
 [in] Numaralandırma adını sabit almak istediğiniz için değer.  
  
 `pbstrValue`  
 [out] Numaralandırma sabiti adını döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi halde döndürür `S_FALSE` değeri ilişkili adı yok ya da bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Sabit listede tanımlanan ilk ad aynı değeriyle ilişkili birden fazla adı varsa, döndürülür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)