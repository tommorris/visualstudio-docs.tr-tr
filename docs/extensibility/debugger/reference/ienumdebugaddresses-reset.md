---
title: IEnumDebugAddresses::Reset | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IEnumDebugAddresses::Reset
helpviewer_keywords:
- IEnumDebugAddresses::Reset method
ms.assetid: 3a9d7f20-5bc6-4e13-8e91-5af4092e092f
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: e38329fd8f6e460111b9052264c92c189a7f5454
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdebugaddressesreset"></a>IEnumDebugAddresses::Reset
Bu yöntem ilk öğeye numaralandırması sıfırlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Reset(void);  
```  
  
```csharp  
int Reset();  
```  
  
#### <a name="parameters"></a>Parametreler  
 Yok.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağrıldıktan sonra sonraki çağrısı [sonraki](../../../extensibility/debugger/reference/ienumdebugaddresses-next.md) sabit listesinin ilk öğesini döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)   
 [Next](../../../extensibility/debugger/reference/ienumdebugaddresses-next.md)