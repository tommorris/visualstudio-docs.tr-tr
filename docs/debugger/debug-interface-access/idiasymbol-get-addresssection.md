---
title: Idiasymbol::get_addresssection | Microsoft Docs
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
- IDiaSymbol::get_addressSection method
ms.assetid: fe80d479-3bb5-4f55-9b62-1bd58d0a60ce
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: af030d63c79901a41ea2704000de5b4d62e70e0c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiasymbolgetaddresssection"></a>IDiaSymbol::get_addressSection
Bir adresi konumu bölüm parçası alır. Şu durumlarda kullanın [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md) ayarlanır `LocIsStatic`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_addressSection (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Bölüm parçası olan bir adres konumunu döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi halde döndürür `S_FALSE` veya bir hata kodu.  
  
> [!NOTE]
>  Dönüş değeri `S_FALSE` özelliği simgesi kullanılabilir olmadığı anlamına gelir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem üyesinin sanal adres edinmek alacağından bir dış DLL'de bulunan statik üyeleri için bu yöntem tarafından döndürülen bölüm 0 olabilir. Sanal adresleri geçerli yalnızca [Idiasession::put_loadaddress](../../debugger/debug-interface-access/idiasession-put-loadaddress.md) yönteminde [Idiasession](../../debugger/debug-interface-access/idiasession.md) arabirimi çağrılıp çağrılmadığını DLL yük adresini belirtmek için sıfır olmayan bir parametre.  
  
 Bir adresi uzaklık parçası almak için arama [Idiasymbol::get_addressoffset](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Gereksinim|Açıklama|  
|-----------------|-----------------|  
|Başlık:|dia2.h|  
|Sürüm:|DIA SDK v7.0|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md)