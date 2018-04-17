---
title: SccGetParentProjectPath işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccGetParentProjectPath
helpviewer_keywords:
- SccGetParentProjectPath function
ms.assetid: 62a71579-36b3-48b9-a1c8-04ab100efa08
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ea52e0d4c6242c57447cd47d41b716ba5e93a2f6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="sccgetparentprojectpath-function"></a>SccGetParentProjectPath işlevi
Bu işlev belirtilen proje ana proje konumunu belirler. Kullanıcının kaynak denetimi için Visual Studio projesi eklerken bu işlev çağrılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccGetParentProjectPath(  
   LPVOID pContext,  
   HWND   hWnd,  
   LPSTR  lpUser,  
   LPCSTR lpProjPath,  
   LPSTR  lpAuxProjPath,  
   LPSTR  lpParentProjPath  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pContext  
 [in] Kaynak Denetim eklentisi bağlam işaretçi.  
  
 hWnd  
 [in] Kaynak Denetim eklentisi sağladığı tüm iletişim kutuları için üst öğe olarak kullanabileceğiniz IDE penceresi için bir tanıtıcı.  
  
 lpUser  
 [içinde out] Kullanıcı adı (kadar SCC_USER_SIZE, NULL Sonlandırıcı dahil olmak üzere).  
  
 lpProjPath  
 [in] Proje yolu (kadar SCC_PRJPATH_SIZE, NULL Sonlandırıcı dahil olmak üzere) tanımlayan dize.  
  
 lpAuxProjPath  
 [içinde out] Proje (kadar SCC_PRJPATH_SIZE, NULL Sonlandırıcı dahil olmak üzere) tanımlayan yardımcı dize.  
  
 lpParentProjPath  
 [içinde out] Ana proje yolu (kadar SCC_PRJPATH_SIZE, NULL Sonlandırıcı dahil olmak üzere) tanımlayan çıkış dize.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Ana proje yolu başarıyla alındı.|  
|SCC_E_INITIALIZEFAILED|Proje başlatılamadı.|  
|SCC_E_INVALIDUSER|Kullanıcının kaynak denetimi eklenti oturum açılamadı.|  
|SCC_E_UNKNOWNPROJECT|Proje kaynak denetimi eklenti bilinmiyor.|  
|SCC_E_INVALIDFILEPATH|Geçersiz veya kullanılamaz dosya yolu.|  
|SCC_E_NOTAUTHORIZED|Kullanıcı bu işlemi gerçekleştirmek için izin verilmiyor.|  
|SCC_E_ACCESSFAILURE|Kaynak Denetim sistem ağ veya Çekişme sorun büyük olasılıkla erişilirken bir sorun oluştu. Yeniden deneme önerilir.|  
|SCC_E_PROJSYNTAXERR|Geçersiz bir proje sözdizimi.|  
|SCC_E_CONNECTIONFAILURE|Bağlantı sorunu depolar.|  
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|Belirli olmayan hata oluştu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev başarı veya hata kodunu döndürür ve, başarılı olursa, değişkeni doldurur `lpParentProjPath` belirtilen proje tam proje yoluna sahip.  
  
 Bu işlev, üst varolan projeyi Proje yolunu döndürür. Kök proje için işlevi geçirildi proje yolu döndürür (diğer bir deyişle, aynı kök proje yolu). Proje yolu yalnızca kaynak denetimi için eklenti anlamlı bir dize olduğunu unutmayın.  
  
 IDE değişiklikleri kabul etmek için hazırlanan `lpUser` ve `lpAuxProjPath` parametrelerini de. IDE bu dizeler kalıcı hale getirmek ve bunları geçirmek [SccOpenProject](../extensibility/sccopenproject-function.md) kullanıcı açtığında bu proje gelecekte. Bu dizeler, bu nedenle, eklenti, bir proje ile ilişkilendirmek için gereken izleme bilgileri için kaynak denetimi için bir yol sağlar.  
  
 Bu işlev benzer [SccGetProjPath](../extensibility/sccgetprojpath-function.md), kullanıcının bir proje seçmesini sormaz dışında. Ayrıca hiçbir zaman yalnızca var olan bir proje ile çalışır ancak yeni bir proje oluşturur.  
  
 Zaman `SccGetParentProjectPath` olarak adlandırılır, `lpProjPath` ve `lpAuxProjPath` boş olur ve geçerli projeye karşılık gelir. Bu dizeler genellikle önceki çağrısından IDE tarafından alınan `SccGetProjPath` işlevi.  
  
 `lpUser` Bağımsız değişkeni olan kullanıcı adı. IDE daha önce gelen almış aynı kullanıcı adı geçer `SccGetProjPath` işlevi ve kaynak denetim eklentisi kullanması gereken adı varsayılan olarak. Kullanıcı eklenti ile açık bir bağlantı zaten varsa, ardından eklenti işlevi sessiz bir şekilde çalıştığından emin olmak için sizden ortadan kaldırmak denemelisiniz. Oturum açma başarısız olursa, ancak, eklenti için bir oturum açma ve, geçerli bir oturum adı yeniden geçişi aldığında, kullanıcıdan `lpUser`. Bu dize eklenti değişebilir olduğundan IDE her zaman bir arabellek boyutunu tahsis (`SCC_USER_LEN`+ 1). Dize değiştirdiyseniz, yeni bir dize (eski dize olarak en az geçerli olarak) geçerli oturum açma adı olmalıdır.  
  
## <a name="technical-notes-for-scccreatesubproject-and-sccgetparentprojectpath"></a>SccCreateSubProject ve SccGetParentProjectPath için teknik notlar  
 Bir kullanıcı konumları kaynak denetim sistemi seçmesi istenir sayısını en aza indirmek için Visual Studio'da çözümler ve projeler kaynak denetimine ekleme basitleştirilmiştir. Kaynak Denetim eklentisi yeni işlevler, her ikisi de destekliyorsa bu değişiklikler Visual Studio tarafından etkinleştirilen [SccCreateSubProject](../extensibility/scccreatesubproject-function.md) ve `SccGetParentProjectPath` işlevi. Ancak, bu değişiklikleri devre dışı bırakın ve önceki Visual Studio (kaynak denetimi eklentisi API sürüm 1.1) davranışı geri döndürmek için aşağıdaki kayıt defteri girdisini kullanılabilir:  
  
 [HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl] "DoNotCreateSolutionRootFolderInSourceControl" = dword: 00000001  
  
 Bu kayıt defteri girdisi yok veya DWORD: 00000000 için ayarlarsanız yeni işlevleri kullanmak Visual Studio çalışır `SccCreateSubProject`ve`SccGetParentProjectPath`.  
  
 Kayıt defteri girdisini DWORD: 00000001 için ayarlarsanız, bu yeni işlevleri kullanmak Visual Studio çalışmaz ve kaynak denetimine ekleme işlemleri Visual Studio'nun önceki sürümlerinde olduğu gibi çalışır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [SccCreateSubProject](../extensibility/scccreatesubproject-function.md)   
 [SccGetProjPath](../extensibility/sccgetprojpath-function.md)