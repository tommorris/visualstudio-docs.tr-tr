---
title: IDebugProcess2::Detach | Microsoft Docs
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
- IDebugProcess2::Detach
helpviewer_keywords:
- IDebugProcess2::Detach
ms.assetid: ee2b9084-2db1-4e49-a1d9-387284b7c3f8
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1895c146f557e0c3ba79bd84970b99fc663cc891
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42683746"
---
# <a name="idebugprocess2detach"></a>IDebugProcess2::Detach
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugProcess2::Detach](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprocess2-detach).  
  
İşlemdeki tüm programları ayırıp hata ayıklayıcı bu işlemden ayırır.  
  
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
 Tüm programları ve işlem çalışmaya devam eder, ancak artık hata ayıklama oturumunun parçası olmayan. Ayırma işlemi bu işlemi (ve programları) için olayları gönderilecek tam, daha fazla hata ayıklama sonra.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)

