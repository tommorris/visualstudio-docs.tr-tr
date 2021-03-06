---
title: SccRunScc işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccRunScc
helpviewer_keywords:
- SccRunScc function
ms.assetid: bbe7c931-b17a-4779-9cf6-59e5f9f0c172
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 322ebe148144260106fb895273b66e1b9f5696f8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31138271"
---
# <a name="sccrunscc-function"></a>SccRunScc işlevi
Bu işlev, kaynak denetimi Yönetim Aracı'nı çağırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccRunScc(  
   LPVOID  pvContext,  
   HWND    hWnd,  
   LONG    nFiles,  
   LPCSTR* lpFileNames  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pvContext  
 [in] Kaynak Denetim eklentisi bağlam yapısı.  
  
 hWnd  
 [in] Kaynak Denetim eklentisi sağladığı tüm iletişim kutuları için üst öğe olarak kullanabileceğiniz IDE penceresi için bir tanıtıcı.  
  
 nFiles  
 [in] Belirtilen dosya sayısı `lpFileNames` dizi.  
  
 lpFileNames  
 [in] Seçilen dosya adları dizisi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Kaynak denetimi Yönetim Aracı'nı başarıyla çağrıldı.|  
|SCC_I_OPERATIONCANCELED|İşlem iptal edildi.|  
|SCC_E_INITIALIZEFAILED|Kaynak denetim sistemi başlatılamadı.|  
|SCC_E_ACCESSFAILURE|Kaynak Denetim sistem ağ veya Çekişme sorun büyük olasılıkla erişilirken bir sorun oluştu.|  
|SCC_E_CONNECTIONFAILURE|Kaynak denetimi sisteme bağlanma başarısız oldu.|  
|SCC_E_FILENOTCONTROLLED|Seçilen dosya kaynak denetimi altında değil.|  
|SCC_E_NONSPECIFICERROR|Belirli olmayan hata oluştu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev bir dış yönetim aracı ile kaynak denetim sistemi özelliklerini tam aralığını erişmek arayan sağlar. Kaynak Denetim sistem kullanıcı arabirimi varsa, kaynak denetim eklentisi gerekli yönetim işlevleri gerçekleştirmek için bir arabirimi uygulayabilirsiniz.  
  
 Bu işlev bir sayısı ve dosya adları şu anda seçili dosyaları için bir dizi çağrılır. Yönetim Aracı'nı destekliyorsa, dosyaların listesini yönetim arabirimi dosyalarında önceden için kullanılabilir; Aksi takdirde, listeye göz ardı edilebilir.  
  
 Kullanıcının seçtiği olduğunda bu işlev genellikle çağrılan **başlatma \<kaynak denetim sunucusuna >** gelen **dosya** -> **kaynak denetimi** menüsü. Bu **başlatma** menü seçeneği her zaman devre dışı ya da bir kayıt defteri girdisini ayarlayarak bile gizli. Bkz: [nasıl yapılır: kaynak denetimi eklentisi yükleme](../extensibility/internals/how-to-install-a-source-control-plug-in.md) Ayrıntılar için. Bu işlev yalnızca çağrılır [SccInitialize](../extensibility/sccinitialize-function.md) döndürür `SCC_CAP_RUNSCC` yeteneği biti (bkz [yetenek bayrakları](../extensibility/capability-flags.md) bu ve diğer yetenek BITS hakkında ayrıntılar için).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [Nasıl yapılır: kaynak denetimi eklentisini yükleme](../extensibility/internals/how-to-install-a-source-control-plug-in.md)   
 [Yetenek bayrakları](../extensibility/capability-flags.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)