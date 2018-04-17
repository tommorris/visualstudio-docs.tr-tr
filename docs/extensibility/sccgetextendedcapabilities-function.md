---
title: SccGetExtendedCapabilities işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccGetExtendedCapabilities
helpviewer_keywords:
- SccGetExtendedCapabilities function
ms.assetid: 588c6a92-2147-4d8b-a357-96ca7da0a092
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 46ae3e051028e8239be5949500ebb710d67eee17
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="sccgetextendedcapabilities-function"></a>SccGetExtendedCapabilities işlevi
Bu işlev, kaynak denetimi eklentisi tarafından desteklenen ek özellikleri döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccGetExtendedCapabilities(  
   LPVOID pContext,  
   LONG lSccExCaps,  
   LPBOOL pbSupported  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pContext  
 [in] Kaynak Denetim eklentisi bağlam işaretçi.  
  
 lSccExCaps  
 [in] Hangi test etmek için bir genişletilmiş özelliği belirten bir bayrak (genişletilmiş özellik kodu tablosunda görmek [yetenek bayrakları](../extensibility/capability-flags.md) olası bayraklar için).  
  
 pbSupported  
 [out] Sıfır olmayan döndürür (`TRUE`) belirtilen yeteneği destekleniyorsa; Aksi halde, sıfır döndürür (`FALSE`).  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Get yetenek işlemi başarıyla tamamlandı.|  
|SCC_E_UNKNOWNERROR<br /><br /> SCC_E_NONSPECIFICERROR|Bilinmeyen veya belirtilmeyen bir hata oluştu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem, isteğe bağlı olarak adlandırılır; bir yetenek sınanacak gerektiğinde, diğer bir deyişle, bu yöntem belirlemek için yetenek desteklenen çağrılır. Bir seferde yalnızca bir bayrağı belirtilmiş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [Hata kodları](../extensibility/error-codes.md)   
 [Özellik Bayrakları](../extensibility/capability-flags.md)