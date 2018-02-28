---
title: "SccCheckout işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SccCheckout
helpviewer_keywords:
- SccCheckout function
ms.assetid: 06e9ecd7-fc09-40c1-9dd1-2b56c622c80b
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: af8aac642ecd21f8f4709874e4e3e6ff0b3e58b5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="scccheckout-function"></a>SccCheckout işlevi
Tam dosya adlarının bir listesini göz önüne alındığında, bu işlev bunları yerel sürücüye kullanıma. Açıklama kullanıma alınmış tüm dosyalara uygulanır. Açıklama bağımsız değişken olabilir bir `null` dize.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccCheckout (  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LPCSTR    lpComment,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pvContext  
 [in] Kaynak Denetim eklentisi bağlam yapısı.  
  
 hWnd  
 [in] Kaynak Denetim eklentisi sağladığı tüm iletişim kutuları için üst öğe olarak kullanabileceğiniz IDE penceresi için bir tanıtıcı.  
  
 nFiles  
 [in] Kullanıma alınması için seçilen dosya sayısı.  
  
 lpFileNames  
 [in] Dosyaları kullanıma tam nitelenmiş bir yerel yol adlarının dizisini.  
  
 lpComment  
 [in] Kullanıma alınmış seçili dosyaları uygulanması için açıklama.  
  
 fOptions  
 [in] Komut bayrakları (bkz [bit işaretleri belirli komutları tarafından kullanılan](../extensibility/bitflags-used-by-specific-commands.md)).  
  
 pvOptions  
 [in] Kaynak denetimi fişi özel seçenekleri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Kullanıma başarılı oldu.|  
|SCC_E_FILENOTCONTROLLED|Seçilen dosya kaynak kodu denetimi altında değil.|  
|SCC_E_ACCESSFAILURE|Kaynak Denetim sistem ağ veya Çekişme sorun büyük olasılıkla erişilirken bir sorun oluştu. Yeniden deneme önerilir.|  
|SCC_E_NOTAUTHORIZED|Kullanıcı bu işlemi gerçekleştirmek için izin verilmiyor.|  
|SCC_E_NONSPECIFICERROR|Belirli olmayan hata oluştu. Dosya kullanıma alındı değil.|  
|SCC_E_ALREADYCHECKEDOUT|Kullanıcının kullanıma dosya zaten var.|  
|SCC_E_FILEISLOCKED|Yeni sürümler oluşturulmasını yasaklanması dosyası kilitli.|  
|SCC_E_FILEOUTEXCLUSIVE|Başka bir kullanıcı bu dosyayı bir özel checkout yapmıştır.|  
|SCC_I_OPERATIONCANCELED|İşlem tamamlanmadan önce iptal edildi.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [Özel Komutlar Tarafından Kullanılan Bit Bayrakları](../extensibility/bitflags-used-by-specific-commands.md)