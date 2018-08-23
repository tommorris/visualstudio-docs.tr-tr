---
title: SccQueryChanges işlevi | Microsoft Docs
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
- SccQueryChanges
helpviewer_keywords:
- SccQueryChanges function
ms.assetid: 4cd58eb3-6952-49b1-9620-8682e3eaa604
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 95f1e5a21ba74779080c601acd42d5deedb75d7c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688504"
---
# <a name="sccquerychanges-function"></a>SccQueryChanges İşlevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [SccQueryChanges işlevi](https://docs.microsoft.com/visualstudio/extensibility/sccquerychanges-function).  
  
Bu işlev, dosyalar, bir geri çağırma işlevi aracılığıyla her dosya için ad değişiklikleri hakkında bilgi sağlayan belirli bir listesini numaralandırır.  
  
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
 [in] Kaynak Denetimi Eklentisi bağlam işaretçisi.  
  
 nFiles  
 [in] Dosya sayısı `lpFileNames` dizisi.  
  
 lpFileNames  
 [in] Hakkında bilgi almak için dosya adları dizisi.  
  
 pfnCallback  
 [in] Listedeki her bir dosya adı için çağrılacak bir geri çağırma işlevi (bkz [QUERYCHANGESFUNC](../extensibility/querychangesfunc.md) Ayrıntılar için).  
  
 pvCallerData  
 [in] Geri çağırma işlevine geçirilen değer değişmedi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Kaynak Denetimi Eklentisi uygulanması bu işlev, aşağıdaki değerlerden birini döndürmesi beklenir:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Sorgu işlemi başarıyla tamamlandı.|  
|SCC_E_PROJNOTOPEN|Proje, kaynak denetiminde açılmadı.|  
|SCC_E_ACCESSFAILURE|Kaynak denetim sistemi, ağ veya çakışma sorunları nedeniyle muhtemelen erişilirken sorun oluştu.|  
|SCC_E_NONSPECIFICERROR|Belirtilmemiş veya genel bir hata oluştu.|  
  
## <a name="remarks"></a>Açıklamalar  
 İçin sorgulanan ad alanına değişiklikler: Bu özellikle, yeniden adlandırma, ekleme ve kaldırma bir dosya.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [QUERYCHANGESFUNC](../extensibility/querychangesfunc.md)   
 [Hata Kodları](../extensibility/error-codes.md)

