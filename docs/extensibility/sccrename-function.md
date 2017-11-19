---
title: "SccRename işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccRename
helpviewer_keywords: SccRename function
ms.assetid: b467ade6-a1db-4c0b-b60f-7850ec4f79eb
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2936c2ea4425ad6eaccc2d23853f4174e1c9c2a2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="sccrename-function"></a>SccRename işlevi
Bu işlev, kaynak denetim sisteminde bir dosyayı yeniden adlandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccRename(  
   LPVOID pvContext,  
   HWND   hWnd,  
   LPCSTR lpFileName,  
   LPCSTR lpNewName  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pvContext  
 [in] Kaynak Denetim eklentisi bağlam yapısı.  
  
 hWnd  
 [in] Kaynak Denetim eklentisi sağladığı tüm iletişim kutuları için üst öğe olarak kullanabileceğiniz IDE penceresi için bir tanıtıcı.  
  
 lpDosyaAdı  
 [in] Adı değiştirilmekte dosyasının tam dosya adı.  
  
 lpNewName  
 [in] Tam yeni adı. Dizin yolu farklıysa, ardından dosyanın bir alt dizinden diğerine taşındı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Yeniden adlandırma işlemi başarıyla tamamlandı.|  
|SCC_E_PROJNOTOPEN|Proje kaynak denetimi altında açık değil.|  
|SCC_E_FILENOTCONTROLLED|Dosya kaynak denetimi altında değil.|  
|SCC_E_ACCESSFAILURE|Kaynak Denetim sistem ağ veya Çekişme sorun büyük olasılıkla erişilirken bir sorun oluştu.|  
|SCC_E_NOTAUTHORIZED|Kullanıcı bu işlemi tamamlamak için yetkili değil.|  
|SCC_E_COULDNOTCREATEPROJECT|Projeyi yeniden adlandırma işleminin bir parçası oluşturulamadı.|  
|SCC_E_OPNOTPERFORMED|İşlem gerçekleştirilemedi.|  
|SCC_E_NONSPECIFICERROR|Belirtilmemiş veya genel bir hata oluştu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev, bir dosyayı yeniden adlandırmak veya taşımak bir konumdan diğerine kaynak denetim sistemi için kullanılabilir. Kaynak Denetim eklentisi diskteki dosya erişmek çalışmamalısınız. Yerel dosyayı yeniden adlandırın IDE'nin sorumluluğundadır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)