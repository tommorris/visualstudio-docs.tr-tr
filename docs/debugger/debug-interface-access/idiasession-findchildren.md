---
title: Idiasession::findchildren | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findChildren method
ms.assetid: 5d19046f-f668-4aa9-8788-95cda9a98997
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cc9b9aabf920fa33828d86e2f0c3ac96f7e6dbdb
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31465349"
---
# <a name="idiasessionfindchildren"></a>IDiaSession::findChildren
Ad ve simge türüyle eşleşen tüm alt öğeleri belirtilen üst tanımlayıcı alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
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
 [in] Bir [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md) üst temsil eden nesne. Bu üst simgeyi işlevi, modül veya blok olan sonra sözcük alt döndürülür `ppResult`. Üst simge türü ise, sınıf alt döndürülür. Bu parametre ise `NULL`, ardından `symtag` ayarlanmalıdır `SymTagExe` veya `SymTagNull`, genel kapsam (.exe dosyası) döndürür.  
  
 `symtag`  
 [in] Alınacak alt simge etiketi belirtir. Değerleri gerçekleştirilecek [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md) numaralandırması. Kümesine `SymTagNull` tüm alt öğeleri alınamadı.  
  
 `name`  
 [in] Alınacak öğenin alt öğelerine adını belirtir. Kümesine `NULL` alınması tüm alt öğeleri için.  
  
 `compareFlags`  
 [in] Ad eşleştirme için uygulanan karşılaştırma seçeneklerini belirtir. Gelen değerleri [NameSearchOptions numaralandırması](../../debugger/debug-interface-access/namesearchoptions.md) numaralandırma tek başına veya birlikte kullanılabilir.  
  
 `ppResult`  
 [out] Döndürür bir [Idiaenumsymbols](../../debugger/debug-interface-access/idiaenumsymbols.md) alt simge listesini içeren nesne alındı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, yerel değişkenleri işlevinin bulmak gösterilmiştir `pFunc` eşleşen ada `szVarName`.  
  
```C++  
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