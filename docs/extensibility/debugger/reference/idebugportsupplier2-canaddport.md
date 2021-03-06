---
title: IDebugPortSupplier2::CanAddPort | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugPortSupplier2::CanAddPort
helpviewer_keywords:
- IDebugPortSupplier2::CanAddPort
ms.assetid: 41f69e0a-e82c-473d-8b7a-0c40fc5730fc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 00b1c1303be8ccc326a58a20d132ad38db3b426d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31113968"
---
# <a name="idebugportsupplier2canaddport"></a>IDebugPortSupplier2::CanAddPort
Bir bağlantı noktası tedarikçi yeni bağlantı noktaları ekleyebilirsiniz doğrular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT CanAddPort(   
   void   
);  
```  
  
```csharp  
int CanAddPort();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bağlantı noktası eklenebiliyorsa döndürür `S_OK`; Aksi halde döndürür `S_FALSE` hiçbir bağlantı noktası Bu bağlantı noktası tedarikçiye eklenebilir belirtmek için.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağırmadan önce çağırın [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md) ikinci yöntemi bağlantı noktasının yanı sıra, hangi uzun süren bir işlem olabilir ekleme oluşturduğundan yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)