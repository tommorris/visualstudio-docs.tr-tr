---
title: SccGetEvents işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccGetEvents
helpviewer_keywords:
- SccGetEvents function
ms.assetid: 32f8147d-6dcc-465e-b07b-42da5824f9b0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 79e517d87acd61eafcd2eb0a12f5a8978912db81
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="sccgetevents-function"></a>SccGetEvents işlevi
Bu işlev bir Sıraya alınan durum olayı alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccGetEvents (  
   LPVOID pvContext,  
   LPSTR  lpFileName,  
   LPLONG lpStatus,  
   LPLONG pnEventsRemaining  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pvContext  
 [in] Kaynak Denetim eklentisi bağlam yapısı.  
  
 lpDosyaAdı  
 [içinde out] Arabellek eklenti kaynak denetimi döndürülen dosya adına (kadar _MAX_PATH karakter) yere koyar.  
  
 lpStatus  
 [içinde out] Durum kodu döndürür (bkz [dosya durum kodu](../extensibility/file-status-code-enumerator.md) olası değerler için).  
  
 pnEventsRemaining  
 [içinde out] Bu çağrısından sonra sırada sol girişleri sayısını döndürür. Bu sayı büyükse, çağıran çağırmak karar verebilir [SccQueryInfo](../extensibility/sccqueryinfo-function.md) tüm bilgileri bir kerede alınacak.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Başarılı olayları alın.|  
|SCC_E_OPNOTSUPPORTED|Bu işlev desteklenmez.|  
|SCC_E_NONSPECIFICERROR|Belirli olmayan hata oluştu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev, boşta yapılmadığını kaynak denetimindeki dosyalar için tüm durum güncelleştirmeleri görmek için işleme sırasında çağrılır. Kaynak Denetim eklentisi hakkında bilgi sahibi tüm dosyaların durumunu tutar ve bir değişikliği her durum not ettiğiniz eklenti tarafından durumu ve ilişkili dosya sıraya depolanır. Zaman `SccGetEvents` çağrılır, üst öğe sırasının alınır ve döndürdü. Bu işlev yalnızca önceden önbelleğe alınan bilgileri döndürmek için sınırlı değildir ve (diğer bir deyişle, diskin okuma veya kaynak denetim sistemi durumunun isteyen); çok hızlı bir döngü olmalıdır Aksi takdirde IDE performansının düşmesine başlayabilir.  
  
 Kaynak Denetim eklentisi boş bir dize raporlanacak durum güncelleştirmesi yok ise gösterdiği arabelleğinde depolar. `lpFileName`. Dosyanın tam yol adını eklenti'Aksi halde, depolar, durum bilgileri değişti ve uygun durum kodunu döndürür (ayrıntılı değerlerden biri [dosya durum kodu](../extensibility/file-status-code-enumerator.md)).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [Dosya durum kodu](../extensibility/file-status-code-enumerator.md)