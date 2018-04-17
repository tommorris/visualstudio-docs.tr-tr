---
title: SccGetProjPath işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccGetProjPath
helpviewer_keywords:
- SccGetProjPath function
ms.assetid: 1079847e-d45f-4cb8-9d92-1e01ce5d08f6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7ef5041b483e85e0806827f7d1188d432b476c5b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="sccgetprojpath-function"></a>SccGetProjPath işlevi
Bu işlev yalnızca kaynak denetimi için eklenti anlamlı bir dize bir proje yolu kullanıcıya sorar. Kullanıcı olduğunda çağrılır:  
  
-   Yeni proje oluşturma  
  
-   Varolan projeyi sürüm denetimine ekleme  
  
-   Mevcut bir sürüm denetim projesini bulmaya çalışırken  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccGetProjPath (  
   LPVOID pvContext,  
   HWND   hWnd,  
   LPSTR  lpUser,  
   LPSTR  lpProjName,  
   LPSTR  lpLocalPath,  
   LPSTR  lpAuxProjPath,  
   BOOL   bAllowChangePath,  
   LPBOOL pbNew  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pvContext  
 [in] Kaynak Denetim eklentisi bağlam yapısı.  
  
 hWnd  
 [in] Kaynak Denetim eklentisi sağladığı tüm iletişim kutuları için üst öğe olarak kullanabileceğiniz IDE penceresi için bir tanıtıcı.  
  
 lpUser  
 [içinde out] Kullanıcı adı (not NULL Sonlandırıcı dahil olmak üzere SCC_USER_SIZE aşmayı)  
  
 lpProjName  
 [içinde out] IDE proje, project çalışma alanı veya derleme görevleri dosyası (not NULL Sonlandırıcı dahil olmak üzere SCC_PRJPATH_SIZE aşmayı) adı.  
  
 lpLocalPath  
 [içinde out] Projenin çalışma yolu. Varsa `bAllowChangePath` olan `TRUE`, kaynak denetim eklentisi bu dizenin (null Sonlandırıcı dahil olmak üzere _MAX_PATH aşan değil) değiştirebilirsiniz.  
  
 lpAuxProjPath  
 [içinde out] Döndürülen proje yolu (NULL Sonlandırıcı dahil olmak üzere SCC_PRJPATH_SIZE aşmayı değil) için bir arabellek.  
  
 bAllowChangePath  
 [in] Bu ise `TRUE`, kaynak denetim eklentisi sor ve değiştirme `lpLocalPath` dize.  
  
 pbNew  
 [içinde out] Gelen değer yeni bir proje oluşturulup oluşturulmayacağını belirtir. Döndürülen projesi oluşturma başarıyı gösterir:  
  
|gelen|Yorumu|  
|--------------|--------------------|  
|TRUE|Kullanıcı yeni bir proje oluşturabilirsiniz.|  
|FALSE|Kullanıcı yeni bir proje oluşturabilirsiniz.|  
  
|Giden|Yorumu|  
|--------------|--------------------|  
|TRUE|Yeni bir proje oluşturuldu.|  
|FALSE|Varolan projeyi seçilmedi.|  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Proje başarıyla oluşturuldu veya alınır.|  
|SCC_I_OPERATIONCANCELED|İşlem iptal edildi.|  
|SCC_E_ACCESSFAILURE|Kaynak Denetim sistem ağ veya Çekişme sorun büyük olasılıkla erişilirken bir sorun oluştu.|  
|SCC_E_CONNECTIONFAILURE|Kaynak denetim sistemi bağlanmaya çalışırken bir hata oluştu.|  
|SCC_E_NONSPECIFICERROR|Belirlenemeyen bir hata oluştu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev amacı IDE parametreleri edinmeye `lpProjName` ve `lpAuxProjPath`. Kaynak Denetim eklentisi bu bilgiyi kullanıcıya sorar sonra bu iki dizeler IDE geçirir. IDE bu dizeler, çözüm dosyasındaki devam ederse ve bunları geçirmeden [SccOpenProject](../extensibility/sccopenproject-function.md) her kullanıcı bu proje açar. Bu dizeler eklenti bir projeyle ilişkili bilgileri izlemek etkinleştirin.  
  
 İşlev ilk kez çağrıldığında `lpAuxProjPath` boş bir dize olarak ayarlayın. `lProjName` boş olabilir veya eklenti kaynak denetimi kullanın veya yoksay IDE proje adı içeriyor olabilir. İşlev başarıyla geri döndüğünde, eklenti iki karşılık gelen dizeyi döndürür. IDE bu dizeler hakkında hiçbir varsayımlar yapar, bunları kullanmaz ve bunları değiştirmek kullanıcı izin vermez. Kullanıcı ayarlarını değiştirmek isterse, IDE çağıracak `SccGetProjPath` aynı değerleri, geçirme önceki zaman yeniden almış. Bu, bu iki dizeler üzerinde eklenti tam denetim verir.  
  
 İçin `lpUser`IDE bir kullanıcı adı iletebilir veya yalnızca boş bir dize için bir işaretçi iletebilir. Kaynak Denetim eklentisi bir kullanıcı adı varsa, varsayılan olarak kullanmalısınız. Ancak, bir ad geçirilmedi veya verilen ada sahip bir oturum açma başarısız olursa, eklenti için bir oturum açma ve geçişi adı yeniden kullanıcıdan `lpUser` aldığı geçerli bir oturum açma zaman. Bu dize eklenti değişebilir olduğundan IDE her zaman bir arabellek boyutunu tahsis (`SCC_USER_LEN`+ 1).  
  
> [!NOTE]
>  IDE gerçekleştirir ilk eylem ya da bir çağrı olabilir `SccOpenProject` işlevi veya `SccGetProjPath` işlevi. Bu nedenle, bunların her ikisi de aynı olması `lpUser` parametresi ya da aynı anda kullanıcı oturum eklenti kaynak denetimi sağlar. İşlev dönüş hata gösterir olsa bile eklenti bu dize bir geçerli oturum açma adı ile doldurmanız gerekir.  
  
 `lpLocalPath` Burada kullanıcının proje tutar dizindir. Boş bir dize olabilir. (Durumunda, kaynak denetimi sisteminden bir proje yüklemeyi deneyen bir kullanıcı gibi) şu anda tanımlanmış hiçbir dizin açıksa ve durumdaysa `bAllowChangePath` olan `TRUE`, kaynak denetim eklentisi giriş kullanıcıdan veya yerleştirmek için başka bir yöntem kullanın, kendi dizeye `lpLocalPath`. Varsa `bAllowChangePath` olan `FALSE`, kullanıcının belirtilen dizinde zaten çalıştığından eklenti dize değiştirilmemesi gerekir.  
  
 Kullanıcı kaynak denetimi altında yerleştirilecek yeni bir proje oluşturursa, kaynak denetim eklentisi gerçekte, kaynak denetim sistemi aynı anda oluşturmayabilir `SccGetProjPath` olarak adlandırılır. Bunun yerine, için sıfır olmayan bir değer dizesiyle boyunca geri geçirir `pbNew`, projenin kaynak denetim sistemi oluşturulacak belirten.  
  
 Örneğin, bir kullanıcı **yeni proje** Visual Studio sihirbazında kaynak denetimine bilgilendirilmesine proje ekler, Visual Studio bu işlevi çağırır ve eklenti için kaynak denetimi sistemindeki yeni bir proje oluşturmak uygun olup olmadığını belirler Visual Studio projesi içerir. Kullanıcı tıklarsa **iptal** Sihirbazı tamamlamadan önce projenin hiçbir zaman oluşturulur. Kullanıcı tıklarsa **Tamam**, Visual Studio çağırır `SccOpenProject`, içinde geçen `SCC_OPT_CREATEIFNEW`, ve o anda denetlenen kaynak projesi oluşturulur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)