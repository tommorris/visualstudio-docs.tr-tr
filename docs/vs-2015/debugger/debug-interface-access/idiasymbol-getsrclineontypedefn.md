---
title: IDiaSymbol::getSrcLineOnTypeDefn | Microsoft Docs
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
ms.assetid: ad554d18-9988-4b64-ad71-e7594c266e94
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c5972c89d545cc0b8394b425e91cecf6aa2532bd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684308"
---
# <a name="idiasymbolgetsrclineontypedefn"></a>IDiaSymbol::getSrcLineOnTypeDefn
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDiaSymbol::getSrcLineOnTypeDefn](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-getsrclineontypedefn).  
  
Belirtilen bir kullanıcı tanımlı tür tanımlandığı belirtmek kaynak dosya ve satır numarasını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT getSrcLineOnTypeDefn(  
   IDiaLineNumber **ppResult);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppResult`  
 [out] A `IDiaLineNumber` kaynak dosya ve satır numarası içeren nesne burada kullanıcı tanımlı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi halde döndürür `S_FALSE` veya bir hata kodu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)



