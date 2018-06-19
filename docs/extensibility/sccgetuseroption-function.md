---
title: SccGetUserOption işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccGetUserOption
helpviewer_keywords:
- SccGetUserOption function
ms.assetid: 17863747-1901-4c53-a2b3-ed996085e120
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b735b8ae53ef484417ae007c6ec74ec03fe4b849
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31136516"
---
# <a name="sccgetuseroption-function"></a>SccGetUserOption işlevi
Bu işlev, çeşitli kullanıcıya özgü seçenekleri alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccGetUserOption(  
   LPVOID pContext,  
   LONG nOption,  
   LPLONG lpVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pContext  
 [in] Kaynak Denetim eklentisi bağlam işaretçi.  
  
 nOption  
 [in] (Açıklamalar için olası seçenekleri bakın) almak için seçeneği.  
  
 lpVal  
 [out] Seçeneği ile ilişkili değer.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Seçeneği başarıyla alındı.|  
|SCC_E_OPNOTSUPPORTED|Seçeneği desteklenmez.|  
|SCC_E_NONSPECIFICERROR|Belirlenemeyen bir hata oluştu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Aşağıdaki seçenekler, bu komut tarafından desteklenir:  
  
|Kullanıcı seçeneği|Açıklama|  
|-----------------|-----------------|  
|`SCC_USEROPT_CHECKOUT_LOCALVER`|Kullanıcının dosyaları yerel sürümlerini kullanıma almak istediği olup olmadığını belirler. `lpVal` atanan `SCC_USEROPT_COLV_YES` (kullanıcının istediği yerel dosyalar kullanıma) veya `SCC_USEROPT_COLV_NO`.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [Hata Kodları](../extensibility/error-codes.md)