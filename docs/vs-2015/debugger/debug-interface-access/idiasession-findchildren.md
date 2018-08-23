---
title: Idiasession::findchildren | Microsoft Docs
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
- IDiaSession::findChildren method
ms.assetid: 5d19046f-f668-4aa9-8788-95cda9a98997
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 97fed0f8ce7ff0712054b2aa3408217efe39f706
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633508"
---
# <a name="idiasessionfindchildren"></a>IDiaSession::findChildren
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiasession::findchildren](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasession-findchildren).  
  
Ad ve simge türüyle eşleşen tüm alt öğelerini belirtilen üst tanımlayıcı alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT findChildren (   
   IDiaSymbol*       parent,  
   SymTagEnum        symtag,  
   LPCOLESTR         name,  
   DWORD             compareFlags,  
   IDiaEnumSymbols** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `parent`  
 [in] Bir [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md) üst temsil eden nesne. İşlevi, modül veya blok bu üst semboldür sonra sözcük alt öğeleri döndürülür `ppResult`. Ardından, üst simge türü ise, sınıf alt döndürülür. Bu parametre `NULL`, ardından `symtag` ayarlanmalıdır `SymTagExe` veya `SymTagNull`, genel kapsam (.exe dosyası) döndürür.  
  
 `symtag`  
 [in] Alınacak alt simge etiketi belirtir. Değerleri verilerinden alınır [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md) sabit listesi. Kümesine `SymTagNull` tüm alt öğeleri almak için.  
  
 `name`  
 [in] Alınacak alt adını belirtir. Kümesine `NULL` alınacak tüm alt öğeleri için.  
  
 `compareFlags`  
 [in] Ad eşleştirme için uygulanan karşılaştırma seçeneklerini belirtir. Değerlerini [NameSearchOptions numaralandırması](../../debugger/debug-interface-access/namesearchoptions.md) numaralandırma, tek başına veya birlikte kullanılabilir.  
  
 `ppResult`  
 [out] Döndürür bir [Idiaenumsymbols](../../debugger/debug-interface-access/idiaenumsymbols.md) alt simge listesini içeren bir nesne alındı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, yerel değişkenleri işlevinin bulmak gösterilmektedir `pFunc` ad eşleştir `szVarName`.  
  
```cpp#  
IDiaEnumSymbols* pEnum;  
pSession->findChildren( pFunc, SymTagData, szVarName, nsCaseSensitive, &pEnum );  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel bakış](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)   
 [Idiaenumsymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [Idiasession](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [NameSearchOptions numaralandırması](../../debugger/debug-interface-access/namesearchoptions.md)   
 [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md)



