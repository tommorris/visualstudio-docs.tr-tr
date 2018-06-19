---
title: IEnumCodePaths2::Reset | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IEnumCodePaths2::Reset
helpviewer_keywords:
- IEnumCodePaths2::Reset
ms.assetid: 490c0e19-ff4b-4673-bd06-cdee996ac226
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8f32c3cef0d92c0f48a765106ee532a3e4992ec4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31121046"
---
# <a name="ienumcodepaths2reset"></a>IEnumCodePaths2::Reset
Numaralandırma ilk öğeye sıfırlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Reset(  
   void  
);  
```  
  
```csharp  
int Reset();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağrıldıktan sonra sonraki çağrısı [sonraki](../../../extensibility/debugger/reference/ienumcodepaths2-next.md) yöntemi numaralandırması ilk öğesi döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IEnumCodePaths2](../../../extensibility/debugger/reference/ienumcodepaths2.md)