---
title: "SccInitialize işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccInitialize
helpviewer_keywords: SccInitialize function
ms.assetid: 5bc0d28b-2c68-4d43-9e51-541506a8f76e
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9e688d30d2367236cfcf5b2d14b36eb602832fc0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="sccinitialize-function"></a>SccInitialize işlevi
Bu işlev, eklenti kaynak denetimi başlatır ve özellikleri ve sınırları tümleşik geliştirme ortamına (IDE) sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccInitialize (  
   LPVOID* ppvContext,  
   HWND    hWnd,  
   LPCSTR  lpCallerName,  
   LPSTR   lpSccName,  
   LPLONG  lpSccCaps,  
   LPSTR   lpAuxPathLabel,  
   LPLONG  pnCheckoutCommentLen,  
   LPLONG  pnCommentLen  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppvContext`  
 [in] Kaynak Denetim eklentisi, bağlam yapısına yönelik işaretçinin buraya koyabilirsiniz.  
  
 `hWnd`  
 [in] Kaynak Denetim eklentisi sağladığı tüm iletişim kutuları için üst öğe olarak kullanabileceğiniz IDE penceresi için bir tanıtıcı.  
  
 `lpCallerName`  
 [in] Kaynak denetimi eklenti çağırma programın adı.  
  
 `lpSccName`  
 [içinde out] Burada eklenti kaynak denetimi koyar kendi adına arabellek (aşmayan `SCC_NAME_LEN`).  
  
 `lpSccCaps`  
 [out] Kaynak denetimi eklentinin yetenek bayrakları döndürür.  
  
 `lpAuxPathLabel`  
 [içinde out] Burada eklenti kaynak denetimi koyar tanımlayan bir dize arabellek `lpAuxProjPath` parametresi tarafından döndürülen [SccOpenProject](../extensibility/sccopenproject-function.md) ve [SccGetProjPath](../extensibility/sccgetprojpath-function.md) (aşmayan `SCC_AUXLABEL_LEN`).  
  
 `pnCheckoutCommentLen`  
 [out] Checkout açıklama için izin verilen en fazla uzunluk döndürür.  
  
 `pnCommentLen`  
 [out] Diğer açıklamaları için izin verilen maksimum döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Kaynak denetimi başlatma başarılı oldu.|  
|SCC_E_INITIALIZEFAILED|Sistem başlatılamadı.|  
|SCC_E_NOTAUTHORIZED|Kullanıcı, belirtilen işlem gerçekleştirmek için izin verilmiyor.|  
|SCC_E_NONSPECFICERROR|Belirli olmayan hata; Kaynak denetim sistemi başlatılamadı.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kaynak Denetim eklentisi ilk kez yüklediğinde IDE bu işlevi çağırır. Eklentiye arayan adı gibi belirli bilgileri geçirmek IDE sağlar. IDE yeniden de açıklamaları ve eklentinin yetenekler için izin verilen uzunluk sınırını gibi belirli bilgileri alır.  
  
 `ppvContext` İşaret eden bir `NULL` işaretçi. Kaynak Denetim eklentisi kendi kullanımı için bir yapı ayırmak ve o yapısında bir işaretçi depolamak `ppvContext`. IDE this işaretçisi, her diğer VSSCI API işlevi için eklenti için genel depolama başvurmadan bağlam bilgilerini kullanılabilir olmasını ve eklenti birden çok örneğini desteklemek için izin verme geçirin. Bu yapı ne zaman serbest [SccUninitialize](../extensibility/sccuninitialize-function.md) olarak adlandırılır.  
  
 `lpCallerName` Ve `lpSccName` parametreleri IDE ve kaynak denetim eklentisi adları Exchange etkinleştirme. Bu adları, yalnızca birden çok örnekler arasında ayrım yapmak için kullanılan veya bunlar aslında menüleri ve iletişim kutularında görünebilir.  
  
 `lpAuxPathLabel` Parametredir çözüm dosyasında depolanır ve kaynak denetimi çağrıda eklenti geçirilen yardımcı proje yolu tanımlamak için bir açıklama olarak kullanılan bir dize [SccOpenProject](../extensibility/sccopenproject-function.md). [!INCLUDE[vsvss](../extensibility/includes/vsvss_md.md)]bir dizeyi kullanan "SourceSafe proje:"; diğer kaynak denetim eklentileri bu belirli dize kullanmamalıdır.  
  
 `lpSccCaps` Parametresi verir kaynak denetimi eklenti eklentinin özelliklerini belirten bit işaretleri depolamak için bir yer. (Yetenek bit işaretleri tam bir listesi için bkz: [yetenek bayrakları](../extensibility/capability-flags.md)). Örneğin, eklenti özelliği ayarlardı sonuçları bir çağıran tarafından sağlanan geri çağırma işlevini yazmak için eklenti planları SCC_CAP_TEXTOUT bit durumunda. Bu sürüm denetimi sonuçları için bir pencere oluşturmak için IDE sinyal.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [SccUninitialize](../extensibility/sccuninitialize-function.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)   
 [Yetenek bayrakları](../extensibility/capability-flags.md)