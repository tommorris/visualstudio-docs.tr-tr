---
title: IDebugProgramHost2::GetHostName | Microsoft Docs
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
- IDebugProgramHost2::GetHostName
helpviewer_keywords:
- IDebugProgramHost2::GetHostName
ms.assetid: 48bbb089-e59a-471a-9965-24b42a8dabf3
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 420a25be81a124c89bc4139d80ae881b1f519726
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691448"
---
# <a name="idebugprogramhost2gethostname"></a>IDebugProgramHost2::GetHostName
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugProgramHost2::GetHostName](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprogramhost2-gethostname).  
  
Başlık, kolay ad veya bu programın barındırma işlemi dosya adını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT GetHostName(   
   DWORD dwType,  
   BSTR* pbstrHostName  
);  
```  
  
```csharp  
int GetHostName(   
   uint dwType,  
   out string pbstrHostName  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dwType`  
 [in] Bir değer [GETHOSTNAME_TYPE](../../../extensibility/debugger/reference/gethostname-type.md) sabit listesi.  
  
 `pbstrHostName`  
 [out] Barındırma işlemi istenen adını döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntemin tipik bir uygulamada `dwType` parametresi yok sayıldı ve bir kolay ad konak makinenin döndürülür. Başka bir olası uygulama geçirmektir `dwType` çağrı için parametre [GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md) adı almak için yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProgramHost2](../../../extensibility/debugger/reference/idebugprogramhost2.md)   
 [GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md)

