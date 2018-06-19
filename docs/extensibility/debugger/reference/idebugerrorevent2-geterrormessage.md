---
title: IDebugErrorEvent2::GetErrorMessage | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugErrorEvent2::GetErrorMessage
helpviewer_keywords:
- IDebugErrorEvent2::GetErrorMessage
ms.assetid: 9e3b0d74-a2dd-4eaa-bd95-21b2f9c79409
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4dffd06c7342b77f1e4293d50217a0c6a468bf18
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31110230"
---
# <a name="idebugerrorevent2geterrormessage"></a>IDebugErrorEvent2::GetErrorMessage
Bir kullanıcı tarafından okunabilen hata iletisi yapımı sağlayan bilgileri döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetErrorMessage(  
   MESSAGETYPE* pMessageType,  
   BSTR*        pbstrErrorFormat,  
   HRESULT*     hrErrorReason,  
   DWORD*       pdwType,  
   BSTR*        pbstrHelpFileName,  
   DWORD*       pdwHelpId  
);  
```  
  
```csharp  
int GetErrorMessage(  
   out enum_MESSAGETYPE   pMessageType,  
   out string             pbstrErrorFormat,  
   out int                phrErrorReason,  
   out uint               pdwType,  
   out string             pbstrHelpFileName,  
   out uint               pdwHelpId  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pMessageType`  
 [out] Arasında bir değer döndürür [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md) ileti türünü tanımlayan numaralandırması.  
  
 `pbstrErrorFormat`  
 [out] Kullanıcı için son ileti biçimi (Ayrıntılar için bkz: "Açıklamalar").  
  
 `hrErrorReason`  
 [out] Hata iletisi hakkında kodudur.  
  
 `pdwType`  
 [out] Hata önem derecesi (için MB_XXX sabitleri kullan `MessageBox`; Örneğin, `MB_EXCLAMATION` veya `MB_WARNING`).  
  
 `pbstrHelpFileName`  
 [out] Yardım dosyası (Yardım dosyası yoksa null bir değere ayarlanırsa) yolu.  
  
 `pdwHelpId`  
 [out] (Yardım konusu yok ise 0 olarak ayarlanırsa) görüntülemek için Yardım konusu kimliği.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Hata iletisi satırları biçimlendirilmesi `"What I was doing.  %1"`. `"%1"` Sonra çağıran tarafından türetilmiş hata kodundan hata iletisini ile değiştirilmesi (içinde döndürülen `hrErrorReason`). `pMessageType` Parametresi, son hata iletisi nasıl görüntüleneceğini çağıran bildirir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md)   
 [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md)