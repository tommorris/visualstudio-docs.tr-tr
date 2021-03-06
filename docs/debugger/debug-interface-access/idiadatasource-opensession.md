---
title: Idiadatasource::opensession | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::openSession method
ms.assetid: a3319ed0-3979-483b-9852-c0af96852c48
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 39fe9bf3a67d3ad5f26ff7c4ccdaa9772cf1346b
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31459873"
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
  
 `IDiaSession` nesneleri veri kaynağında sorgu uygular. Bir oturum hata ayıklama simgeleri her kümesi için bir adres alanı yönetir. Veri kaynağı simgeleriyle açıklanan .exe veya .dll dosyası ise (örneğin, birden çok işlem yüklü olması nedeniyle) etkin olan, birden çok adres aralıkları, ardından her bir adres aralığı için bir oturum kullanılmalıdır.  
  
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