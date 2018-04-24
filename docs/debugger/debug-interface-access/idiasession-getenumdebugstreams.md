---
title: Idiasession::getenumdebugstreams | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::getEnumDebugStreams method
ms.assetid: d294954b-80e9-476c-b9f0-5ca6fd575f68
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 24e604734b7dceb9c0edc1fc19aaae56655ee27f
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="idiasessiongetenumdebugstreams"></a>IDiaSession::getEnumDebugStreams
Hata ayıklama veri akışlarını numaralandırılmış bir dizisini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT getEnumDebugStreams (   
   IDiaEnumDebugStreams** ppEnumDebugStreams  
)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppEnumDebugStreams`  
 [out] Döndürür bir [Idiaenumdebugstreams](../../debugger/debug-interface-access/idiaenumdebugstreams.md) hata ayıklama akışları listesini içeren nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaEnumDebugStreams](../../debugger/debug-interface-access/idiaenumdebugstreams.md)