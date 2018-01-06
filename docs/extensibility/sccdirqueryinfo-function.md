---
title: "SccDirQueryInfo işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccDirQueryInfo
helpviewer_keywords: SccDirQueryInfo function
ms.assetid: 459e2d99-573d-47c4-b834-6d82c5e14162
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: c7a930c0fcdffbc76bba431012d76dd6d13686d0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="sccdirqueryinfo-function"></a>SccDirQueryInfo işlevi
Bu işlev, bunların geçerli durum için tam dizinler listesinde inceler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccDirQueryInfo(  
LPVOID  pContext,  
LONG    nDirs,  
LPCSTR* lpDirNames,  
LPLONG  lpStatus  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pContext  
 [in] Kaynak Denetim eklentisi bağlam yapısı.  
  
 nDirs  
 [in] Sorgulanacak seçili dizinleri sayısı.  
  
 lpDirNames  
 [in] Tam yollar Sorgulanacak dizinlerin bir dizi.  
  
 lpStatus  
 [içinde out] Kaynak Denetim durumu bayrakları döndürülecek eklentisi için bir dizi yapısı (bkz [Directory durum kodu](../extensibility/directory-status-code-enumerator.md) Ayrıntılar için).  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Sorgu başarılı oldu.|  
|SCC_E_OPNOTSUPPORTED|Kaynak kodu denetim sistem bu işlemi desteklemiyor.|  
|SCC_E_ACCESSFAILURE|Kaynak Denetim sistem ağ veya Çekişme sorun büyük olasılıkla erişilirken bir sorun oluştu. Yeniden deneme önerilir.|  
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|Belirli olmayan hata oluştu.|  
  
## <a name="remarks"></a>Açıklamalar  
 İşlev dönüş dizi bitten, bir bit maskesi ile doldurur `SCC_DIRSTATUS` ailesi (bkz [Directory durum kodu](../extensibility/directory-status-code-enumerator.md)), verilen her dizin için bir giriş. Durum dizi çağıran tarafından ayrılır.  
  
 Bir dizin karşılık gelen bir proje sahip olup olmadığını sorgulayarak dizin kaynak denetimi altında olup olmadığını denetlemek için yeniden adlandırmadan önce IDE bu işlev kullanır. Dizin kaynak denetimi altında değilse, IDE kullanıcıya uygun uyarı sağlayabilir.  
  
> [!NOTE]
>  Bir veya daha fazla durum değerleri uygulamak bir kaynak denetim eklentisi seçerse, uygulanmayan BITS sıfır olarak ayarlanması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [Dizin durum kodu](../extensibility/directory-status-code-enumerator.md)