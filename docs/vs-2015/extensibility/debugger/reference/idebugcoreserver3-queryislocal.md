---
title: IDebugCoreServer3::QueryIsLocal | Microsoft Docs
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
- IDebugCoreServer3::QueryIsLocal
helpviewer_keywords:
- IDebugCoreServer3::QueryIsLocal
ms.assetid: cca030de-f853-4ed7-b2fb-395f08a6b884
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8161e1cd1930e8f1c5c8a9f27202079a52417bbf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686648"
---
# <a name="idebugcoreserver3queryislocal"></a>IDebugCoreServer3::QueryIsLocal
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugCoreServer3::QueryIsLocal](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugcoreserver3-queryislocal).  
  
Sunucu çağırana yerel olup olmadığını belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT QueryIsLocal(  
   void  
);  
```  
  
```csharp  
int QueryIsLocal();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` sunucu yerel olduğunu belirtmek için. Döndürür `S_FALSE` sunucu örneğinden genellikle uzaktan hata ayıklama için kullanılan msvsmon.exe çalıştırıyorsa.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)

