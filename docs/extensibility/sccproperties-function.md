---
title: "SccProperties işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccProperties
helpviewer_keywords: SccProperties function
ms.assetid: 1bed38c9-73d2-4474-9717-f9dc26a89cbe
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: efaa2877743fcf69a61a79633108d203442489e0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="sccproperties-function"></a>SccProperties işlevi
Bu işlev bir dosya veya proje için kaynak denetim özelliklerini görüntüler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccProperties (  
   LPVOID pvContext,  
   HWND   hWnd,  
   LPCSTR lpFileName  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pvContext  
 [in] Kaynak Denetim eklentisi bağlam yapısı.  
  
 hWnd  
 [in] Kaynak Denetim eklentisi sağladığı tüm iletişim kutuları için üst öğe olarak kullanabileceğiniz IDE penceresi için bir tanıtıcı.  
  
 lpDosyaAdı  
 [in] Dosya veya proje tam nitelenmiş bir yol adı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Özellikler başarıyla görüntülenir.|  
|SCC_I_RELOADFILE|IDE bu dosyayı yeniden yüklemek için sürüm denetimi sistemini dosya özelliklerini değiştirdi.|  
|SCC_E_PROJNOTOPEN|Belirtilen proje kaynak denetiminde açılmadı.|  
|SCC_E_NOTAUTHORIZED|Kullanıcı bu dosya veya proje özelliklerini görüntülemek için yetkili değil.|  
|SCC_E_FILENOTCONTROLLED|Belirtilen dosya veya proje kaynak denetimi altında değil.|  
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|Bilinmeyen veya genel bir hata oluştu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kaynak Denetim eklentisi kendi iletişim kutusunda özelliklerini görüntüler.  
  
 Özellikler kaynak denetimi eklentisi tarafından tanımlanır ve eklentiden eklenti için farklı olabilir. Eklenti bir dosya kaynak denetim özelliklerini değiştirmek kullanıcının sağlar varsa, döndürme zorunluluğu `SCC_I_RELOAD` bu dosya veya projeyi yeniden yüklenmesi gerekiyor IDE sinyal.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentisi API İşlevleri](../extensibility/source-control-plug-in-api-functions.md)