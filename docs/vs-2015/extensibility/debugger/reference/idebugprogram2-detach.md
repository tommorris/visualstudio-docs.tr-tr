---
title: IDebugProgram2::Detach | Microsoft Docs
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
- IDebugProgram2::Detach
helpviewer_keywords:
- IDebugProgram2::Detach
ms.assetid: 5e8d88b0-a8d4-4746-88c0-ad332ee73f33
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 610b96c22e1fa64a0434b0b8bbdaeec506373135
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692917"
---
# <a name="idebugprogram2detach"></a>IDebugProgram2::Detach
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugProgram2::Detach](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprogram2-detach).  
  
Programın hata ayıklama altyapısından ayırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT Detach(   
   void   
);  
```  
  
```csharp  
int Detach();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Ayrılmış bir program çalışmaya devam eder, ancak artık hata ayıklama oturumunun parçası değildir. Hata ayıklama altyapısı ayrılmış sonra daha fazla program hata ayıklama olay gönderilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)

