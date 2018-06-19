---
title: IDebugProcess3::DisableENC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProcess3::DisableENC
helpviewer_keywords:
- IDebugProcess3::DisableENC
ms.assetid: cffdbdac-4d76-4aeb-aa55-5d0410db99f1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2da464c82332f6fc4f9bcd57ee8197e111e9fa0a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31116636"
---
# <a name="idebugprocess3disableenc"></a>IDebugProcess3::DisableENC
Bu yöntem açıkça devre dışı bırakır düzenleyin ve bu işlemi devam (ve tüm programları içerir). Özel bir bağlantı noktası tedarikçi her zaman döndürmelidir `E_NOTIMPL`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT DisableENC(  
   EncUnavailableReason reason  
);  
```  
  
```csharp  
   EncUnavailableReason reason  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `reason`  
 [in] Arasında bir değer [EncUnavailableReason](../../../extensibility/debugger/reference/encunavailablereason.md) numaralandırması.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde, hata kodunu döndürür.  
  
> [!NOTE]
>  Özel bir bağlantı noktası tedarikçi her zaman döndürmelidir `E_NOTIMPL`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir kez Düzenle ve devam bir işlem için devre dışı, bu işlem yalnızca yeniden başlatarak yeniden etkinleştirilebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [EncUnavailableReason](../../../extensibility/debugger/reference/encunavailablereason.md)