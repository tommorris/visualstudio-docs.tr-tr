---
title: IDebugProgram2::GetProgramId | Microsoft Docs
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
- IDebugProgram2::GetProgramId
helpviewer_keywords:
- IDebugProgram2::GetProgramId
ms.assetid: 2c31c0aa-2b71-46c7-849c-356e237d26f8
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ec9805ef49da0331689f34e1657327f2a836b834
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687781"
---
# <a name="idebugprogram2getprogramid"></a>IDebugProgram2::GetProgramId
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugProgram2::GetProgramId](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprogram2-getprogramid).  
  
Bu program için bir GUID alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT GetProgramId(   
   GUID* pguidProgramId  
);  
```  
  
```csharp  
int GetProgramId(   
   out Guid pguidProgramId  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pguidProgramId`  
 [out] Döndürür `GUID` Bu program için.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Hata ayıklama altyapısı (DE) geçirilen ilk program tanımlayıcısı döndürmelidir [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) veya [iliştirme](../../../extensibility/debugger/reference/idebugengine2-attach.md) yöntemleri. Bu program kimliği arasında hata ayıklayıcı bileşenleri sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)   
 [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)

