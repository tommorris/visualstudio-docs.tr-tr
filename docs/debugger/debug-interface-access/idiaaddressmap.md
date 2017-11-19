---
title: Idiaaddressmap | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaAddressMap interface
ms.assetid: e6467529-508c-4328-85d7-89444ae4d1c1
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ef0bff2d084abc51f22bccc8aeef42d1545a5ac9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idiaaddressmap"></a>IDiaAddressMap
DIA SDK'sı sanal ve göreli sanal adresleri hata ayıklama nesneleri için nasıl hesaplar üzerinde denetim sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDiaAddressMap : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDiaAddressMap`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Idiaaddressmap::get_addressmapenabled](../../debugger/debug-interface-access/idiaaddressmap-get-addressmapenabled.md)|Belirli bir oturum için bir adres eşlemesi kurulduğunda olup olmadığını gösterir.|  
|[Idiaaddressmap::put_addressmapenabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md)|Adres eşlemesi simgesi adresleri çevirmek için kullanılması gerekip gerekmediğini belirtir.|  
|[Idiaaddressmap::get_relativevirtualaddressenabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md)|Hesaplama ve göreli sanal adresleri kullanımını etkinleştirilip etkinleştirilmediğini gösterir.|  
|[Idiaaddressmap::put_relativevirtualaddressenabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md)|İstemcinin etkinleştirmek veya devre dışı göreli sanal adresleri hesaplama olanak tanır.|  
|[Idiaaddressmap::get_imagealign](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md)|Geçerli resmi hizalaması alır.|  
|[Idiaaddressmap::put_imagealign](../../debugger/debug-interface-access/idiaaddressmap-put-imagealign.md)|Resmi hizalaması ayarlar.|  
|[Idiaaddressmap::set_imageheaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)|Ayarlar göreli sanal adres çevirisi etkinleştirmek için üstbilgiler görüntü.|  
|[Idiaaddressmap::set_addressmap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)|Görüntü düzeni çevirileri desteklemek için bir adres eşlemesi sağlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim tarafından sağlanan denetim iki sağladığınız veri kümesi içinde kapsüllenir: görüntü üstbilgileri ve adres eşlemeleri. Çoğu istemcilerin kullandığı [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) yöntemi bir görüntü ve yöntem genellikle tüm gerekli üst bilgileri ve haritalar verileri kendisini bulabilir uygun hata ayıklama bilgilerini bulamıyor. Ancak bazı istemciler özel işleme ve veri için arama uygular. Bu tür istemciler yöntemlerini kullanın `IDiaAddressMap` DIA SDK ile arama sonuçları sağlamak için arabirim.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim DIA session nesnesinden kullanılabilir. İstemci çağrılarını `QueryInterface` yöntemi arabirimde DIA oturum nesnesi, genellikle [Idiasession](../../debugger/debug-interface-access/idiasession.md)almak için `IDiaAddressMap` arabirimi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Dia2.h  
  
 Kitaplığı: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimler (arabirim erişimi SDK'SINDA hata ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [Idiasession](../../debugger/debug-interface-access/idiasession.md)