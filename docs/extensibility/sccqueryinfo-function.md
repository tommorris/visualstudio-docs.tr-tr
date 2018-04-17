---
title: SccQueryInfo işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccQueryInfo
helpviewer_keywords:
- SccQueryInfo function
ms.assetid: 3973d336-a9b7-41a2-a4e6-bb8184a96aaf
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5e2838709d7c2c2ad6e6b1eeef36c2cc0018a1a1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="sccqueryinfo-function"></a>SccQueryInfo işlevi
Bu işlev, seçilen dosyaları kaynak denetimi altında bir dizi durum bilgilerini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccQueryInfo(  
   LPVOID  pvContext,  
   LONG    nFiles,  
   LPCSTR* lpFileNames,  
   LPLONG  lpStatus  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pvContext  
 [in] Kaynak Denetim eklentisi bağlam yapısı.  
  
 nFiles  
 [in] Belirtilen dosya sayısı `lpFileNames` dizi ve uzunluğu `lpStatus` dizi.  
  
 lpFileNames  
 [in] Sorgulanacak dosyaların adlarını dizisi.  
  
 lpStatus  
 [içinde out] Bir dizi eklenti kaynak denetimi her dosya için durumu bayrakları döndürür. Daha fazla bilgi için bkz: [dosya durum kodu](../extensibility/file-status-code-enumerator.md).  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Sorgu başarılı oldu.|  
|SCC_E_ACCESSFAILURE|Büyük olasılıkla ağ veya Çekişme sorunları neden kaynak denetim sistemi erişim ile ilgili bir sorun oluştu. Yeniden deneme önerilir.|  
|SCC_E_PROJNOTOPEN|Proje kaynak denetimi altında açık değil.|  
|SCC_E_NONSPECIFICERROR|Belirli olmayan hata oluştu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa `lpFileName` boş bir dize var. şu anda güncelleştirmek için durum bilgisi yok. Aksi halde, durum bilgileri değişmiş olabilir dosyasının tam yolu adı değil.  
  
 Dönüş dizisi, bir bit maskesi olabilir `SCC_STATUS_xxxx` BITS. Daha fazla bilgi için bkz: [dosya durum kodu](../extensibility/file-status-code-enumerator.md). Kaynak denetim sistemi tüm bit türlerini desteklemiyor olabilir. Örneğin, varsa `SCC_STATUS_OUTOFDATE` değil sunulur, bit yalnızca ayarlanmadı.  
  
 Bu işlev dosyalar kullanıma kullanırken, aşağıdakileri göz önünde bulundurun `MSSCCI` durumu gereksinimleri:  
  
-   `SCC_STATUS_OUTBYUSER` Geçerli kullanıcının dosyayı kullanıma işaretlendiğinde ayarlanır.  
  
-   `SCC_STATUS_CHECKEDOUT` sürece ayarlanamaz `SCC_STATUS_OUTBYUSER` ayarlanır.  
  
-   `SCC_STATUS_CHECKEDOUT` dosyanın belirtilen çalışma dizinine kullanıma yalnızca ayarlanır.  
  
-   Dosya geçerli kullanıcı tarafından çalışma dizini dışındaki bir dizine kullanıma durumdaysa `SCC_STATUS_OUTBYUSER` ayarlanır, ancak `SCC_STATUS_CHECKEDOUT` değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [Dosya durum kodu](../extensibility/file-status-code-enumerator.md)