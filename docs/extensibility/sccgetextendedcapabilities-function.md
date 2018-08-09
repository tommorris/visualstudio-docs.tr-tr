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
ms.openlocfilehash: e7fd4a42b9c94cb2470f6e7dc7b4904aa890e8a6
ms.sourcegitcommit: 06db1892fff22572f0b0a11994dc547c2b7e2a48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39637792"
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
  
### <a name="parameters"></a>Parametreler  
 pContext  
 [in] Kaynak Denetimi Eklentisi bağlam işaretçisi.  
  
 lSccExCaps  
 [in] Test etmek istediğiniz genişletilmiş bir özellik belirten bir bayrak (genişletilmiş özelliği kodu tablosuna bakın [özellik bayrakları](../extensibility/capability-flags.md) olası bayrakları için).  
  
 pbSupported  
 [out] Sıfır olmayan döndürür (`TRUE`) belirtilen yeteneği desteklenir; Aksi takdirde, sıfır döndürür (`FALSE`).  
  
## <a name="return-value"></a>Dönüş değeri  
 Kaynak Denetimi Eklentisi uygulanması bu işlev, aşağıdaki değerlerden birini döndürmesi beklenir:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Alma özelliği işlemi başarıyla tamamlandı.|  
|SCC_E_UNKNOWNERROR<br /><br /> SCC_E_NONSPECIFICERROR|Bilinmeyen veya belirtilmeyen bir hata oluştu.|  
  
## <a name="remarks"></a>Açıklamalar  
 İsteğe bağlı olarak bu yöntem çağrılır; Test edilecek bir yetenek gerektiğinde, diğer bir deyişle, bu yöntem belirlemek için özellik desteklenen çağrılır. Aynı anda yalnızca bir bayrağı belirtilmiş.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Kaynak Denetimi Eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [Hata kodları](../extensibility/error-codes.md)   
 [Özellik bayrakları](../extensibility/capability-flags.md)