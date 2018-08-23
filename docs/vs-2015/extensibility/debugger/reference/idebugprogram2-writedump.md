---
title: IDebugProgram2::WriteDump | Microsoft Docs
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
- IDebugProgram2::WriteDump
helpviewer_keywords:
- IDebugProgram2::WriteDump
ms.assetid: 375afb8c-882d-44db-bfa7-e2c9eb555122
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8708751820ca70386e6c9927105384eee9a96a15
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694486"
---
# <a name="idebugprogram2writedump"></a>IDebugProgram2::WriteDump
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugProgram2::WriteDump](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprogram2-writedump).  
  
Bir döküm bir dosyaya yazar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
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
 [in] Bir değer [DUMPTYPE](../../../extensibility/debugger/reference/dumptype.md) Örneğin, kısa döküm, türünü belirten sabit listesi veya uzun süre.  
  
 `pszDumpUrl`  
 [in] Döküm için yazma URL'si. Genellikle, bu biçimindedir `file://c:\path\filename.ext`, ancak geçerli bir URL olabilir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir program dökümü genellikle verilebilir geçerli yığın çerçevesi yığın, program ve program sahip büyük olasılıkla herhangi bir bellek çalışan iş parçacıkları listesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)

