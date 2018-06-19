---
title: SccDiff işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccDiff
helpviewer_keywords:
- SccDiff function
ms.assetid: d49bc8c5-f631-4153-9d3c-feb3564da305
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 30d8d6a4b8b400088d5feed663c8257215a0f8a1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31138583"
---
# <a name="sccdiff-function"></a>SccDiff işlevi
Bu işlev görüntüler (veya isteğe bağlı olarak yalnızca denetler) (yerel diskte) geçerli bir dosya ve son kullanıma açma sürümünün arasındaki farklar kaynak denetim sistemi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccDiff(  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LPCSTR    lpFileName,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pvContext  
 [in] Kaynak Denetim eklentisi bağlam yapısı.  
  
 hWnd  
 [in] Kaynak Denetim eklentisi sağladığı tüm iletişim kutuları için üst öğe olarak kullanabileceğiniz IDE penceresi için bir tanıtıcı.  
  
 lpDosyaAdı  
 [in] Fark istenen dosya adı.  
  
 fOptions  
 [in] Komutunu bayraklar. Açıklamalar için bkz.  
  
 pvOptions  
 [in] Kaynak denetimi fişi özel seçenekleri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Çalışma kopyası ve sunucu sürümü aynıdır.|  
|SCC_I_FILESDIFFERS|Çalışma kopyası sürümü kaynak denetimi altında farklıdır.|  
|SCC_I_RELOADFILE|Bir dosya veya projeyi yeniden yüklenmesi gerekiyor.|  
|SCC_E_FILENOTCONTROLLED|Dosya kaynak denetimi altında değil.|  
|SCC_E_NOTAUTHORIZED|Kullanıcı bu işlemi gerçekleştirmek için izin verilmiyor.|  
|SCC_E_ACCESSFAILURE|Kaynak Denetim sistem ağ veya Çekişme sorun büyük olasılıkla erişilirken bir sorun oluştu. Yeniden deneme önerilir.|  
|SCC_E_NONSPECIFICERROR|Belirli olmayan hata; Dosya fark alınamadı.|  
|SCC_E_FILENOTEXIST|Yerel dosya bulunamadı.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev, farklı iki amaca hizmet eder. Varsayılan olarak, bir dosyaya yapılan değişikliklerin bir listesi görüntüler. Kaynak Denetim eklentisi, kullanıcının dosya diskte ve kaynak denetimi altında dosyasının en son sürümünü arasındaki farkları görüntülemek için seçtiği ne olursa olsun biçiminde kendi penceresi açılır.  
  
 Alternatif olarak, IDE, yalnızca bir dosya değişip değişmediğini belirlemek gerekebilir. Örneğin, IDE, kullanıcı bildiren olmadan dosyasını teslim almak güvenli olup olmadığını belirlemek gerekebilir. Bu durumda, IDE geçirir `SCC_DIFF_CONTENTS` bayrağı. Kaynak Denetim eklentisi diskteki karşı kaynak denetimli dosya bayt, dosyayı denetleyin ve hiçbir şey kullanıcıya görüntülemeden iki dosya farklı olup olmadığını gösteren bir değer döndürmesi gerekir.  
  
 Performansı iyileştirme bir sağlama toplamı veya zaman damgası için adlı bayt bayt karşılaştırma yerine dayalı bir alternatif kaynak denetim eklentisi kullanabilir `SCC_DIFF_CONTENTS`: Bu formların karşılaştırma tabii daha hızlı ancak daha az güvenilir. Tüm kaynak denetim sistemleri bu alternatif karşılaştırma yöntemleri destekleyebilir ve eklenti içeriğini karşılaştırma geri yüklemeniz gerekebilir. Tüm kaynak denetim eklentileri en azından bir içeriğini karşılaştırma desteklemesi gerekir.  
  
> [!NOTE]
>  Hızlı fark bayrakları karşılıklı olarak birbirini dışlar. Hiçbir bayrakları geçirmek için geçerlidir, ancak aynı anda birden fazla geçirmek için geçerli değil. `SCC_DIFF_QUICK_DIFF`, test etmek için tüm bayraklar birleştiren bir maskesi olan kullanılabilir, ancak hiçbir zaman bir parametre olarak aktarılmalıdır.  
  
|`fOption`|Açıklama|  
|---------------|-------------|  
|SCC_DIFF_IGNORECASE|Büyük küçük harf duyarsız karşılaştırma (hızlı veya görsel fark için kullanılabilir).|  
|SCC_DIFF_IGNORESPACE|(Hızlı veya görsel fark için kullanılabilir) boşluk yok sayar.|  
|SCC_DIFF_QD_CONTENTS|Sessizce bayt dosya karşılaştırır.|  
|SCC_DIFF_QD_CHECKSUM|Sessiz bir şekilde dosyanın desteklendiği durumlarda bir sağlama toplamı ile karşılaştırır. Desteklenmeyen, içeriği karşılaştırması için geri döner.|  
|SCC_DIFF_QD_TIME|Sessizce desteklendiğinde, zaman damgası aracılığıyla dosya karşılaştırır. Desteklenmeyen, içeriği karşılaştırması için geri döner.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentisi API İşlevleri](../extensibility/source-control-plug-in-api-functions.md)