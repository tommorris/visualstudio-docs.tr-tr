---
title: IDebugArrayField::GetRank | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugArrayField::GetRank
helpviewer_keywords:
- IDebugArrayField::GetRank method
ms.assetid: 2364b876-5be1-4bab-9b8f-3b6121da35c6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4fee642bb5f19efb62b631d71d3ba95eec45c0be
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugarrayfieldgetrank"></a>IDebugArrayField::GetRank
Derece veya dizinin boyut sayısını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetRank(   
   DWORD* pdwRank  
);  
```  
  
```csharp  
int GetRank(  
   out uint pdwRank  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pdwRank`  
 [out] Derecesini döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK verir; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir dizi derecesini dimensions sayısı karşılık gelir. C++ ve C#, çok boyutlu diziler gerçekten ayrı diziler olan ve bu nedenle yalnızca bir tek boyutlu dizi kabul edilebilir (ve `GetRank` yöntem her zaman 1 döndürür). İçinde [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)], diğer yandan, çok boyutlu diziler farklı şekilde işlenir ve bu tür bir dizi derecesini boyut sayısını yansıtır (ve `GetRank` yöntem her zaman boyut sayısını döndürür).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)