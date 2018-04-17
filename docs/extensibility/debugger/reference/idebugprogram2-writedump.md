---
title: IDebugProgram2::WriteDump | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::WriteDump
helpviewer_keywords:
- IDebugProgram2::WriteDump
ms.assetid: 375afb8c-882d-44db-bfa7-e2c9eb555122
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0b17d75ace19ac53cbcd229d7c15de573c1ecb8b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprogram2writedump"></a>IDebugProgram2::WriteDump
Bir döküm bir dosyaya yazar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT WriteDump(   
   DUMPTYPE  DumpType,  
   LPCOLESTR pszDumpUrl  
);  
```  
  
```csharp  
int WriteDump(   
   enum_DUMPTYPE  DumpType,  
   string         pszDumpUrl  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `DumpType`  
 [in] Arasında bir değer [DUMPTYPE](../../../extensibility/debugger/reference/dumptype.md) dökümü, türünü belirtir. Örneğin, kısa numaralandırma veya uzun süre.  
  
 `pszDumpUrl`  
 [in] Döküm yazmak için URL. Genellikle, bu biçimindedir `file://c:\path\filename.ext`, ancak geçerli bir URL olabilir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir program dökümü genellikle içerir geçerli yığın çerçevesini, yığını, program ve büyük olasılıkla program sahip tüm bellek çalışan iş parçacıklarının listesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)