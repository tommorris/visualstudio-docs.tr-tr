---
title: SccOpenProject işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccOpenProject
helpviewer_keywords:
- SccOpenProject function
ms.assetid: d609510b-660a-46d7-b93d-2406df20434d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 15d9cf6d5fa4533b5ee0ff65f8aeae86df3d571a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31143380"
---
# <a name="sccopenproject-function"></a>SccOpenProject işlevi
Bu işlev, mevcut bir kaynak denetimi projesini açar veya yeni bir tane oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccOpenProject (  
   LPVOID        pvContext,  
   HWND          hWnd,  
   LPSTR         lpUser,  
   LPCSTR        lpProjName,  
   LPCSTR        lpLocalProjPath,  
   LPSTR         lpAuxProjPath,  
   LPCSTR        lpComment,  
   LPTEXTOUTPROC lpTextOutProc,  
   LONG          dwFlags  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pvContext  
 [in] Kaynak Denetim eklentisi bağlam yapısı.  
  
 hWnd  
 [in] Kaynak Denetim eklentisi sağladığı tüm iletişim kutuları için üst öğe olarak kullanabileceğiniz IDE penceresi için bir tanıtıcı.  
  
 lpUser  
 [içinde out] (NULL Sonlandırıcı dahil olmak üzere SCC_USER_SIZE aşmayı değil) kullanıcı adı.  
  
 lpProjName  
 [in] Projenin adını tanımlayan dize.  
  
 lpLocalProjPath  
 [in] Proje için çalışma klasörü yolu.  
  
 lpAuxProjPath  
 [içinde out] Proje (not NULL Sonlandırıcı dahil olmak üzere SCC_AUXPATH_SIZE aşmayı) tanımlayan bir isteğe bağlı yardımcı dize.  
  
 lpComment  
 [in] Oluşturulmakta olan yeni bir proje için açıklama.  
  
 lpTextOutProc  
 [in] Eklenti kaynak denetiminden çıkış metni görüntülemek için bir isteğe bağlı geri çağırma işlevi.  
  
 dwFlags  
 [in] Yeni bir proje proje kaynağına bilinmeyen ise oluşturulması gerekip gerekmediğini sinyalleri eklenti denetler. Değer bir bileşimi olabilir `SCC_OP_CREATEIFNEW` ve `SCC_OP_SILENTOPEN.`  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Proje açarken başarılı.|  
|SCC_E_INITIALIZEFAILED|Proje başlatılamadı.|  
|SCC_E_INVALIDUSER|Kullanıcı kaynak denetimi sisteme oturum açılamadı.|  
|SCC_E_COULDNOTCREATEPROJECT|Proje çağrıdan önce mevcut değildir;  `SCC_OPT_CREATEIFNEW` bayrağı ayarlandığından, ancak proje oluşturulamadı.|  
|SCC_E_PROJSYNTAXERR|Geçersiz bir proje sözdizimi.|  
|SCC_E_UNKNOWNPROJECT|Kaynak Denetimi Eklentisi, bilinmeyen bir projedir ve `SCC_OPT_CREATEIFNEW` bayrağı ayarlanmamış.|  
|SCC_E_INVALIDFILEPATH|Geçersiz veya kullanılamaz dosya yolu.|  
|SCC_E_NOTAUTHORIZED|Kullanıcı bu işlemi gerçekleştirmek için izin verilmiyor.|  
|SCC_E_ACCESSFAILURE|Kaynak Denetim sistem ağ veya Çekişme sorun büyük olasılıkla erişilirken bir sorun oluştu. Yeniden deneme önerilir.|  
|SCC_E_NONSPECFICERROR|Belirli olmayan bir hata; Kaynak denetim sistemi başlatılamadı.|  
  
## <a name="remarks"></a>Açıklamalar  
 IDE içinde bir kullanıcı adı iletebilir (`lpUser`), ya da yalnızca boş bir dize için bir işaretçi iletebilir. Kaynak Denetim eklentisi bir kullanıcı adı varsa, varsayılan olarak kullanmalısınız. Ancak, bir ad geçirilmedi ya da verilen ada sahip bir oturum açma başarısız olursa, eklenti kullanıcıdan oturum açmak için ve geçerli ad döndürülecek `lpUser` aldığı geçerli bir oturum açma zaman`.` kullanıcı adı dizesi eklenti değişebilir çünkü , IDE her zaman bir arabellek boyutunu tahsis (`SCC_USER_LEN`+ 1 ya da null Sonlandırıcı alanı içeren SCC_USER_SIZE).  
  
> [!NOTE]
>  IDE gereken gerçekleştirmek için ilk eylem çağrısı olabilir `SccOpenProject` işlevi veya [SccGetProjPath](../extensibility/sccgetprojpath-function.md). Bu nedenle, bunların her ikisi de aynı olması `lpUser` parametresi.  
  
 `lpAuxProjPath` ve`lpProjName` çözüm dosyasından okuma veya çağrısından döndürülen `SccGetProjPath` işlevi. Bu parametreler eklenti kaynak denetimi proje ile ilişkilendirir dizeler içeriyor ve yalnızca eklenti için anlamlı. Bu tür bir dize çözüm dosyasında varsa ve kullanıcı göz atmak için istenmedi (hangi döndürebildiği bir dize aracılığıyla `SccGetProjPath` işlevi), IDE boş dizeler için her ikisini de geçirir `lpAuxProjPath` ve `lpProjName`ve güncelleştirilmesi için bu değeri bekler tarafından eklenti olduğunda bu işlev döndürür.  
  
 `lpTextOutProc` IDE komut sonuç çıktısı görüntüleme amacıyla eklenti kaynak denetimi tarafından sağlanan bir geri çağırma işlevi için bir işaretçidir. Bu geri çağırma işlevi içinde ayrıntılı olarak açıklanmıştır [LPTEXTOUTPROC](../extensibility/lptextoutproc.md).  
  
> [!NOTE]
>  Bu yararlanmak kaynak denetim eklentisi çalışırsa, onu ayarlamış olmanız gerekir `SCC_CAP_TEXTOUT` içinde bayrak [SccInitialize](../extensibility/sccinitialize-function.md). Bu bayrak ayarlanmadı veya IDE bu özelliği desteklemez `lpTextOutProc` olacaktır `NULL`.  
  
 `dwFlags` Parametre açılmakta proje şu anda yok gerektiğinde, sonucu denetler. İki bit işaretleri oluşur `SCC_OP_CREATEIFNEW` ve `SCC_OP_SILENTOPEN`. Zaten açık proje yoksa işlevi yalnızca projeyi açar ve döndürür `SCC_OK`. Proje yoksa ve varsa `SCC_OP_CREATEIFNEW` bayrağı üzerinde eklenti kaynak denetimi kaynak denetim sistemi projesi oluşturun, bunu açıp dönmek `SCC_OK`. Proje yoksa ve `SCC_OP_CREATEIFNEW` bayrağı kapalıdır eklenti sonra için denetlemelisiniz `SCC_OP_SILENTOPEN` bayrağı. Bu bayrağı açık değilse, eklenti kullanıcı için bir proje adı isteyebilir. Bu bayrak üzerindeyse, eklenti yalnızca döndürmelidir `SCC_E_UNKNOWNPROJECT`.  
  
## <a name="calling-order"></a>Arama sırası  
 Olaylar, normal seyrinde [SccInitialize](../extensibility/sccinitialize-function.md) önce bir kaynak denetim oturumu açmak için çağrılması. Bir oturum için bir arama oluşabilir `SccOpenProject`, diğer kaynak denetim eklentisi API işlev çağrılarını tarafından izlenen ve çağrısıyla sonlandıracak [SccCloseProject](../extensibility/scccloseproject-function.md). Bu tür oturumları birkaç kez önce yinelenebilir [SccUninitialize](../extensibility/sccuninitialize-function.md) olarak adlandırılır.  
  
 Kaynak denetimi için Eklenti kümeleri `SCC_CAP_REENTRANT` içinde bit `SccInitialize`, yukarıdaki oturum dizisi paralel olarak birçok kez yinelenebilir sonra. Farklı `pvContext` yapıları her farklı oturumları izlemek `pvContext` aynı anda bir açık projesi ile ilişkilidir. Temel`pvContext` parametresi, eklenti hangi proje belirli herhangi bir çağrıda başvuruluyor belirleyebilirsiniz. Yetenek bit ise `SCC_CAP_REENTRANT` , nonreentrant ayarlanmadı kaynak denetim eklentileri birden çok projelerle çalışmak için kendi yeteneği sınırlıdır.  
  
> [!NOTE]
>  `SCC_CAP_REENTRANT` Bit sürümünde kaynak denetim eklentisi API 1.1 sunulmuştur. Ayarlanmadı veya sürüm 1.0 göz ardı edilir ve tüm sürüm 1.0 kaynak denetim eklentileri nonreentrant olduğu varsayılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [SccCloseProject](../extensibility/scccloseproject-function.md)   
 [SccGetProjPath](../extensibility/sccgetprojpath-function.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)   
 [SccUninitialize](../extensibility/sccuninitialize-function.md)   
 [Dize uzunluğu kısıtlamalar](../extensibility/restrictions-on-string-lengths.md)   
 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)