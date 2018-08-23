---
title: Idiaenumtables::Item | Microsoft Docs
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
- IDiaEnumTables::Item method
ms.assetid: d65ab262-10c6-48ce-95a3-b5e4cb2c85af
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ea80cbcda60b54f17e79e492c43058579465ad90
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42689634"
---
# <a name="idiaenumtablesitem"></a>IDiaEnumTables::Item
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiaenumtables::Item](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaenumtables-item).  
  
Bir dizin veya ad ile bir tabloyu alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT Item (   
   VARIANT     index,  
   IDiaTable** table  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `index`  
 [in] Dizin veya adını [Idiatable](../../debugger/debug-interface-access/idiatable.md) alınacak. Bir tamsayı değişken kullandıysanız, aralığı 0 olmalıdır `count`-1, burada `count` tarafından döndürülen [Idiaenumtables::get_Count](../../debugger/debug-interface-access/idiaenumtables-get-count.md) yöntemi.  
  
 `table`  
 [out] Döndürür bir [Idiatable](../../debugger/debug-interface-access/idiatable.md) istediğiniz tabloyu temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir dize değişken belirtilirse, dize belirli bir tablo adları. Adı bir tablo adlarının sınıfında tanımlandığı gibi olmalıdır [sabitler (arabirim erişimi SDK'ı hata ayıklama)](../../debugger/debug-interface-access/constants-debug-interface-access-sdk.md).  
  
## <a name="example"></a>Örnek  
  
```cpp#  
VARIANT var;  
var.vt = VT_BSTR;  
var.bstrVal = SysAllocString(DiaTable_Symbols );  
IDiaTable* pTable;  
pEnumTables->Item( var, &pTable );  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaenumtables](../../debugger/debug-interface-access/idiaenumtables.md)   
 [Idiatable](../../debugger/debug-interface-access/idiatable.md)   
 [Idiaenumtables::get_Count](../../debugger/debug-interface-access/idiaenumtables-get-count.md)   
 [Sabitler (Arabirim Erişimi SDK'sında Hata Ayıklama)](../../debugger/debug-interface-access/constants-debug-interface-access-sdk.md)



