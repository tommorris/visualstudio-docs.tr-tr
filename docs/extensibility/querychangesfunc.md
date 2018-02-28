---
title: QUERYCHANGESFUNC | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- QUERYCHANGESFUNC
helpviewer_keywords:
- QUERYCHANGESFUNC callback function
- QUERYCHANGESDATA structure
ms.assetid: 9d383e2c-eee1-4996-973a-0652d4c5951c
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 43add362011b31ce695e9a8d9e77d6ca2dedb0e2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="querychangesfunc"></a>QUERYCHANGESFUNC
Tarafından kullanılan bir geri çağırma işlevini budur [SccQueryChanges](../extensibility/sccquerychanges-function.md) dosya adları topluluğu numaralandırır ve her bir dosyanın durumunu belirlemek için işlemi.  
  
 `SccQueryChanges` İşlevi dosyaları ve bir işaretçi listesini verilen `QUERYCHANGESFUNC` geri çağırma. Kaynak Denetim eklentisi verilen listesini numaralandırır ve listedeki her bir dosyanın durumu (aracılığıyla, bu geri çağırma) sağlar.  
  
## <a name="signature"></a>İmza  
  
```cpp  
typedef BOOL (*QUERYCHANGESFUNC)(  
   LPVOID pvCallerData,  
   QUERYCHANGESDATA * pChangesData  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 pvCallerData  
 [in] `pvCallerData` Parametresi için (IDE) çağıran tarafından geçirilen [SccQueryChanges](../extensibility/sccquerychanges-function.md). Kaynak Denetim eklentisi içeriği hakkında hiçbir varsayımlar bu değer olmanız gerekir.  
  
 pChangesData  
 [in] İşaretçi bir [QUERYCHANGESDATA yapısı](#LinkQUERYCHANGESDATA) bir dosyayı yapılan değişiklikler açıklayan yapısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 IDE uygun hata kodunu döndürür:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|İşleme devam edin.|  
|SCC_I_OPERATIONCANCELED|İşlemeyi durdur.|  
|SCC_E_xxx|Tüm uygun SCC hata işleme durdurmanız gerekir.|  
  
##  <a name="LinkQUERYCHANGESDATA"></a>QUERYCHANGESDATA yapısı  
 Her dosya için geçirilen yapısı aşağıdaki gibi görünür:  
  
```cpp  
struct QUERYCHANGESDATA_A  
{  
    DWORD  dwSize;  
    LPCSTR lpFileName;  
    DWORD  dwChangeType;  
    LPCSTR lpLatestName;  
};  
  
typedef struct QUERYCHANGESDATA_A QUERYCHANGESDATA;  
  
struct QUERYCHANGESDATA_W  
{  
    DWORD   dwSize;  
    LPCWSTR lpFileName;  
    DWORD   dwChangeType;  
    LPCWSTR lpLatestName;  
};  
```  
  
 dwSize  
 Bu yapı (bayt cinsinden) boyutu.  
  
 lpDosyaAdı  
 Bu öğenin özgün dosya adı.  
  
 dwChangeType  
 Dosya durumunu gösteren kod:  
  
|Kod|Açıklama|  
|----------|-----------------|  
|`SCC_CHANGE_UNKNOWN`|Nelerin değiştiğini bildiremez.|  
|`SCC_CHANGE_UNCHANGED`|Bu dosya için ad değişiklik yok.|  
|`SCC_CHANGE_DIFFERENT`|Farklı bir kimliğe sahip dosya ancak veritabanında aynı adı yok.|  
|`SCC_CHANGE_NONEXISTENT`|Dosya veritabanında veya yerel olarak mevcut değil.|  
|`SCC_CHANGE_DATABASE_DELETED`|Dosya veritabanında silinmiş.|  
|`SCC_CHANGE_LOCAL_DELETED`|Dosya yerel olarak silindi ancak dosya veritabanında hala yok. Bu belirlenemiyorsa dönmek `SCC_CHANGE_DATABASE_ADDED`.|  
|`SCC_CHANGE_DATABASE_ADDED`|Dosya veritabanına eklendi ancak yerel olarak mevcut değil.|  
|`SCC_CHANGE_LOCAL_ADDED`|Dosya veritabanında mevcut değil ve yeni yerel bir dosyadır.|  
|`SCC_CHANGE_RENAMED_TO`|Dosya yeniden adlandırılmış veya veritabanında olarak taşındığı `lpLatestName`.|  
|`SCC_CHANGE_RENAMED_FROM`|Dosya yeniden adlandırılmış veya veritabanından taşınmış `lpLatestName`; bu izlemek, çok pahalı olup olmadığını döndürür farklı bir bayrak gibi `SCC_CHANGE_DATABASE_ADDED`.|  
  
 lpLatestName  
 Bu öğe için geçerli dosya adı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDE tarafından uygulanan geri arama işlevleri](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [SccQueryChanges](../extensibility/sccquerychanges-function.md)   
 [Hata Kodları](../extensibility/error-codes.md)