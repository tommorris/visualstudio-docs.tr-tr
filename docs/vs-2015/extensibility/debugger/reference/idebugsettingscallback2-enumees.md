---
title: IDebugSettingsCallback2::EnumEEs | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugSettingsCallback2::EnumEEs
ms.assetid: 9f884c49-426f-461b-b547-9d909486e73f
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: afc9337ac2312c356fe5ea6fcbe9cfb492ea5221
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629177"
---
# <a name="idebugsettingscallback2enumees"></a>IDebugSettingsCallback2::EnumEEs
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugSettingsCallback2::EnumEEs](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugsettingscallback2-enumees).  
  
Dil ve satıcı tanımlayıcıları verilen kullanılabilir ifade değerlendiricilerini numaralandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT EnumEEs(  
   DWORD  celtBuffer,  
   GUID*  rgguidLang,  
   GUID*  rgguidVendor,  
   DWORD* pceltEEs  
);  
```  
  
```csharp  
public int EnumEEs(  
   uint       celtBuffer,  
   ref Guid   rgguidLang,  
   ref Guid   rgguidVendor,  
   ref uint[] pceltEEs  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `celtBuffer`  
 [in] İçindeki öğelerin sayısını `pceltEEs` arabellek.  
  
 `rgguidLang`  
 [out içinde] Programlama dili için benzersiz tanımlayıcı.  
  
 `rgguidVendor`  
 [out içinde] Satıcı için benzersiz tanımlayıcı.  
  
 `pceltEEs`  
 [out içinde] İfade değerlendiricilerini dizisi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)

