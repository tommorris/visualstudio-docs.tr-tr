---
title: Idiasymbol::get_addressoffset | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_addressOffset method
ms.assetid: c15639b0-7f37-46c7-891b-40273b7f6319
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d00838fc3f76221293241656743bbf5a2a7f4d26
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31466363"
---
# <a name="idiasymbolgetaddressoffset"></a>IDiaSymbol::get_addressOffset
Bir adresi konumu uzaklık parçası alır. Şu durumlarda kullanın [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md) ayarlanır `LocIsStatic`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_addressOffset (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Uzaklık parçası olan bir adres konumunu döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi halde döndürür `S_FALSE` veya bir hata kodu.  
  
> [!NOTE]
>  Dönüş değeri `S_FALSE` özelliği simgesi kullanılabilir olmadığı anlamına gelir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem üyesinin sanal adres edinmek alacağından bir dış DLL'de bulunan statik üyeleri için bu yöntem tarafından döndürülen uzaklığı 0 olabilir. Sanal adresleri geçerli yalnızca [Idiasession::put_loadaddress](../../debugger/debug-interface-access/idiasession-put-loadaddress.md) yönteminde [Idiasession](../../debugger/debug-interface-access/idiasession.md) arabirimi çağrılıp çağrılmadığını DLL yük adresini belirtmek için sıfır olmayan bir parametre.  
  
 Bir adresi bölüm parçası almak için arama [Idiasymbol::get_addresssection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Gereksinim|Açıklama|  
|-----------------|-----------------|  
|Başlık:|dia2.h|  
|Sürüm:|DIA SDK v7.0|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md)   
 [Idiasymbol::get_addresssection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)   
 [Idiasession::put_loadaddress](../../debugger/debug-interface-access/idiasession-put-loadaddress.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)