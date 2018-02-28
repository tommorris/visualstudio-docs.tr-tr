---
title: "SccUncheckout işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SccUncheckout
helpviewer_keywords:
- SccUncheckout function
ms.assetid: 6d498b70-29c7-44b7-ae1c-7e99e488bb09
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: f9b4b2f06b8ee020ca07e780836ec2abbbc96e82
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="sccuncheckout-function"></a>SccUncheckout işlevi
Bu işlev seçilen dosya veya dosyaları içeriğini checkout önce durumuna böylece geri yükleme önceki bir kullanıma alma işlemini geri alır. Bu yana checkout dosyada yapılan tüm değişiklikler kaybolur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccUncheckout (  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
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
 [in] Belirtilen dosya sayısı `lpFileNames` dizi.  
  
 lpFileNames  
 [in] Dosyaların, bir kullanıma almayı geri almak tam nitelenmiş bir yerel yol adlarının dizisini.  
  
 fOptions  
 [in] Komutunu bayrakları (kullanılmaz).  
  
 pvOptions  
 [in] Kaynak denetimi fişi özel seçenekleri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Kullanıma almayı geri al başarılı oldu.|  
|SCC_E_FILENOTCONTROLLED|Seçilen dosya kaynak kodu denetimi altında değil.|  
|SCC_E_ACCESSFAILURE|Kaynak Denetim sistem ağ veya Çekişme sorun büyük olasılıkla erişilirken bir sorun oluştu. Yeniden deneme önerilir.|  
|SCC_E_NONSPECIFICERROR|Belirli olmayan hata oluştu. Geri ödeme etkinleştirilemedi.|  
|SCC_E_NOTCHECKEDOUT|Kullanıcı dosya kullanıma sahip değil.|  
|SCC_E_NOTAUTHORIZED|Kullanıcı bu işlemi gerçekleştirmek için izin verilmiyor.|  
|SCC_E_PROJNOTOPEN|Proje kaynak denetiminden açılmadı.|  
|SCC_I_OPERATIONCANCELED|İşlem tamamlanmadan önce iptal edildi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlem sonrasında `SCC_STATUS_CHECKEDOUT` ve `SCC_STATUS_MODIFIED` bayraklarının hem temizlenmiş kullanıma almayı geri al gerçekleştirildiği dosyaları.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentisi API İşlevleri](../extensibility/source-control-plug-in-api-functions.md)