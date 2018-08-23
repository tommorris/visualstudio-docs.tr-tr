---
title: SccWillCreateSccFile işlevi | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SccWillCreateSccFile
helpviewer_keywords:
- SccWillCreateSccFile function
ms.assetid: 0d7542f0-4351-41b3-b24c-960ab99c05a1
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 79fd34f742309fe94a329e75d78a57cf551b3a85
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684342"
---
# <a name="sccwillcreatesccfile-function"></a>SccWillCreateSccFile İşlevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [SccWillCreateSccFile işlevi](https://docs.microsoft.com/visualstudio/extensibility/sccwillcreatesccfile-function).  
  
Bu işlev, kaynak denetimi eklentisi MSSCCPRJ oluşturulmasını destekleyip desteklemediğini belirler. SCC dosyası belirli dosyaların her biri için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
SCCRTN SccWillCreateSccFile(  
   LPVOID  pContext,  
   LONG    nFiles,  
   LPCSTR* lpFileNames,  
   LPBOOL  pbSccFiles  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pContext  
 [in] Kaynak Denetimi Eklentisi bağlam işaretçisi.  
  
 nFiles  
 [in] Dosya adlarını dahil sayısını `lpFileNames` dizi uzunluğu yanı sıra `pbSccFiles` dizisi.  
  
 lpFileNames  
 [in] Bir dizi kontrol etmek için tam olarak nitelenmiş dosya adını (dizisi gerekir ayrılan çağıran tarafından).  
  
 pbSccFiles  
 [out içinde] Sonuçları depolanacağı dizisi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Kaynak Denetimi Eklentisi uygulanması bu işlev, aşağıdaki değerlerden birini döndürmesi beklenir:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Başarılı.|  
|SCC_E_INVALIDFILEPATH|Dizideki yollardan biri geçersiz.|  
|SCC_E_NONSPECIFICERROR|Belirli olmayan hata oluştu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev, kaynak denetimi eklentisi MSSCCPRJ desteği sağlayıp sağlamadığını belirlemek için dosyaların listesiyle birlikte çağrılır. SCC dosya her belirli dosyaları (MSSCCPRJ hakkında daha fazla bilgi. SCC dosya bkz [MSSCCPRJ. SCC dosya](../extensibility/mssccprj-scc-file.md)). Kaynak denetimi eklentileri MSSCCPRJ oluşturma yeteneğine sahip olup olmadığını bildirebilir. SCC dosyaları bildirme `SCC_CAP_SCCFILE` başlatma sırasında. Eklenti döndürür `TRUE` veya `FALSE` dosya başına `pbSccFiles` MSSCCPRJ sahip olduğu belirli dosyaları belirtmek için bir dizi. SCC desteği. Eklenti, işlevden bir başarı kodu döndürürse, dönüş dizideki değerleri dikkate alınır. Hata durumunda, dizi göz ardı edilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [MSSCCPRJ.SCC Dosyası](../extensibility/mssccprj-scc-file.md)

