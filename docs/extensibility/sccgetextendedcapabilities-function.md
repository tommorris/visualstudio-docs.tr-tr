---
title: "SccGetExtendedCapabilities işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SccGetExtendedCapabilities
helpviewer_keywords:
- SccGetExtendedCapabilities function
ms.assetid: 588c6a92-2147-4d8b-a357-96ca7da0a092
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 870d793a11cccdaae9657deabb0e3b08c4d8c6f5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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