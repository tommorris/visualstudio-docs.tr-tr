---
title: "SccAdd işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccAdd
helpviewer_keywords: SccAdd function
ms.assetid: 545268f3-8e83-446a-a398-1a9db9e866e8
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c8cd55986d7f4597030830906485ba1d7c1b3389
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="sccadd-function"></a>SccAdd işlevi
Bu işlev için kaynak denetim sisteminizle yeni dosyaları ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccAdd(  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LPCSTR    lpComment,  
   LONG*     pfOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pvContext  
 [in] Kaynak Denetim eklentisi bağlam yapısı.  
  
 hWnd  
 [in] Kaynak Denetim eklentisi sağladığı tüm iletişim kutuları için üst öğe olarak kullanabileceğiniz IDE penceresi için bir tanıtıcı.  
  
 nFiles  
 [in] İçinde belirtilen geçerli projeye eklemek için seçilen dosya sayısı `lpFileNames` dizi.  
  
 lpFileNames  
 [in] Eklenecek dosyaların tam yerel adlarını dizisi.  
  
 lpComment  
 [in] Eklenmekte olan dosyaları tümüne uygulanacak açıklama.  
  
 pfOptions  
 [in] Bir dosya başına temelinde sağlanan komut bayrakları dizisi.  
  
 pvOptions  
 [in] Kaynak denetimi fişi özel seçenekleri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Ekleme işlemi başarılı oldu.|  
|SCC_E_FILEALREADYEXISTS|Seçilen dosya kaynak denetimi altında zaten var.|  
|SCC_E_TYPENOTSUPPORTED|(Örneğin, ikili) dosya türü, kaynak denetim sistemi tarafından desteklenmiyor.|  
|SCC_E_OPNOTSUPPORTED|Kaynak Denetim sistem bu işlemi desteklemiyor.|  
|SCC_E_ACCESSFAILURE|Kaynak Denetim sistem ağ veya Çekişme sorun büyük olasılıkla erişilirken bir sorun oluştu. Yeniden deneme önerilir.|  
|SCC_E_NOTAUTHORIZED|Kullanıcı bu işlemi gerçekleştirmek için izin verilmiyor.|  
|SCC_E_NONSPECIFICERROR|Belirli olmayan hata; gerçekleştirilemiyor ekleyin.|  
|SCC_I_OPERATIONCANCELED|İşlem tamamlanmadan önce iptal edildi.|  
|SCC_I_RELOADFILE|Bir dosya veya projeyi yeniden yüklenmesi gerekiyor.|  
|SCC_E_FILENOTEXIST|Yerel dosya bulunamadı.|  
  
## <a name="remarks"></a>Açıklamalar  
 Normal `fOptions` bir dizi tarafından buraya değiştirilir `pfOptions`, biriyle `LONG` seçeneği dosya başına belirtimi. Bu durum, dosya türünü dosya dosyasından farklı olabilir çünkü.  
  
> [!NOTE]
>  Her ikisi de belirtmek için geçersiz `SCC_FILETYPE_TEXT` ve `SCC_FILETYPE_BINARY` hiçbiri belirtmek için aynı dosyayı, ancak seçeneklerini geçerlidir. Hiçbiri ayardır ayarı ile aynı `SCC_FILETYPE_AUTO`, bu durumda kaynak denetim eklentisi autodetects dosya türü.  
  
 Kullanılan bayrakların listesi aşağıdadır `pfOptions` dizi:  
  
|Seçenek|Değer|Açıklama|  
|------------|-----------|-------------|  
|SCC_FILETYPE_AUTO|0x00|Kaynak Denetim eklentisi dosya türünü algıla.|  
|SCC_FILETYPE_TEXT|0x01|Bir ASCII metin dosyası gösterir.|  
|SCC_FILETYPE_BINARY|0x02|ASCII metni farklı bir dosya türünü belirtir.|  
|SCC_ADD_STORELATEST|0x04|Hiçbir farkları dosyanın yalnızca en yeni kopyasını saklar.|  
|SCC_FILETYPE_TEXT_ANSI|0x08|Dosyası ANSI metin olarak değerlendirir.|  
|SCC_FILETYPE_UTF8|0x10|UTF8 biçiminde Unicode metin olarak dosyası değerlendirir.|  
|SCC_FILETYPE_UTF16LE|0x20|Dosyası biraz Endian biçiminde Unicode metin UTF16 olarak değerlendirir.|  
|SCC_FILETYPE_UTF16BE|0x40|Davranır dosyanın UTF16 Big Endian Unicode metin olarak biçimlendirin.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)