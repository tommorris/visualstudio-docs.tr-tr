---
title: Idiasession::findınjectedsource | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findInjectedSource method
ms.assetid: 907531b6-1ef8-4153-986d-b72611a1632d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: af1eba03b231bf894084090a191432c64bedc861
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiasessionfindinjectedsource"></a>IDiaSession::findInjectedSource
Öznitelik sağlayıcıları tarafından simgesi depoya yerleştirdiğiniz kaynaklarının listesi veya diğer bileşenleri derleme işleminin alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT findInjectedSource (   
   LPCOLESTR                 srcFile,  
   IDiaEnumInjectedSources** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 srcFile  
 [in] Aranacak kaynak dosyasının adı.  
  
 ppResult  
 [out] Döndürür bir [Idiaenumınjectedsources](../../debugger/debug-interface-access/idiaenuminjectedsources.md) tüm eklenen kaynakların bir listesini içeren nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaenumınjectedsources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)