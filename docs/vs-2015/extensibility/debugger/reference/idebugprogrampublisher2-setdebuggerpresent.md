---
title: IDebugProgramPublisher2::SetDebuggerPresent | Microsoft Docs
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
- IDebugProgramPublisher2::SetDebuggerPresent
helpviewer_keywords:
- IDebugProgramPublisher2::SetDebuggerPresent
ms.assetid: c88c3ff4-3632-4199-b5de-83c6d21bcf75
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 86351bda9d221200e9c84c2e1fb3590c451c57e8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691404"
---
# <a name="idebugprogrampublisher2setdebuggerpresent"></a>IDebugProgramPublisher2::SetDebuggerPresent
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugProgramPublisher2::SetDebuggerPresent](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprogrampublisher2-setdebuggerpresent).  
  
Program yayımcı, bir hata ayıklayıcı mevcut ve çalışıyor olduğunu söyler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT SetDebuggerPresent(  
   BOOL fDebuggerPresent  
);  
```  
  
```csharp  
int SetDebuggerPresent(  
   int fDebuggerPresent  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `fDebuggerPresent`  
 [in] Sıfır olmayan (`TRUE`) bir hata ayıklayıcı varsa, sıfır (`FALSE`), değilse.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Döndürülen veri varlığı veya yokluğu bir hata ayıklayıcı yansıtılır [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md) yöntemi: var. döndürülen değer kümesi veya önceki bir çağrı tarafından temizlenmiş `SetDebuggerPresent` yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProgramPublisher2](../../../extensibility/debugger/reference/idebugprogrampublisher2.md)   
 [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)

