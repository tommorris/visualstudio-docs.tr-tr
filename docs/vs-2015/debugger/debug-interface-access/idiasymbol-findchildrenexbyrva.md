---
title: IDiaSymbol::findChildrenExByRVA | Microsoft Docs
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
- IDiaSymbol::findChildrenExByRVA
ms.assetid: cbc57c6c-7d64-4469-a114-1dd6671e5ec5
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ae091a82542b9ed3f32b93a95995cdb0fc2cfadd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693833"
---
# <a name="idiasymbolfindchildrenexbyrva"></a>IDiaSymbol::findChildrenExByRVA
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDiaSymbol::findChildrenExByRVA](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-findchildrenexbyrva).  
  
Belirlediğiniz göreli sanal adresten (RVA) geçerli olan alt simge alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT findChildrenExByRVA (   
   enum SymTagEnum   symtag,  
   LPCOLESTR         name,  
   DWORD             compareFlags,  
   DWORD             address,  
   IDiaEnumSymbols** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `symtag`  
 [in] Alınacak, alt simge etiketleri sınıfında tanımlandığı gibi belirtir [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md). Kümesine `SymTagNull` alınacak tüm alt öğeleri için.  
  
 `name`  
 [in] Alınacak alt adını belirtir. Kümesine `NULL` alınacak tüm alt öğeleri için.  
  
 `compareFlags`  
 [in] Ad eşleştirme için uygulanacak karşılaştırma seçeneklerini belirtir. Değerlerini [NameSearchOptions numaralandırması](../../debugger/debug-interface-access/namesearchoptions.md) numaralandırma, tek başına veya birlikte kullanılabilir.  
  
 `address`  
 [in] RVA belirtir.  
  
 `ppResult`  
 [out] Döndürür bir [Idiaenumsymbols](../../debugger/debug-interface-access/idiaenumsymbols.md) alt simge listesini içeren bir nesne alındı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` simgenin en az bir alt öğe bulunamadı ya da döndürür `S_FALSE` alt öğe bulundu; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Döndürülen yerel semboller dinamik aralık bilgilerini içerir.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: Dia2.h  
  
 Kitaplık: diaguids.lib  
  
 DLL: msdia100.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md)   
 [Idiaenumsymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [Idiasession::findchildren](../../debugger/debug-interface-access/idiasession-findchildren.md)   
 [NameSearchOptions numaralandırması](../../debugger/debug-interface-access/namesearchoptions.md)



