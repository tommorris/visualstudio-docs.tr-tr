---
title: IDebugProcessEx2::Detach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProcessEx2::Detach
helpviewer_keywords: IDebugProcessEx2::Detach method
ms.assetid: 66d54c2c-9302-47c8-9975-f30ed988ab29
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d810008391398741e644da7215de174918db604f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprocessex2detach"></a>IDebugProcessEx2::Detach
Bu yöntem, bir oturum işlemi artık hata ayıklamayı işlem sizi bilgilendirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Detach(   
   IDebugSession2* pSession  
);  
```  
  
```csharp  
int Detach(  
   IDebugSession2 pSession  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pSession`  
 [in] Bu işlemin dışında ayırmak için oturumu benzersiz olarak tanımlayan bir değer.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Arabirim geçirilen `pSession` oturum hata ayıklama Yöneticisi, ilk olarak tanıtan bir değer yalnızca bir tanımlama bilgisi olarak kabul edilmesi için bu işlem için bağlı; sağlanan arabirimde yöntemlerin hiçbiri işlevsel olur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProcessEx2](../../../extensibility/debugger/reference/idebugprocessex2.md)