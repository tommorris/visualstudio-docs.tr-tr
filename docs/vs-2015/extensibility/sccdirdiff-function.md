---
title: SccDirDiff işlevi | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SccDirDiff
helpviewer_keywords:
- SccDirDiff function
ms.assetid: 26c9ba92-e3b9-4dd2-bd5e-76b17745e308
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 38730348fcafbbed9a3284f79e14fade2efb70ba
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690668"
---
# <a name="sccdirdiff-function"></a>SccDirDiff İşlevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [SccDirDiff işlevi](https://docs.microsoft.com/visualstudio/extensibility/sccdirdiff-function).  
  
Bu işlev, geçerli yerel dizin istemci diskte ve ilgili proje kaynak denetimi altında arasındaki farkları görüntüler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
SCCRTN SccDirDiff(  
   LPVOID    pContext,  
   HWND      hWnd,  
   LPCSTR    lpDirName,  
   LONG      dwFlags,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pContext  
 [in] Kaynak Denetimi Eklentisi bağlam yapısı.  
  
 hWnd  
 [in] Kaynak Denetimi Eklentisi sağladığı herhangi bir iletişim kutusu için bir üst öğe olarak kullanabileceğiniz IDE penceresi için bir tanıtıcı.  
  
 lpDirName  
 [in] Bir görsel farkı göstermek yerel dizini tam yolu.  
  
 CertOpenStore  
 [in] Komut bayrakları (bkz. Açıklamalar bölümü).  
  
 pvOptions  
 [in] Kaynak denetimi fişi özel seçenekleri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Kaynak Denetimi Eklentisi uygulanması bu işlev, aşağıdaki değerlerden birini döndürmesi beklenir:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Diskteki kaynak kod denetimi projede aynı dizindir.|  
|SCC_I_FILESDIFFER|Kaynak kodu denetiminde projeden farklı diskte dizindir.|  
|SCC_I_RELOADFILE|Bir dosya veya projenin yeniden yüklenmesi gerekiyor.|  
|SCC_E_FILENOTCONTROLLED|Dizin, kaynak kod denetimi altında değil.|  
|SCC_E_NOTAUTHORIZED|Kullanıcı bu işlemi gerçekleştirmek için izin verilmiyor.|  
|SCC_E_ACCESSFAILURE|Kaynak denetim sistemi, ağ veya çakışma sorunları nedeniyle muhtemelen erişilirken sorun oluştu. Bir yeniden deneme önerilir.|  
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|Belirli olmayan hata oluştu.|  
|SCC_E_FILENOTEXIST|Yerel dizin bulunamadı.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev, kaynak denetimi eklentisi kullanıcı için belirtilen dizine değişikliklerin bir listesini görüntülemek için istemek için kullanılır. Eklenti, kullanıcının dizini disk üzerinde sürüm denetimi altında karşılık gelen proje arasındaki farkları görüntülemek için seçtiğiniz bir biçimde kendi penceresi açılır.  
  
 Dizinleri hiç eklenti destekler karşılaştırması, "hızlı fark" seçenekleri desteklenmiyor olsa bile, karşılaştırma dizinlerin bir dosya adı temelinde desteklemesi gerekir.  
  
|`dwFlags`|Yorumu|  
|---------------|--------------------|  
|SCC_DIFF_IGNORECASE|Büyük küçük harf duyarsız karşılaştırma (hızlı fark veya görsel için kullanılabilir).|  
|SCC_DIFF_IGNORESPACE|(Hızlı fark veya görsel için kullanılabilir) boşluk yok sayar.|  
|SCC_DIFF_QD_CONTENTS|Kaynak Denetimi Eklentisi tarafından destekleniyorsa, sessizce bayt dizin karşılaştırır.|  
|SCC_DIFF_QD_CHECKSUM|Eklenti tarafından desteklenen, sessiz bir sağlama toplamı aracılığıyla bir dizine karşılaştırır veya SCC_DIFF_QD_CONTENTS için desteklenmiyor, geri döner.|  
|SCC_DIFF_QD_TIME|Eklenti tarafından desteklenen, sessiz bir şekilde karşılaştırır, zaman damgası aracılığıyla bir dizine veya SCC_DIFF_QD_CHECKSUM veya SCC_DIFF_QD_CONTENTS desteklenmiyor, geri döner.|  
  
> [!NOTE]
>  Bu işlev, aynı komut bayrakları olarak kullanır [SccDiff](../extensibility/sccdiff-function.md). Ancak, bir kaynak denetimi eklentisi "hızlı fark" işlemi için dizinleri desteklemeyen tercih edebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentisi API İşlevleri](../extensibility/source-control-plug-in-api-functions.md)

