---
title: IDebugProcessSecurity::QueryCanSafelyAttach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugProcessSecurity::QueryCanSafelyAttach
ms.assetid: 63ec1ae8-27da-4574-aa15-1c986fe9fe58
caps.latest.revision: "4"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0ad6b7ffde868bf6b9dc4f9ef3bab9d9094ab765
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprocesssecurityquerycansafelyattach"></a>IDebugProcessSecurity::QueryCanSafelyAttach
Bu yöntem, kullanıcının güvenli olmayan bir işlem ekler önce bir uyarı görüntüleyecek şekilde bağlantı noktası sağlayıcı sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT QueryCanSafelyAttach();  
```  
  
```csharp  
int QueryCanSafelyAttach();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Dönüş değerleri aşağıdaki gibidir:  
  
-   `S_OK`: İşlemine iliştirme güvendedir ve hiçbir uyarı iletişim kutusu gösterilir.  
  
-   `S_FALSE`: Ekleme bir güvenlik sorunu olabilir ve bir uyarı içeren bir iletişim kutusu gösterilir.  
  
-   `FAILURE`: İşlemine iliştirme başarısız olur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProcessSecurity](../../../extensibility/debugger/reference/idebugprocesssecurity.md)