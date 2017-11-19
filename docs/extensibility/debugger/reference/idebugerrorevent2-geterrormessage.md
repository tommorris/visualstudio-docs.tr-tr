---
title: IDebugErrorEvent2::GetErrorMessage | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugErrorEvent2::GetErrorMessage
helpviewer_keywords: IDebugErrorEvent2::GetErrorMessage
ms.assetid: 9e3b0d74-a2dd-4eaa-bd95-21b2f9c79409
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0b8a4e4c2ca938d8c600d3fd9ef0e615aa847fd9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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