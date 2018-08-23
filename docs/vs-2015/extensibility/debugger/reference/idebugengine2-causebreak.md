---
title: IDebugEngine2::CauseBreak | Microsoft Docs
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
- IDebugEngine2::CauseBreak
helpviewer_keywords:
- IDebugEngine2::CauseBreak
ms.assetid: 17fe4698-b04e-4798-8412-80e0da60c387
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c568fb753dd86680f8942a97c46e78ae31fc7cf5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686293"
---
# <a name="idebugengine2causebreak"></a>IDebugEngine2::CauseBreak
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugEngine2::CauseBreak](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugengine2-causebreak).  
  
Tüm programları bu hata ayıklama altyapısı yürütme sonraki durdurmak için (DE) hata ayıklaması yapılan istekleri, iş parçacıkları birini çalıştırmayı dener.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT CauseBreak(   
   void   
);  
```  
  
```csharp  
int CauseBreak();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu zaman uyumsuz bir yöntemdir: bir [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md) program bu yöntem çağrıldıktan sonra yürütülecek sonraki denediğinde olay gönderilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)   
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)

