---
title: Idiatable::Item | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaTable::Item method
ms.assetid: eae11b26-4807-400c-be25-e85bbc0c6b20
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e5c0c810dfd1a17f2fa63e64bf199a5882174aae
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Idiaenumınjectedsources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)