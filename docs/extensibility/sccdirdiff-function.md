---
title: SccDirDiff işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccDirDiff
helpviewer_keywords:
- SccDirDiff function
ms.assetid: 26c9ba92-e3b9-4dd2-bd5e-76b17745e308
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7d2bea7816375da1131f557ebcbe206056f347f2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31138028"
---
# <a name="sccdirdiff-function"></a>SccDirDiff işlevi
Bu işlev istemci diskteki geçerli yerel dizin ve kaynak denetimi altında karşılık gelen proje arasındaki farkları görüntüler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccDirDiff(  
   LPVOID    pContext,  
   HWND      hWnd,  
   LPCSTR    lpDirName,  
   LONG      dwFlags,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pContext  
 [in] Kaynak Denetim eklentisi bağlam yapısı.  
  
 hWnd  
 [in] Kaynak Denetim eklentisi sağladığı tüm iletişim kutuları için üst öğe olarak kullanabileceğiniz IDE penceresi için bir tanıtıcı.  
  
 lpDirName  
 [in] Görsel fark gösterileceği yerel dizinin tam yolu.  
  
 dwFlags  
 [in] Komut bayrakları (açıklamalar bkz bölümü).  
  
 pvOptions  
 [in] Kaynak denetimi fişi özel seçenekleri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Disk üzerinde dizin kaynak kodu denetimi projesinde ile aynıdır.|  
|SCC_I_FILESDIFFER|Disk üzerinde dizin, kaynak kodu denetimi projesinde farklıdır.|  
|SCC_I_RELOADFILE|Bir dosya veya projeyi yeniden yüklenmesi gerekiyor.|  
|SCC_E_FILENOTCONTROLLED|Dizin kaynak kodu denetimi altında değil.|  
|SCC_E_NOTAUTHORIZED|Kullanıcı bu işlemi gerçekleştirmek için izin verilmiyor.|  
|SCC_E_ACCESSFAILURE|Kaynak Denetim sistem ağ veya Çekişme sorun büyük olasılıkla erişilirken bir sorun oluştu. Yeniden deneme önerilir.|  
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|Belirli olmayan hata oluştu.|  
|SCC_E_FILENOTEXIST|Yerel dizin bulunamadı.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev eklentisinin kullanıcıya belirli bir dizine değişikliklerin listesini görüntülemek için kaynak denetimi istemek için kullanılır. Eklenti, kullanıcının dizini disk üzerinde ve sürüm denetimi altındaki karşılık gelen proje arasındaki farklar görüntülemek için kendi seçtikleri biçimde kendi penceresi açılır.  
  
 "Hızlı-fark" seçenekleri desteklenmiyor olsa bile dizinleri hiç eklenti destekler karşılaştırması varsa, onu bir dosya adı temelinde dizinleri karşılaştırması desteklemesi gerekir.  
  
|`dwFlags`|Yorumu|  
|---------------|--------------------|  
|SCC_DIFF_IGNORECASE|Büyük küçük harf duyarsız karşılaştırma (hızlı fark veya visual için kullanılabilir).|  
|SCC_DIFF_IGNORESPACE|(Hızlı fark veya visual için kullanılabilir) boşluk yok sayar.|  
|SCC_DIFF_QD_CONTENTS|Kaynak Denetimi Eklentisi tarafından destekleniyorsa, sessizce bayt dizin karşılaştırır.|  
|SCC_DIFF_QD_CHECKSUM|Eklenti tarafından desteklenen, sessizce directory bir sağlama toplamı ile karşılaştırır veya desteklenmiyor, SCC_DIFF_QD_CONTENTS için geri döner.|  
|SCC_DIFF_QD_TIME|Eklenti tarafından desteklenen, sessizce directory kendi zaman damgası ile karşılaştırır veya desteklenmiyor, SCC_DIFF_QD_CHECKSUM veya SCC_DIFF_QD_CONTENTS geri döner.|  
  
> [!NOTE]
>  Bu işlev olarak aynı komutu bayrakları kullanır [SccDiff](../extensibility/sccdiff-function.md). Ancak, kaynak denetim eklentisi dizinler için "hızlı-fark" işlemi desteklemeyen tercih edebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentisi API İşlevleri](../extensibility/source-control-plug-in-api-functions.md)