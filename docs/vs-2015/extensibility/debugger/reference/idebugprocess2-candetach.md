---
title: IDebugProcess2::CanDetach | Microsoft Docs
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
- IDebugProcess2::CanDetach
helpviewer_keywords:
- IDebugProcess2::CanDetach
ms.assetid: 2830f7c3-69fb-474a-97b8-5b869e38d546
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 46a9a877269b3bdb56b9bfb8e8d8279de85ab25f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695332"
---
# <a name="idebugprocess2candetach"></a>IDebugProcess2::CanDetach
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugProcess2::CanDetach](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprocess2-candetach).  
  
Oturum hata ayıklama Yöneticisi (SDM) bir işlem ayırabilirsiniz belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT CanDetach(  
   void  
);  
```  
  
```csharp  
int CanDetach();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK.` döndürür `S_FALSE` hata ayıklayıcı işlemden ayırma yapılamıyor. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CanDetach](../../../extensibility/debugger/reference/idebugprogram2-candetach.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)

