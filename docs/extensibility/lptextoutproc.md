---
title: LPTEXTOUTPROC | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LPTEXTOUTPROC
helpviewer_keywords:
- SccMsgDataOnMessage structure
- SccMsgDataOnBeforeGetFile structure
- SccMsgDataIsCancelled structure
- LPTEXTOUTPROC callback function
- SccMsgDataOnAfterGetFile structure
ms.assetid: 2025c969-e3c7-4cf4-a5c5-099d342895ea
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 9fb212d7908d32bc9d9d14d7e8f4786089bc5f89
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="lptextoutproc"></a>LPTEXTOUTPROC
Kullanıcı bir kaynak denetimi işleminin tümleşik geliştirme ortamı (IDE) içindeki yürütüldüğünde, eklenti kaynak denetimi için işlemi ile ilgili hata veya durum mesajları iletmek isteyebilirsiniz. Eklenti kendi ileti kutuları bu amaçla görüntüleyebilirsiniz. Ancak, daha fazla sorunsuz tümleştirme için eklenti dizeler ardından bunları durum bilgilerini görüntüleme, kendi yerel yolu görüntüler IDE geçirebilirsiniz. Bu mekanizma `LPTEXTOUTPROC` işlev işaretçisi. IDE hata ve durum görüntüleme (aşağıdaki daha ayrıntılı olarak açıklanmıştır) Bu işlev uygular.  
  
 IDE için kaynak denetimi eklenti bu işlev bir işlev işaretçisi olarak geçirir `lpTextOutProc` çağırırken parametre [SccOpenProject](../extensibility/sccopenproject-function.md). Örneğin, bir çağrı ortasında bir SCC işlemi sırasında [SccGet](../extensibility/sccget-function.md) çok sayıda dosya içeren, eklenti çağırabilirsiniz `LPTEXTOUTPROC` işlevi, düzenli aralıklarla görüntülemek için dizeleri geçirme. IDE durum çubuğunda, bir çıktı penceresinde veya ayrı bir ileti kutusu, uygun şekilde bu dizeler görüntülenebilir. İsteğe bağlı olarak, IDE belirli iletileri ile görüntüleme mümkün olabilir bir **iptal** düğmesi. Bu işlemi iptal etmek kullanıcının sağlar ve bu bilgileri tekrar eklenti geçirmek olanağı IDE sağlar.  
  
## <a name="signature"></a>İmza  
 IDE işlevi aşağıdaki imzaya sahip çıktı:  
  
```cpp  
typedef LONG (*LPTEXTOUTPROC) (  
   LPSTR display_string,  
   LONG mesg_type  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 display_string  
 Görüntülenecek bir metin dizesi. Bu dize bir satır başı dönüş veya satır besleme ile sonlandırılmalıdır değil.  
  
 mesg_type  
 İleti türü. Aşağıdaki tabloda, bu parametre için desteklenen değerler listelenmektedir.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`SCC_MSG_INFO, SCC_MSG_WARNING, SCC_MSG_ERROR`|İleti bilgi, uyarı veya hata olarak kabul edilir.|  
|`SCC_MSG_STATUS`|İleti durumunu gösterir ve durum çubuğunda görüntülenir.|  
|`SCC_MSG_DOCANCEL`|Hiçbir ileti dizesi ile gönderilir.|  
|`SCC_MSG_STARTCANCEL`|Görüntüleme başlayan bir **iptal** düğmesi.|  
|`SCC_MSG_STOPCANCEL`|Görüntüleme durdurur bir **iptal** düğmesi.|  
|`SCC_MSG_BACKGROUND_IS_CANCELLED`|IDE arka plan işlemi iptal edilecek olup olmadığını soran: IDE verir `SCC_MSG_RTN_CANCEL` işlem iptal edildi; Aksi halde, döndürür `SCC_MSG_RTN_OK`. `display_string` Parametre olarak atandığında bir [SccMsgDataIsCancelled](#LinkSccMsgDataIsCancelled) eklenti kaynak denetimi tarafından sağlanan yapısı.|  
|`SCC_MSG_BACKGROUND_ON_BEFORE_GET_FILE`|Sürüm denetiminden alınmadan önce bir dosya hakkında IDE söyler. `display_string` Parametre olarak atandığında bir [SccMsgDataOnBeforeGetFile](#LinkSccMsgDataOnBeforeGetFile) eklenti kaynak denetimi tarafından sağlanan yapısı.|  
|`SCC_MSG_BACKGROUND_ON_AFTER_GET_FILE`|Sürüm denetiminden aldıktan sonra IDE bir dosya hakkında söyler. `display_string` Parametre olarak atandığında bir [SccMsgDataOnAfterGetFile](#LinkSccMsgDataOnAfterGetFile) eklenti kaynak denetimi tarafından sağlanan yapısı.|  
|`SCC_MSG_BACKGROUND_ON_MESSAGE`|Arka plan işlemi geçerli durumunu IDE söyler. `display_string` Parametre olarak atandığında bir [SccMsgDataOnMessage](#LinkSccMsgDataOnMessage) eklenti kaynak denetimi tarafından sağlanan yapısı.|  
  
## <a name="return-value"></a>Dönüş Değeri  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_MSG_RTN_OK|Dize görüntülenen veya işlem başarıyla tamamlandı.|  
|SCC_MSG_RTN_CANCEL|Kullanıcı işlemi iptal etmek istiyor.|  
  
## <a name="example"></a>Örnek  
 IDE çağrıları varsayalım [SccGet](../extensibility/sccget-function.md) yirmi dosya adlarına sahip. Kaynak Denetim eklentisi ortasında dosya alma işlemi iptal ediliyor önlemek istiyor. Her dosya edindikten sonra çağıran `lpTextOutProc`durum bilgileri her bir dosyada geçirme ve gönderir bir `SCC_MSG_DOCANCEL` durumu yok varsa iletisi. Herhangi bir zamanda eklenti dönüş değerini alıp almadığına `SCC_MSG_RTN_CANCEL` böylece daha fazla dosya alınır IDE üzerinden, alma işlemi hemen iptal eder.  
  
## <a name="structures"></a>Yapılar  
  
###  <a name="LinkSccMsgDataIsCancelled"></a>SccMsgDataIsCancelled  
  
```cpp  
typedef struct {  
   DWORD dwBackgroundOperationID;  
} SccMsgDataIsCancelled;  
```  
  
 Bu yapı ile gönderilen `SCC_MSG_BACKGROUND_IS_CANCELLED` ileti. İptal edildi arka plan işlemi kimliği iletişim kurmak için kullanılır.  
  
###  <a name="LinkSccMsgDataOnBeforeGetFile"></a>SccMsgDataOnBeforeGetFile  
  
```cpp  
typedef struct {  
   DWORD dwBackgroundOperationID;  
   PCSTR szFile;  
} SccMsgDataOnBeforeGetFile;  
```  
  
 Bu yapı ile gönderilen `SCC_MSG_BACKGROUND_ON_BEFORE_GET_FILE` ileti. Yaklaşık alınacak dosyasının adını ve alma yaptığını arka plan işlemi kimliği iletişim kurmak için kullanılır.  
  
###  <a name="LinkSccMsgDataOnAfterGetFile"></a>SccMsgDataOnAfterGetFile  
  
```cpp  
typedef struct {  
   DWORD dwBackgroundOperationID;  
   PCSTR szFile;  
   SCCRTN sResult;  
} SccMsgDataOnAfterGetFile;  
```  
  
 Bu yapı ile gönderilen `SCC_MSG_BACKGROUND_ON_AFTER_GET_FILE` ileti. Belirtilen dosya ve bunun yanı sıra alma vermedi arka plandaki işlem Kimliğini alma sonucunu iletişim kurmak için kullanılır. Dönüş değerleri için bkz: [SccGet](../extensibility/sccget-function.md) için ne sonuç olarak verilebilir.  
  
###  <a name="LinkSccMsgDataOnMessage"></a>SccMsgDataOnMessage  
 [C++]  
  
```  
typedef struct {  
   DWORD dwBackgroundOperationID;  
   PCSTR szMessage;  
   BOOL bIsError;  
} SccMsgDataOnMessage;  
```  
  
 Bu yapı ile gönderilen `SCC_MSG_BACKGROUND_ON_MESSAGE` ileti. Arka plan işlemi geçerli durumunu iletişim kurmak için kullanılır. Durum IDE tarafından görüntülenecek dize olarak ifade edilir ve `bIsError` ileti önemini gösterir (`TRUE` bir hata iletisi; `FALSE` bir uyarı ya da bir bilgi iletisidir). Durum gönderme arka plandaki işlem Kimliğini de verilir.  
  
## <a name="code-example"></a>Kod Örneği  
 Arama kısa bir örneği burada verilmiştir `LPTEXTOUTPROC` göndermek için `SCC_MSG_BACKGROUND_ON_MESSAGE` çağrısı yapısı nasıl gösteren ileti.  
  
```cpp  
LONG SendStatusMessage(  
    LPTEXTOUTPROC pTextOutProc,  
    DWORD         dwBackgroundID,  
    LPCTSTR       pStatusMsg,  
    BOOL          bIsError)  
{  
    SccMsgDataOnMessage msgData = { 0 };  
    LONG                result  = 0;  
  
    msgData.dwBackgroundOperationID = dwBackgroundID;  
    msgData.szMessage               = pStatusMsg;  
    msgData.bIsError                = bIsError;  
  
    result = pTextOutProc(reinterpret_cast<LPCTSTR>(&msgData), SCC_MSG_BACKGROUND_ON_MESSAGE);  
    return result;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDE tarafından uygulanan geri arama işlevleri](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [Kaynak Denetimi Eklentileri](../extensibility/source-control-plug-ins.md)