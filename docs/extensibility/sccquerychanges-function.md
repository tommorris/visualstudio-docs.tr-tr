---
title: "SccQueryChanges işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SccQueryChanges
helpviewer_keywords:
- SccQueryChanges function
ms.assetid: 4cd58eb3-6952-49b1-9620-8682e3eaa604
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: ec61845433329645fbc4f02a72c062c3cf47f9f3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="sccquerychanges-function"></a>SccQueryChanges işlevi
Bu işlev belirli bir geri çağırma işlevini aracılığıyla her bir dosyanın adı değişiklikler hakkında bilgi sağlayan dosyaların listesini numaralandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccQueryChanges(  
   LPVOID           pContext,  
   LONG             nFiles,  
   LPCSTR*          lpFileNames,  
   QUERYCHANGESFUNC pfnCallback,  
   LPVOID           pvCallerData  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pContext  
 [in] Kaynak Denetim eklentisi bağlam işaretçi.  
  
 nFiles  
 [in] Dosya sayısı `lpFileNames` dizi.  
  
 lpFileNames  
 [in] Hakkında bilgi almak için dosya adları dizisi.  
  
 pfnCallback  
 [in] Listedeki her bir dosya adı için çağırmak için geri çağırma işlevi (bkz [QUERYCHANGESFUNC](../extensibility/querychangesfunc.md) Ayrıntılar için).  
  
 pvCallerData  
 [in] Geri çağırma işlevi değişmeden geçirilen değer.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Sorgu işlemi başarıyla tamamlandı.|  
|SCC_E_PROJNOTOPEN|Proje kaynak denetiminde açılmadı.|  
|SCC_E_ACCESSFAILURE|Kaynak Denetim sistem ağ veya Çekişme sorun büyük olasılıkla erişilirken bir sorun oluştu.|  
|SCC_E_NONSPECIFICERROR|Belirtilmemiş veya genel bir hata oluştu.|  
  
## <a name="remarks"></a>Açıklamalar  
 İçin sorgulanan ad alanına değişir: özellikle, yeniden adlandırma, ekleme ve bir dosya kaldırılıyor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [QUERYCHANGESFUNC](../extensibility/querychangesfunc.md)   
 [Hata Kodları](../extensibility/error-codes.md)