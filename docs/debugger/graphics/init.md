---
title: Init | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c55ddec8-9101-4673-979b-4109caca9146
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f32e2e4c5c57359acdc4348f0a83399096383ff2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="init"></a>Init
Etkin olarak yakalamak ve grafik bilgilerini bir grafik günlük dosyasına kaydetmek için grafik tanılamayı uygulama bileşeninin hazırlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
void Init(  
  std::function<void (int len, wchar_t * pszBuffer)> vsgLogGetter  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `vsgLogGetter`  
 Aranabilir varlık — işlevi, işlev işaretçisi, lambda veya işlev nesnesi gibi — oluşan bir arabellek uzunluğu parametreler olarak alır `wchar_t` , arabellek ve döndürür gösteren bir işaretçi `void`. Çağrıldığında, aranabilir varlık grafik bilgilerini kaydetmek için kullanılan ve döndürmeden önce belirtilen arabellek Yazar dosya adını belirler.  
  
## <a name="remarks"></a>Açıklamalar  
 `Init` İşlevi çağrılır otomatik olarak örneği `VsgDbg` sınıfı belirterek yapılandırılmıştır `bDefaultInit` kurucusu parametresinin `true`; Aksi halde, `Init` önce açıkça çağrılmalıdır Etkin olarak yakalayabilir ve grafik bilgilerini kaydedin.  
  
 Sonlandırma ve Kapat etkin grafikler çağırarak günlük dosyası `UnInit`ve ardından yakalamak ve yeni bir grafik günlük dosyası için daha fazla grafik bilgilerini çağırarak kayıt `Init` yeniden. Bu sayıda birkaç bağımsız grafik aynı kullanarak günlük dosyalarını oluşturmak istediğiniz yineleyebilirsiniz `VsgDbg` örneği.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başlatmış](init.md)