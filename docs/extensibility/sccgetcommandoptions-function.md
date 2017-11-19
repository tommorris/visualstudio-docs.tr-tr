---
title: "SccGetCommandOptions işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccGetCommandOptions
helpviewer_keywords: SccGetCommandOptions function
ms.assetid: bbe4aa4e-b4b0-403e-b7a0-5dd6eb24e5a9
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6848689be19e67009314b167b60724a95fd6da5b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="sccgetcommandoptions-function"></a>SccGetCommandOptions işlevi
Bu işlev verilen komut için Gelişmiş Seçenekleri kullanıcıya sorar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccGetCommandOptions(  
   LPVOID pvContext,  
   HWND hWnd,  
   enum SCCCOMMAND iCommand,  
   LPCMDOPTS* ppvOptions  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pvContext  
 [in] Kaynak Denetim eklentisi bağlam yapısı.  
  
 hWnd  
 [in] Kaynak Denetim eklentisi sağladığı tüm iletişim kutuları için üst öğe olarak kullanabileceğiniz IDE penceresi için bir tanıtıcı.  
  
 ICommand  
 [in] Gelişmiş Seçenekler istenir komutu (bkz [komut kodu](../extensibility/command-code-enumerator.md) olası değerler için).  
  
 ppvOptions  
 [in] Seçenek yapısı (aynı zamanda olabilir `NULL`).  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Başarılı.|  
|SCC_I_ADV_SUPPORT|Kaynak Denetim eklentisi komutu için Gelişmiş seçenekleri destekler.|  
|SCC_I_OPERATIONCANCELED|Kaynak denetimi eklentinin kullanıcı iptal **seçenekleri** iletişim kutusu.|  
|SCC_E_OPTNOTSUPPORTED|Kaynak Denetim eklentisi bu işlemi desteklemiyor.|  
|SCC_E_ISCHECKEDOUT|Şu anda kullanıma alınmış bir dosya üzerinde bu işlemi gerçekleştiremezsiniz.|  
|SCC_E_ACCESSFAILURE|Kaynak Denetim sistem ağ veya Çekişme sorun büyük olasılıkla erişilirken bir sorun oluştu. Yeniden deneme önerilir.|  
|SCC_E_NONSPECIFICERROR|Belirli olmayan hata oluştu.|  
  
## <a name="remarks"></a>Açıklamalar  
 IDE ilk kez bu işlev çağrıları `ppvOptions` = `NULL` eklenti kaynak denetimi için belirtilen komutu Gelişmiş Seçenekleri özelliğini destekleyip desteklemediğini belirlemek için. Eklenti özelliği için bu komutu destekliyorsa, kullanıcı Gelişmiş Seçenekler istediğinde IDE bu işlevi yeniden çağırır (genellikle olarak uygulanan bir **Gelişmiş** iletişim kutusunda düğmesini) ve içinNULLolmayanişaretçisağlar`ppvOptions` işaret eden bir `NULL` işaretçi. Eklenti özel bir yapı kullanıcı tarafından belirtilen tüm gelişmiş seçenekleri saklar ve o yapısında bir işaretçi döndürür `ppvOptions`. Bu yapı ardından sonraki çağrılar dahil olmak üzere bu hakkında bilmeniz gereken diğer tüm kaynak denetim eklentisi API işlevleri geçirilen `SccGetCommandOptions` işlevi.  
  
 Bir örnek, bu durum açıklamak yardımcı olabilir.  
  
 Kullanıcının seçtiği **almak** komutu ve IDE görüntüler bir **Al** iletişim kutusu. IDE çağrıları `SccGetCommandOptions` ile işlev `iCommand` kümesine `SCC_COMMAND_GET` ve `ppvOptions` kümesine `NULL`. Bu soru olarak eklenti kaynak denetimi tarafından yorumlanır, "Bu komutu için Gelişmiş seçenekleri var mı?" Eklenti döndürürse `SCC_I_ADV_SUPPORT`, IDE görüntüler bir **Gelişmiş** düğmesini kendi **Al** iletişim kutusu.  
  
 Kullanıcı ilk kez **Gelişmiş** düğmesi, IDE yeniden çağırır `SccGetCommandOptions` , bu kez olmayan bir işlev`NULL``ppvOptions` işaret eden bir `NULL` işaretçi. Eklenti görüntüler kendi **alma seçenekleri** iletişim kutusu, kullanıcıdan bilgi için bu bilgileri kendi yapıda alır ve bu yapısında bir işaretçi döndürür `ppvOptions`.  
  
 Kullanıcı tıklarsa **Gelişmiş** aynı iletişim kutusunda IDE yeniden çağırır `SccGetCommandOptions` değiştirmeden yeniden işlevi `ppvOptions`, böylece yapısı geri eklenti geçirilir. Bu eklenti kullanıcı daha önce ayarlamış olduğunuz değerlere iletişim kutusu yeniden başlatılmasını sağlar. Eklenti yerinde yapısı, döndürmeden önce değiştirir.  
  
 Son olarak, kullanıcı tıkladığında **Tamam** IDE'nin içinde **almak** iletişim kutusu, IDE çağrıları [SccGet](../extensibility/sccget-function.md), döndürülen yapısı geçirme `ppvOptions` içeren Gelişmiş Seçenekler.  
  
> [!NOTE]
>  Komut `SCC_COMMAND_OPTIONS` IDE görüntüler kullanıldığında bir **seçenekleri** kullanıcı iletişim kutusunu tümleştirme nasıl çalıştığını denetleyen tercihleri ayarlayın. Kaynak Denetim eklentisi kendi Tercihleri iletişim kutusuyla sağlamak istiyorsa, ondan görüntüleyebilirsiniz bir **Gelişmiş** IDE'nin Tercihleri iletişim kutusunda düğme. Eklenti alma ve bu bilgileri sürdürmek için yalnızca sorumludur; IDE bırakmaz kullanmak veya değiştirin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [Komut kodu](../extensibility/command-code-enumerator.md)