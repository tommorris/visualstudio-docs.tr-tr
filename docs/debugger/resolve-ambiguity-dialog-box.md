---
title: "Belirsizliği Çöz iletişim kutusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vs.debug.Disambig
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Resolve Ambiguity dialog box
- debugger, Resolve Ambiguity dialog box
- debugging [C++], resolving ambiguity
ms.assetid: d9f47455-a116-4c84-8bad-2dfbf4d77f74
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 62b41d5345d1a17781e4e9490abedbd0c169f393
ms.sourcegitcommit: 9e6ff74da1afd8bd2f0e69387ce81f2a74619182
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/04/2018
---
# <a name="resolve-ambiguity-dialog-box"></a>Belirsizliği Çöz İletişim Kutusu
`Resolve Ambiguity` Hata ayıklayıcı görüntülemek için konum seçtiğinizde iletişim kutusu görüntülenir. Örneğin, C++ şablonları kullanıyorsanız, birden çok işlevler tek işlevi şablondan oluşturabilirsiniz. Hata ayıklayıcı şablonu kaynak konumda durdurur ve seçtiğiniz `Go To Disassembly`, hata ayıklayıcı birden çok seçenek vardır. Şablondan oluşturulan her işlevi kendi Ayrıştırılmış kod var ve hata ayıklayıcı, görüntülemek istediğiniz hangi koduyla bilmez. `Resolve Ambiguity` İletişim kutusu tüm ilgili konumlara bir listeden istediğiniz konuma seçmenize olanak sağlar.  
  
 `Choose the specific location`  
 Komutunuza karşılık gelen tüm konumları listeler.  
  
 `Address`  
 Her işlev için bellek adreslerini gösterir.  
  
 `Function`  
 Her işlevin adını gösterir.  
  
 `Module`  
 (EXE ya da DLL) modülü gösterir işlevi için nesne kodu içeren.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcıdaki ifadeler](../debugger/expressions-in-the-debugger.md)