---
title: Idiatable::Item | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaTable::Item method
ms.assetid: eae11b26-4807-400c-be25-e85bbc0c6b20
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cd734d287a4740a25840d93b4724b45396c7dd87
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="idiatableitem"></a>IDiaTable::Item
Belirtilen giriş tablosundaki bir başvuru alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT Item (   
   DWORD      index,  
   IUnknown** element  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `index`  
 [in] Tablo girişi aralıktaki 0 dizini `count`-1, burada `count` tarafından döndürülen [Idiatable::get_Count](../../debugger/debug-interface-access/idiatable-get-count.md)yöntemi.  
  
 `element`  
 [out] Döndürür bir `IUnknown` belirtilen tablo girişini temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir tablo nesneler koleksiyonunu temsil eder. Bu nesneler bağlı olarak öğesi parametresi için uygun arabirimi çevirebilirsiniz. Örneğin, bir tablo içeriyorsa [Idiasegment](../../debugger/debug-interface-access/idiasegment.md) nesneleri öğesi parametresi için çevirebilirsiniz sonra `IDiaSegment` arabirimi.  
  
 Çağrılacak daha yaygın bir yaklaşımdır `QueryInterface` yönteminde [Idiatable](../../debugger/debug-interface-access/idiatable.md) arabirim için uygun Numaralandırıcı arabirimi ve Numaralandırıcının belirli yöntemler İçindekiler erişmek için kullanabilirsiniz. Bkz: [Idiaenumınjectedsources](../../debugger/debug-interface-access/idiaenuminjectedsources.md) bir örnek için arabirim.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiatable](../../debugger/debug-interface-access/idiatable.md)   
 [Idiatable::get_Count](../../debugger/debug-interface-access/idiatable-get-count.md)   
 [Idiasegment](../../debugger/debug-interface-access/idiasegment.md)   
 [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)