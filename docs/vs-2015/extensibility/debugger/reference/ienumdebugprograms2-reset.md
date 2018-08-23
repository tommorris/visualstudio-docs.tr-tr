---
title: IEnumDebugPrograms2::Reset | Microsoft Docs
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
- IEnumDebugPrograms2::Reset
helpviewer_keywords:
- IEnumDebugPrograms2::Reset
ms.assetid: b289242b-24ea-4df3-a811-20b0c8a903d6
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: af27fc1d8edf12bc06e24cdd5b29c01274e57790
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694415"
---
# <a name="ienumdebugprograms2reset"></a>IEnumDebugPrograms2::Reset
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IEnumDebugPrograms2::Reset](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumdebugprograms2-reset).  
  
Numaralandırma ilk öğeyi sıfırlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT Reset(  
   void  
);  
```  
  
```csharp  
int Reset();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem çağrıldığında sonra yapılan sonraki çağrıda [sonraki](../../../extensibility/debugger/reference/ienumdebugprograms2-next.md) yöntemi numaralandırma ilk öğeyi döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IEnumDebugPrograms2](../../../extensibility/debugger/reference/ienumdebugprograms2.md)

