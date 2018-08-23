---
title: Idiaenumınjectedsources::Item | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumInjectedSources::Item method
ms.assetid: 14846955-7270-451d-91d2-9cb34bb65187
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9a4e0dcdd523f67145cf96d0589c6559ee598afd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691468"
---
# <a name="idiaenuminjectedsourcesitem"></a>IDiaEnumInjectedSources::Item
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiaenumınjectedsources::Item](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaenuminjectedsources-item).  
  
Eklenen bir kaynak dizin yoluyla alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT Item (   
   DWORD                index,  
   IDiaInjectedSource** injectedSource  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 dizin  
 [in] Dizin [Idiaınjectedsource](../../debugger/debug-interface-access/idiainjectedsource.md) alınacak nesne. ' % S'aralığı 0 için dizinidir `count`-1, burada `count` tarafından döndürülen [Idiaenumınjectedsources::get_Count](../../debugger/debug-interface-access/idiaenuminjectedsources-get-count.md) yöntemi.  
  
 injectedSource  
 [out] Döndürür bir [Idiaınjectedsource](../../debugger/debug-interface-access/idiainjectedsource.md) eklenen kaynak temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaenumınjectedsources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)   
 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)



