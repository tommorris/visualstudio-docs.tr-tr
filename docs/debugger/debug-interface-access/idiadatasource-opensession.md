---
title: Idiadatasource::opensession | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::openSession method
ms.assetid: a3319ed0-3979-483b-9852-c0af96852c48
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 6b7cfaf3e2cf7331576ca79b9820bafb761fc44c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiadatasourceopensession"></a>IDiaDataSource::openSession
Simgeler sorgulama için bir oturum açar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT openSession (   
   IDiaSession** ppSession  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 ppSession  
 [out] Döndürür bir [Idiasession](../../debugger/debug-interface-access/idiasession.md) açık oturum temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Aşağıdaki tabloda bu yöntem için olası dönüş değerleri gösterir.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|E_UNEXPECTED|[Idiadatasource](../../debugger/debug-interface-access/idiadatasource.md) nesne daha önce başlatılmadı simgelerin bir kaynağı.|  
|E_INVALIDARG|Geçersiz `ppSession` parametresi.|  
|E_OUTOFMEMORY|Oturum açmak için bellek yetersiz.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem açılır bir [Idiasession](../../debugger/debug-interface-access/idiasession.md) nesne bir veri kaynağı için.  
  
 `IDiaSession`nesneleri veri kaynağında sorgu uygular. Bir oturum hata ayıklama simgeleri her kümesi için bir adres alanı yönetir. Veri kaynağı simgeleriyle açıklanan .exe veya .dll dosyası ise (örneğin, birden çok işlem yüklü olması nedeniyle) etkin olan, birden çok adres aralıkları, ardından her bir adres aralığı için bir oturum kullanılmalıdır.  
  
## <a name="example"></a>Örnek  
  
```C++  
IDiaSession* pSession;  
HRESULT hr = pSource->openSession( &pSession );  
if (FAILED(hr))  
{  
   // report error  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiadatasource](../../debugger/debug-interface-access/idiadatasource.md)   
 [Genel bakış](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)   
 [Idiasession](../../debugger/debug-interface-access/idiasession.md)   
 [.Pdb Dosyasını Sorgulama](../../debugger/debug-interface-access/querying-the-dot-pdb-file.md)