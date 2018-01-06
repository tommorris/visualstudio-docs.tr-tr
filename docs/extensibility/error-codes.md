---
title: "Hata kodları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- error codes, source control plug-ins
- source control plug-ins, error codes
- errors [Visual Studio SDK]
ms.assetid: d9cbd1c4-719b-467a-8100-333c1e146d3b
caps.latest.revision: "19"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 13eff6aca9470e88be788fe3fcb625fecc32c2c2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="error-codes"></a>Hata Kodları
Kaynak Denetim eklentisi API işlev hata döndürür, aşağıdaki hata kodlarından birini olması beklenir. Uyarı veya bilgilendirme hata kodları pozitif, tüm hataları negatif ve başarılı 0'dır.  
  
|Hata Kodu|Değer|Açıklama|  
|----------------|-----------|-----------------|  
|`SCC_I_SHARESUBPROJOK`|7|İki adımda kaynak denetiminden dosyaları ekleme eklenti destekler. Daha fazla bilgi için bkz: [SccSetOption](../extensibility/sccsetoption-function.md).|  
|`SCC_I_FILEDIFFERS`|6|Yerel kaynak denetim veritabanı dosyasında farklı bir dosyadır (örneğin, [SccDiff](../extensibility/sccdiff-function.md) bu değer döndürebilir).|  
|`SCC_I_RELOADFILE`|5|Yerel dosya kaynak denetimi işlemi sırasında değiştirildi; IDE mümkünse dosyayı yeniden.|  
|`SCC_I_FILENOTAFFECTED`|4|Dosya etkilenmez.|  
|`SCC_I_PROJECTCREATED`|3|Proje kaynak denetimi işlemi sırasında oluşturulan (örneğin, bir çağrı sırasında [SccOpenProject](../extensibility/sccopenproject-function.md) zaman `SCC_OP_CREATEIFNEW` bayrağı belirtilir).|  
|`SCC_I_OPERATIONCANCELED`|2|İşlem iptal edildi.|  
|`SCC_I_ADV_SUPPORT`|1.|Belirtilen komut seçeneklerini Gelişmiş eklenti destekler. Daha fazla bilgi için bkz: [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md).|  
|`SCC_OK`|0|Başarılı.|  
|`SCC_E_INITIALIZEFAILED`|-1|Hata: başlatma başarısız oldu.|  
|`SCC_E_UNKNOWNPROJECT`|-2|Hata: Proje bilinmiyor.|  
|`SCC_E_COULDNOTCREATEPROJECT`|-3|Hata: Proje oluşturulamadı.|  
|`SCC_E_NOTCHECKEDOUT`|-4|Hata: dosya kullanıma alınmadı.|  
|`SCC_E_ALREADYCHECKEDOUT`|-5|Hata: dosya zaten kullanıma alındı.|  
|`SCC_E_FILEISLOCKED`|-6|Hata: Dosya kilitlendi.|  
|`SCC_E_FILEOUTEXCLUSIVE`|-7|Hata: dosyanın özel olarak kullanıma alındı.|  
|`SCC_E_ACCESSFAILURE`|-8|Kaynak Denetim sistem ağ veya Çekişme sorun büyük olasılıkla erişilirken bir sorun oluştu. Yeniden deneme önerilir.|  
|`SCC_E_CHECKINCONFLICT`|-9|Hata: iade etme sırasında bir çakışma vardı.|  
|`SCC_E_FILEALREADYEXISTS`|-10|Hata: dosya zaten var.|  
|`SCC_E_FILENOTCONTROLLED`|-11|Hata: dosya kaynak denetimi altında değil.|  
|`SCC_E_FILEISCHECKEDOUT`|-12|Hata: dosya kullanıma alınmış.|  
|`SCC_E_NOSPECIFIEDVERSION`|-13|Hata: belirtilen sürümü yoktur.|  
|`SCC_E_OPNOTSUPPORTED`|-14|Hata: işlem desteklenmiyor.|  
|`SCC_E_NONSPECIFICERROR`|-15|Belirli olmayan bir hata oluştu.|  
|`SCC_E_OPNOTPERFORMED`|-16|Hata, işlem gerçekleştirilemedi.|  
|`SCC_E_TYPENOTSUPPORTED`|-17|Hata: dosya türü, örneğin, ikili, kaynak kodu denetimi sistem tarafından desteklenmiyor.|  
|`SCC_E_VERIFYMERGE`|-18|Dosya otomatik birleştirilmiş olmuştur, ancak bekleyen kullanıcı doğrulama olduğundan denetlendi değil.|  
|`SCC_E_FIXMERGE`|-19|Dosya otomatik birleştirilmiş olmuştur, ancak el ile çözümlenmelidir birleştirme çakışması nedeniyle iade edilmedi.|  
|`SCC_E_SHELLFAILURE`|-20|Kabuk hata nedeniyle hata oluştu.|  
|`SCC_E_INVALIDUSER`|-21|Hata: Kullanıcı geçersiz.|  
|`SCC_E_PROJECTALREADYOPEN`|-22|Hata: Proje zaten açıktır.|  
|`SCC_E_PROJSYNTAXERR`|-23|Proje sözdizimi hatası.|  
|`SCC_E_INVALIDFILEPATH`|-24|Hata: dosya yolu geçersiz.|  
|`SCC_E_PROJNOTOPEN`|-25|Hata: Proje açık değil.|  
|`SCC_E_NOTAUTHORIZED`|-26|Hata: kullanıcı, bu işlemi gerçekleştirmek için yetkili değil.|  
|`SCC_E_FILESYNTAXERR`|-27|Dosya sözdizimi hatası.|  
|`SCC_E_FILENOTEXIST`|-28|Hata, yerel dosya yok.|  
|`SCC_E_CONNECTIONFAILURE`|-29|Hata: bir bağlantı hatası oluştu.|  
|`SCC_E_UNKNOWNERROR`|-30|Bilinmeyen hata.|  
|`SCC_E_BACKGROUNDGETINPROGRESS`|-31|Arka plan alma işlemi şu anda devam ediyor.|  
  
## <a name="macros-provided-for-quick-checking"></a>Hızlı denetlemek için sağlanan makroları  
  
```cpp  
IS_SCC_ERROR(rtn) (((rtn) < 0) ? TRUE : FALSE)  
IS_SCC_SUCCESS(rtn) (((rtn) == SCC_OK) ? TRUE : FALSE)  
IS_SCC_WARNING(rtn) (((rtn) > 0) ? TRUE : FALSE)  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Tüm kaynak denetim eklentisi API işlevleri (dışında [SccAdd](../extensibility/sccadd-function.md), [SccCheckin](../extensibility/scccheckin-function.md), ve [SccDiff](../extensibility/sccdiff-function.md)) bağımsız değişken olarak geçirilen yerel dosyaları yaptığınızda başarılı olması beklenir çalışma klasörü yok. Örneğin, IDE yapılan bir çağrı verebileceği [SccCheckout](../extensibility/scccheckout-function.md) veya [SccUncheckout](../extensibility/sccuncheckout-function.md) çalışma klasörü yok, ancak kaynak denetimi sistemde mevcut bir dosyada. Bu çağrı başarılı. Yalnızca hiçbir dosya çalışma klasörü veya kaynak denetim sistemi olduğunda işlevi başarısız olması beklenir.  
  
 Gibi belirli işlevleri `SccAdd` ve `SccCheckin`, özellikle döndürmelidir `SCC_E_FILENOTEXIST` zaman çalışma klasörü dosyasında yok. Diğer işlevleri çalışma dosyası mevcut değil, işlevleri kaynak denetim sistemi geçerli bir dosya adı üzerinde çalışmazsa başarılı olması beklenir.  
  
 Eklenti dosyanın salt okunur sırasında başka bir işlem olarak işaretlenmiş olsa bile eklenti kaynak denetimi çalışma klasöründe bir dosyada ayrıcalıkları ilgili hiçbir varsayımlar olmanız gerekir. Çalışma klasörü dosyasında taşınmış, silindi ve eklentinin denetimi dışında değiştirildi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentileri](../extensibility/source-control-plug-ins.md)