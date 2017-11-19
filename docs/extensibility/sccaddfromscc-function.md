---
title: "SccAddFromScc işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccAddFromScc
helpviewer_keywords: SccAddFromScc function
ms.assetid: 902e764d-200e-46e1-8c42-4da7b037f9a0
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5027e765e12ff483a9a27795990f0ddfbb479a5c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="sccaddfromscc-function"></a>SccAddFromScc işlevi
Bu işlev kaynak denetimi sistemde zaten olan dosyaları göz olanak tanır ve daha sonra bu dosyaları bölümü geçerli projenin yapın. Örneğin, bu işlev dosya kopyalama olmadan ortak bir üst bilgi dosyası geçerli projede alabilirsiniz. Dosyaları iade dizisi `lplpFileNames`, IDE projeye eklemek için kullanıcının istediği dosyaların listesini içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccAddFromScc (  
   LPVOID   pvContext,  
   HWND     hWnd,  
   LPLONG   lpnFiles,  
   LPCSTR** lplpFileNames  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pvContext  
 [in] Kaynak Denetim eklentisi bağlam yapısı.  
  
 hWnd  
 [in] Kaynak Denetim eklentisi sağladığı tüm iletişim kutuları için üst öğe olarak kullanabileceğiniz IDE penceresi için bir tanıtıcı.  
  
 lpnFiles  
 [içinde out] İçinde eklenen dosyaların sayısı için bir arabellek. (Bu `NULL` bellek gösterdiği varsa `lplpFileNames` yayımlanması sağlamaktır. Açıklamalar için bkz.)  
  
 lplpFileNames  
 [içinde out] Tüm dosya adlarını dizin yolları olmadan işaretçiler dizisi. Bu dizi ayrılmış ve kaynak denetimi eklentisi tarafından serbest. Varsa `lpnFiles` = 1 ve `lplpFileNames` değil `NULL`, tarafından dizinin ilk adlarında işaret için `lplpFileNames` hedef klasör içerir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Dosyaları başarıyla bulunan ve projeye eklenir.|  
|SCC_I_OPERATIONCANCELED|İşlem ile herhangi bir etkisi iptal edildi.|  
|SCC_I_RELOADFILE|Bir dosya veya projeyi yeniden yüklenmesi gerekiyor.|  
  
## <a name="remarks"></a>Açıklamalar  
 IDE bu işlevi çağırır. Kaynak Denetim eklentisi bir yerel hedef klasör belirtme destekliyorsa, IDE geçirir `lpnFiles` = 1 ve yerel klasör adı içine geçirir `lplpFileNames`.  
  
 Zaman çağrısı `SccAddFromScc` işlevi döndürür, eklenti atanan değerlere `lpnFiles` ve `lplpFileNames`, dosya adı dizisi gerektiği için bellek ayırma (Bu ayırma işaretçinin değiştirir `lplpFileNames`). Kaynak Denetim eklentisi, kullanıcının dizine veya belirtilen ataması klasördeki tüm dosyaları yerleştirmek için sorumludur. IDE sonra IDE projeye dosyaları ekler.  
  
 Son olarak, bu işlev IDE tümleştirilmesidir ikinci bir kez çağıran `NULL` için `lpnFiles`. Bu kaynak denetimi dosya adı dizisinde için ayrılan belleği serbest eklenti tarafından özel bir sinyal yorumlanır`lplpFileNames``.`  
  
 `lplpFileNames`olan bir `char ***` işaretçi. Kaynak Denetim eklentisi dosya adları, böylece listenin bu API için standart şekilde geçirme işaretçiler dizisi için bir işaretçi yerleştirir.  
  
> [!NOTE]
>  İlk VSSCI API sürümleri eklenen dosyalar için hedef proje belirtmek için bir yol sağlamadı. Bu, semantiği uyum sağlayacak şekilde `lplpFIleNames` parametresi bir output parametresi yerine bir giriş/çıkış parametresine yapmak için geliştirildi. Yalnızca tek bir dosyada belirtilen diğer bir deyişle, değer işaret için tarafından `lpnFiles` = 1 then ilk öğesi `lplpFileNames` hedef klasör içerir. Bu yeni semantiği IDE çağrıları kullanılacak `SccSetOption` ile işlev `nOption`parametre kümesine `SCC_OPT_SHARESUBPROJ`. Bir kaynak denetimi eklenti semantiğini desteklemiyor varsa, döndürür `SCC_E_OPTNOTSUPPORTED`. Bunu devre dışı bırakır kullanımını yapılması **Ekle kaynak denetiminden** özelliği. Bir eklenti destekler, **Ekle kaynak denetiminden** özelliği (`SCC_CAP_ADDFROMSCC`), yeni semantiğini desteklemek gerekir ve dönüş `SCC_I_SHARESUBPROJOK`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [SccSetOption](../extensibility/sccsetoption-function.md)