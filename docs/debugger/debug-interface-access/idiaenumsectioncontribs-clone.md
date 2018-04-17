---
title: Idiaenumsectioncontribs::Clone | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSectionContribs::Clone method
ms.assetid: 81d3f3a7-3684-4e5c-b028-29b268684a2c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2d2475a68eb85cd98856dd70f2345d99bccab078
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiaenumsectioncontribsclone"></a>IDiaEnumSectionContribs::Clone
Geçerli Numaralandırıcı aynı numaralandırma duruma içeren bir numaralandırıcı oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT Clone(   
   IDiaEnumSectionContrib** ppenum  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 ppenum  
 [out] Döndürür bir [Idiaenumsectioncontribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md) Numaralandırıcı tekrarı içeren nesne. Yinelenen Katkıları olmayan bölüm, yalnızca Numaralandırıcı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)