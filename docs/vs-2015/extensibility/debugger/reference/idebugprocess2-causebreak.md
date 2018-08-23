---
title: IDebugProcess2::CauseBreak | Microsoft Docs
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
- IDebugProcess2::CauseBreak
helpviewer_keywords:
- IDebugProcess2::CauseBreak
ms.assetid: efda8865-2319-4d53-90bf-6d9d74cd5195
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9d50452e234ea56631c1c77eabff372a63f01e4d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687959"
---
# <a name="idebugprocess2causebreak"></a>IDebugProcess2::CauseBreak
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugProcess2::CauseBreak](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprocess2-causebreak).  
  
Sonraki diğer bir deyişle bu işlemde çalışan kod program isteklerini durdurmak ve gönderme bir [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md) olay nesnesi.  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)

