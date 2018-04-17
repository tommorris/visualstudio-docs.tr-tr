---
title: SccCreateSubProject işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccCreateSubProject
helpviewer_keywords:
- SccCreateSubProject function
ms.assetid: 08154aed-ae5c-463c-8694-745d0e332965
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: fa87be4c9d22aca46814e8fa284fda9d587386a7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="scccreatesubproject-function"></a>SccCreateSubProject işlevi
Bu işlev tarafından belirtilen varolan üst projesini altında verilen ada sahip bir alt oluşturur `lpParentProjPath` bağımsız değişkeni.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccCreateSubProject(  
   LPVOID pContext,  
   HWND   hWnd,  
   LPSTR  lpUser,  
   LPCSTR lpParentProjPath,  
   LPCSTR lpSubProjName,  
   LPSTR  lpAuxProjPath,  
   LPSTR  lpSubProjPath  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pContext  
 [in] Kaynak Denetim eklentisi bağlam işaretçi.  
  
 hWnd  
 [in] Kaynak Denetim eklentisi sağladığı tüm iletişim kutuları için üst öğe olarak kullanabileceğiniz IDE penceresi için bir tanıtıcı.  
  
 lpUser  
 [içinde out] Kullanıcı adı (kadar SCC_USER_SIZE, NULL Sonlandırıcı dahil olmak üzere).  
  
 lpParentProjPath  
 [in] Yolun (kadar SCC_PRJPATH_SIZE, NULL Sonlandırıcı dahil olmak üzere) üst projenin tanımlayan bir dize.  
  
 lpSubProjName  
 [in] Önerilen alt proje adı (kadar SCC_PRJPATH_SIZE, NULL Sonlandırıcı dahil olmak üzere).  
  
 lpAuxProjPath  
 [içinde out] Proje (kadar SCC_PRJPATH_SIZE, NULL Sonlandırıcı dahil olmak üzere) tanımlayan yardımcı dize.  
  
 lpSubProjPath  
 [içinde out] Alt (kadar SCC_PRJPATH_SIZE, NULL Sonlandırıcı dahil olmak üzere) yolunu tanımlayan çıkış dize.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Alt başarıyla oluşturuldu.|  
|SCC_E_INITIALIZEFAILED|Ana proje başlatılamadı.|  
|SCC_E_INVALIDUSER|Kullanıcı kaynak denetimi sisteme oturum açılamadı.|  
|SCC_E_COULDNOTCREATEPROJECT|Alt oluşturulamıyor.|  
|SCC_E_PROJSYNTAXERR|Geçersiz bir proje sözdizimi.|  
|SCC_E_UNKNOWNPROJECT|Ana proje kaynak denetimi eklenti bilinmiyor.|  
|SCC_E_INVALIDFILEPATH|Geçersiz veya kullanılamaz dosya yolu.|  
|SCC_E_NOTAUTHORIZED|Kullanıcı bu işlemi gerçekleştirmek için izin verilmiyor.|  
|SCC_E_ACCESSFAILURE|Kaynak Denetim sistem ağ veya Çekişme sorun büyük olasılıkla erişilirken bir sorun oluştu. Yeniden deneme önerilir.|  
|SCC_E_CONNECTIONFAILURE|Kaynak Denetim eklentisi bağlantı sorunu oluştu.|  
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|Belirli olmayan hata oluştu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ada sahip bir alt zaten varsa, işlev ekleyerek örneğin benzersiz bir tane oluşturmak için varsayılan adını değiştirebilirsiniz "_\<numarası >" ona. Arayan değişiklikleri kabul etmek hazırlıklı olmalıdır `lpUser`, `lpSubProjPath`, ve `lpAuxProjPath`. `lpSubProjPath` Ve`lpAuxProjPath` bağımsız değişkenleri kullanılır çağrıda [SccOpenProject](../extensibility/sccopenproject-function.md). Bunlar return bağlı çağıran tarafından değiştirilmemelidir. Bu dizeler, bir proje ile ilişkilendirmek için gereken bilgileri izlemek için eklenti kaynak denetimi için bir yol sağlar. Eklenti görüntülemek için uygun olmayabilir biçimlendirilmiş bir dize kullanabileceğinizden IDE arayan bu parametrelerden iade, bağlı görüntülenmez. İşlev başarı veya hata kodunu döndürür ve, başarılı olursa, değişkeni doldurur `lpSubProjPath` yeni projeye tam proje yoluna sahip.  
  
 Bu işlev benzer [SccGetProjPath](../extensibility/sccgetprojpath-function.md)sessizce birini seçmek için kullanıcıdan yerine bir proje oluşturur, dışında. Zaman `SccCreateSubProject` işlevi çağrıldığında, `lpParentProjName` ve `lpAuxProjPath` boş olur ve geçerli projeye karşılık gelir. Bu dizeler genellikle önceki çağrısından IDE tarafından alınan `SccGetProjPath` işlevi veya [SccGetParentProjectPath](../extensibility/sccgetparentprojectpath-function.md).  
  
 `lpUser` Bağımsız değişkeni olan kullanıcı adı. IDE daha önce gelen almış aynı kullanıcı adı geçer `SccGetProjPath`, ve kaynak denetimi eklenti adı varsayılan olarak kullanmanız gerekir. Kullanıcı eklenti ile açık bir bağlantı zaten varsa, ardından eklenti işlevi sessiz bir şekilde çalıştığından emin olmak için sizden ortadan kaldırmak denemelisiniz. Oturum açma başarısız olursa, ancak, eklenti için bir oturum açma ve, geçerli bir oturum adı yeniden geçişi aldığında, kullanıcıdan `lpUser`. Bu dize eklenti değişebilir olduğundan IDE her zaman bir arabellek ayırın boyut (SCC_USER_LEN + 1 ya da null Sonlandırıcı alanı içeren SCC_USER_SIZE). Dize değiştirdiyseniz, yeni bir dize (eski dize olarak en az geçerli olarak) geçerli oturum açma adı olmalıdır.  
  
## <a name="technical-notes-for-scccreatesubproject-and-sccgetparentprojectpath"></a>SccCreateSubProject ve SccGetParentProjectPath için teknik notlar  
 Bir kullanıcı konumları kaynak denetim sistemi seçmesi istenir sayısını en aza indirmek için Visual Studio'da çözümler ve projeler kaynak denetimine ekleme basitleştirilmiştir. Kaynak Denetim eklentisi yeni işlevler, her ikisi de destekliyorsa bu değişiklikler Visual Studio tarafından etkinleştirilen `SccCreateSubProject` ve `SccGetParentProjectPath`. Ancak, bu değişiklikleri devre dışı bırakın ve önceki Visual Studio (kaynak denetimi eklentisi API sürüm 1.1) davranışı geri döndürmek için aşağıdaki kayıt defteri girdisini kullanılabilir:  
  
 [HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl] "DoNotCreateSolutionRootFolderInSourceControl" = dword: 00000001  
  
 Bu kayıt defteri girdisi yok veya DWORD: 00000000 için ayarlarsanız yeni işlevleri kullanmak Visual Studio çalışır `SccCreateSubProject` ve `SccGetParentProjectPath`.  
  
 Kayıt defteri girdisini DWORD: 00000001 için ayarlarsanız, bu yeni işlevleri kullanmak Visual Studio çalışmaz ve kaynak denetimine ekleme işlemleri Visual Studio'nun önceki sürümlerinde olduğu gibi çalışır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [SccGetParentProjectPath](../extensibility/sccgetparentprojectpath-function.md)   
 [SccGetProjPath](../extensibility/sccgetprojpath-function.md)