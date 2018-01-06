---
title: "SccSetOption işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccSetOption
helpviewer_keywords: SccSetOption function
ms.assetid: 4b5e6666-c24c-438a-a9df-9c52f58f8175
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 70fe624984adce58191ee7d354185eac0bb527ed
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="sccsetoption-function"></a>SccSetOption işlevi
Bu işlev, kaynak denetim eklentisi davranışını denetleyen seçenekler ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccSetOption(  
   LPVOID pvContext,  
   LONG   nOption,  
   LONG   dwVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pvContext  
 [in] Kaynak Denetim eklentisi bağlam yapısı.  
  
 nOption  
 [in] Ayarlı seçeneği.  
  
 dwVal  
 [in] Seçenek için ayarlar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Seçeneği başarıyla ayarlandı.|  
|SCC_I_SHARESUBPROJOK|Döndürülen IF `nOption` oluştu `SCC_OPT_SHARESUBPROJ` ve hedef klasörü ayarlamak IDE eklenti kaynak denetimi sağlar.|  
|SCC_E_OPNOTSUPPORTED|Seçeneği ayarlı değil ve üzerinde kullanılmamalıdır.|  
  
## <a name="remarks"></a>Açıklamalar  
 IDE eklenti kaynak denetimi davranışını denetlemek için bu işlevi çağırır. İlk parametre `nOption`, ikinci olmakla ayarlı değeri gösterir `dwVal`, söz konusu değerle yapmanız gerekenler gösterir. Eklentisi ile ilişkili bu bilgileri depolayan bir `pvContext``,` IDE çağrıldıktan sonra bu işlevini çağırmanız gerekir böylece [SccInitialize](../extensibility/sccinitialize-function.md) (ancak mutlaka her çağrı sonra [SccOpenProject](../extensibility/sccopenproject-function.md)).  
  
 Seçenekleri ve bunların değerleri özeti:  
  
|`nOption`|`dwValue`|Açıklama|  
|---------------|---------------|-----------------|  
|`SCC_OPT_EVENTQUEUE`|`SCC_OPT_EQ_DISABLE`<br /><br /> `SCC_OPT_EQ_ENABLE`|Etkinleştirir/devre dışı bırakır, olay queuing arka plan.|  
|`SCC_OPT_USERDATA`|Rastgele değeri|Geçirilecek kullanıcı değeri belirten [OPTNAMECHANGEPFN](../extensibility/optnamechangepfn.md) geri çağırma işlevi.|  
|`SCC_OPT_HASCANCELMODE`|`SCC_OPT_HCM_NO`<br /><br /> `SCC_OPT_HCM_YES`|IDE şu anda bir işlem iptal ediliyor destekleyip desteklemediğini belirtir.|  
|`SCC_OPT_NAMECHANGEPFN`|İşaretçi [OPTNAMECHANGEPFN](../extensibility/optnamechangepfn.md) geri çağırma işlevi|Bir işaretçi bir ad değişikliği geri çağırma işlevini ayarlar.|  
|`SCC_OPT_SCCCHECKOUTONLY`|`SCC_OPT_SCO_NO`<br /><br /> `SCC_OPT_SCO_YES`|IDE dosyalarını el ile (kaynak denetimi kullanıcı arabirimi aracılığıyla) dışında denetleme veya olup bunlar yalnızca kaynak denetimi eklenti kullanıma alınmış olmalıdır izin verip vermeyeceğini belirtir.|  
|`SCC_OPT_SHARESUBPROJ`|Yok|Kaynak Denetim eklentisi yerel proje klasörü belirtmek IDE izin veriyorsa, eklenti döndürür `SCC_I_SHARESUBPROJOK`.|  
  
## <a name="sccopteventqueue"></a>SCC_OPT_EVENTQUEUE  
 Varsa `nOption` olan `SCC_OPT_EVENTQUEUE`, IDE devre dışı bırakma (yeniden etkinleştirme ya da) arka plan işleme. Örneğin, bir derleme sırasında IDE üzerinde boşta işleme herhangi bir türde durdurmak için eklenti kaynak denetimi taramasını sağlayabilirsiniz. Derlemeden sonra bu eklentinin olay sırası güncel tutmak için arka plan işleme yeniden etkinleştirmeniz. Karşılık gelen `SCC_OPT_EVENTQUEUE` değerini `nOption`, iki olası değerler için `dwVal`, yani, `SCC_OPT_EQ_ENABLE` ve `SCC_OPT_EQ_DISABLE`.  
  
## <a name="sccopthascancelmode"></a>SCC_OPT_HASCANCELMODE  
 Varsa değeri `nOption` olan `SCC_OPT_HASCANCELMODE`, uzun işlemlerini iptal etme kullanıcıların IDE verir. Ayarı `dwVal` için `SCC_OPT_HCM_NO` (varsayılan) IDE iptal modu yok olduğunu gösterir. Kaynak Denetim eklentisi, iptal etmek kullanıcı istiyorsa, kendi iptal düğmesi sağlaması gerekir. `SCC_OPT_HCM_YES`IDE eklenti SCC kendi iptal düğmesi görüntülemek gerek kalmayacak şekilde, bir işlem iptal etme olanağı sağlar gösterir. IDE ayarlarsa `dwVal` için `SCC_OPT_HCM_YES`, yanıt vermesi için hazırlanan `SCC_MSG_STATUS` ve `DOCANCEL` gönderilen iletileri `lpTextOutProc` geri çağırma işlevi (bkz [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)). IDE Bu değişken ayarlı değil, eklenti bu iki iletiyle göndermemelisiniz.  
  
## <a name="sccoptnamechangepfn"></a>SCC_OPT_NAMECHANGEPFN  
 NOption ayarlanmışsa `SCC_OPT_NAMECHANGEPFN`ve her iki kaynak denetimi eklentisini ve IDE izin verebilirsiniz, eklenti gerçekte yeniden adlandırabilir veya bir kaynak denetimi işlemi sırasında dosya taşıma. `dwVal` Türü için bir işlev işaretçisi ayarlanacak [OPTNAMECHANGEPFN](../extensibility/optnamechangepfn.md). Bir kaynak denetimi işlemi sırasında üç parametre geçirme, bu işlev eklenti çağırabilirsiniz. Bu eski adı (tam yolu) dosyasının, yeni adıyla (tam yolu), dosya ve IDE ilgisi olan bilgileri için bir işaretçi var. IDE üzerinde son this işaretçisi çağırarak gönderir `SccSetOption` ile `nOption` kümesine `SCC_OPT_USERDATA`, ile `dwVal` verilere işaret eden. Bu işlev için destek isteğe bağlıdır. VSSCI Tak-kullanır bu özelliği kendi işlevi işaretçisi ve kullanıcı verisi değişkenleri başlatmalıdır `NULL`, ve onu bir verildi sürece, bir yeniden adlandırma işlevini çağırmanız gerekir değil. Bu ayrıca verilen değer tutun veya yanıt için yeni bir çağrı olarak değiştirmek için hazırlıklı olmalıdır `SccSetOption`. Bu kaynak denetimi komutu işlemi ortasında yapılmaz, ancak komut arasında gerçekleşebilir.  
  
## <a name="sccoptscccheckoutonly"></a>SCC_OPT_SCCCHECKOUTONLY  
 NOption ayarlanmışsa `SCC_OPT_SCCCHECKOUTONLY`, IDE açık proje dosyalarında hiçbir zaman el ile kaynak denetimi sistemin kullanıcı arabirimi üzerinden kullanıma alınması olduğunu gösteren. Bunun yerine, dosyaları yalnızca IDE denetiminde eklenti kaynak denetimi aracılığıyla kullanıma alınması. Varsa `dwValue` ayarlanır `SCC_OPT_SCO_NO`, dosyaları normalde eklenti tarafından değerlendirilmelidir ve kaynak denetimi kullanıcı Arabirimi kullanıma anlamına gelir. Varsa `dwValue` ayarlanır `SCC_OPT_SCO_YES`sonra yalnızca eklenti dosyalar kullanıma izin verilen ve kaynak denetimi sistemin UI değil çağrılmalıdır. Bu, IDE "yalnızca IDE kullanıma mantıklı sözde dosyalar" nerede olabilir durumlar içindir.  
  
## <a name="sccoptsharesubproj"></a>SCC_OPT_SHARESUBPROJ  
 Varsa`nOption` ayarlanır `SCC_OPT_SHARESUBPROJ`, kaynak denetim eklentisi belirtilen bir yerel klasöre dosya kaynak denetiminden eklenirken kullanıp kullanamayacağını IDE test ediyor. Değeri `dwVal` parametresi önemli değildir, bu durumda. Eklenti burada dosyaları eklenecek kaynak sunucudan yerel hedef klasörü belirtmek IDE izin veriyorsa denetimi [SccAddFromScc](../extensibility/sccaddfromscc-function.md) çağrılır, eklenti döndürmelidir sonra `SCC_I_SHARESUBPROJOK` zaman `SccSetOption` işlevi çağrılır. IDE sonra kullanır `lplpFileNames` parametresinin `SccAddFromScc` hedef klasörde geçirmek için işlevi. Eklenti kaynak denetiminden eklenen dosyalar yerleştirmek için hedef klasör kullanır. Eklenti oluşmazsa `SCC_I_SHARESUBPROJOK` zaman `SCC_OPT_SHARESUBPROJ` seçeneği olarak ayarlanmışsa, IDE eklenti yalnızca geçerli yerel klasörde bulunan dosya eklemek mümkün olduğunu varsayar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)   
 [SccAddFromScc](../extensibility/sccaddfromscc-function.md)   
 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)   
 [OPTNAMECHANGEPFN](../extensibility/optnamechangepfn.md)