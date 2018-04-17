---
title: Init | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: c55ddec8-9101-4673-979b-4109caca9146
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0e81b5ac1b49e9ab021a2436013b0db3dff9a5e0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
 [UnInit](init.md)