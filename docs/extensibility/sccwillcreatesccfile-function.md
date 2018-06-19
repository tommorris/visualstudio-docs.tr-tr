---
title: SccWillCreateSccFile işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccWillCreateSccFile
helpviewer_keywords:
- SccWillCreateSccFile function
ms.assetid: 0d7542f0-4351-41b3-b24c-960ab99c05a1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: af6da09badf0ffea4846d35fe00b4ca146243d64
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31137060"
---
# <a name="sccwillcreatesccfile-function"></a>SccWillCreateSccFile işlevi
Bu işlev, eklenti kaynak denetimi MSSCCPRJ oluşturulmasını destekleyip desteklemediğini belirler. Verilen dosyaların her biri için SCC dosya.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccWillCreateSccFile(  
   LPVOID  pContext,  
   LONG    nFiles,  
   LPCSTR* lpFileNames,  
   LPBOOL  pbSccFiles  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pContext  
 [in] Kaynak Denetim eklentisi bağlam işaretçi.  
  
 nFiles  
 [in] Dosya adlarını dahil sayısı `lpFileNames` dizi uzunluğu, hem de `pbSccFiles` dizi.  
  
 lpFileNames  
 [in] Bir dizi denetlemek için tam dosya adını (array gerekir ayrılan çağıran tarafından).  
  
 pbSccFiles  
 [içinde out] Sonuçların depolanacağı dizisi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Başarılı.|  
|SCC_E_INVALIDFILEPATH|Dizideki yollarından biri geçersiz.|  
|SCC_E_NONSPECIFICERROR|Belirli olmayan hata oluştu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev, eklenti kaynak denetimi MSSCCPRJ desteği sağlayıp sağlamadığını belirlemek için dosya listesini içeren çağrılır. SCC dosya her belirli dosyaları (MSSCCPRJ hakkında daha fazla bilgi. SCC dosya bkz [MSSCCPRJ. SCC dosya](../extensibility/mssccprj-scc-file.md)). Kaynak Denetim Eklentileri MSSCCPRJ oluşturma yeteneğine sahip olup olmadığını bildirebilir. Bildirme SCC dosyaları `SCC_CAP_SCCFILE` başlatma sırasında. Eklenti döndürür `TRUE` veya `FALSE` dosya başına `pbSccFiles` MSSCCPRJ sahip olduğunuz belirli dosyaları belirtmek için dizi. SCC desteği. Eklenti, işlevinden başarı kodu döndürürse, dönüş dizideki dikkate alınır. Hatada, dizi göz ardı edilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [MSSCCPRJ.SCC Dosyası](../extensibility/mssccprj-scc-file.md)