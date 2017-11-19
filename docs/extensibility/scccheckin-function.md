---
title: "SccCheckin işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccCheckin
helpviewer_keywords: SccCheckin function
ms.assetid: e3f26ac2-6163-42e1-a764-22cfea5a3bc6
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3742887be40f07f4b64003727333d4d21d08831e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="scccheckin-function"></a>SccCheckin işlevi
Bu işlev değişiklikleri depolamak ve yeni bir sürüm oluşturma kaynak denetim sistemi kullanıma daha önce dosyaları denetler. Bu işlev bir sayı ve bir dizi iade edilmesi dosyaların adlarını çağrılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccCheckin (  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPSTR*    lpFileNames,  
   LPCSTR    lpComment,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pvContext  
 [in] Kaynak Denetim eklentisi bağlam yapısı.  
  
 hWnd  
 [in] Eklenti SCC sağladığı tüm iletişim kutuları için üst öğe olarak kullanabileceğiniz IDE penceresi için bir tanıtıcı.  
  
 nFiles  
 [in] İade edilmesi seçili dosya sayısı.  
  
 lpFileNames  
 [in] İade edilmesi dosyaları tam nitelenmiş bir yerel yol adlarının dizisini.  
  
 lpComment  
 [in] Seçili dosyaları iade edildi uygulanması için açıklama. Bu `NULL` eklenti kaynak denetimi için bir açıklama istiyorsanız.  
  
 fOptions  
 [in] Komutunu bayrakları, ya da 0 veya `SCC_KEEP_CHECKEDOUT`.  
  
 pvOptions  
 [in] SCC fişi özel seçenekleri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Dosyaları başarıyla işaretlendiğinde.|  
|SCC_E_FILENOTCONTROLLED|Seçilen dosya kaynak kodu denetimi altında değil.|  
|SCC_E_ACCESSFAILURE|Kaynak Denetim sistem ağ veya Çekişme sorun büyük olasılıkla erişilirken bir sorun oluştu. Yeniden deneme önerilir.|  
|SCC_E_NONSPECIFICERROR|Belirli olmayan hata oluştu. Dosya iade.|  
|SCC_E_NOTCHECKEDOUT|Kullanıcının dosyaya iade edilemiyor, kullanıma değil.|  
|SCC_E_CHECKINCONFLICT|İade etme nedeniyle gerçekleştirilemedi:<br /><br /> -Başka bir kullanıcı önceden kullanıma ve `bAutoReconcile` yanlıştı.<br /><br /> veya<br /><br /> -(Örneğin, dosyaları ikili olduğunda) otomatik birleştirme işlemi yapılamaz.|  
|SCC_E_VERIFYMERGE|Dosya otomatik birleştirilmiş olmuştur, ancak kullanıcı doğrulaması iade edilmedi.|  
|SCC_E_FIXMERGE|Dosya otomatik birleştirilmiş olmuştur, ancak el ile çözümlenmelidir birleştirme çakışması nedeniyle iade edilmedi.|  
|SCC_E_NOTAUTHORIZED|Kullanıcı bu işlemi gerçekleştirmek için izin verilmiyor.|  
|SCC_I_OPERATIONCANCELED|İşlem tamamlanmadan önce iptal edildi.|  
|SCC_I_RELOADFILE|Bir dosya veya projeyi yeniden yüklenmesi gerekiyor.|  
|SCC_E_FILENOTEXIST|Yerel dosya bulunamadı.|  
  
## <a name="remarks"></a>Açıklamalar  
 Açıklama iade edildi tüm dosyalara uygulanır. Açıklama bağımsız değişken olabilir bir `null` dize, kaynak denetim eklentisi her dosya için bir açıklama dizesi kullanıcıdan; bu durumda.  
  
 `fOptions` Bağımsız değişken değeri verilebilir `SCC_KEEP_CHECKEDOUT` dosyasını denetleyin ve yeniden kullanıma kullanıcının yapma belirtmek için bayrak.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)