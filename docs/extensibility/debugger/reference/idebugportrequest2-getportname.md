---
title: IDebugPortRequest2::GetPortName | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugPortRequest2::GetPortName
helpviewer_keywords: IDebugPortRequest2::GetPortName
ms.assetid: 53e2a3a4-bb34-4a02-a983-6bd84ea70587
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ab94c9bcb0ec686b9b2d8aba7378bbd55ca71c72
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugportrequest2getportname"></a>IDebugPortRequest2::GetPortName
Bağlantı noktası adını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetPortName(   
   BSTR* pbstrPortName  
);  
```  
  
```csharp  
int GetPortName(   
   out string pbstrPortName  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pbstrPortName`  
 [out] Bağlantı noktası adını döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md) arabirimi genellikle geçirilir hata ayıklama paketinden (istemci) bir bağlantı almak için bir bağlantı noktası tedarikçiye (sunucu) bir bağlantı noktası. Hata ayıklama paketi ve bağlantı noktası sağlayıcı bağlantı noktası için olası seçenekleri farkında. Bağlantı noktası, basit bir dize tanımlayabilir, sonra `IDebugPortRequest2::GetPortName` yöntemi bağlantı oluşturmak için yeterli bilgi sahiptir. Aksi durumda, ek arabirimler sunucusu kullanılarak alınabilir istemci tarafından sağlanabilir `IDebugPortRequest2::QueryInterface`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)