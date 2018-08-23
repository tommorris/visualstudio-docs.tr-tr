---
title: Belirsizliği Çöz iletişim kutusu | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.Disambig
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Resolve Ambiguity dialog box
- debugger, Resolve Ambiguity dialog box
- debugging [C++], resolving ambiguity
ms.assetid: d9f47455-a116-4c84-8bad-2dfbf4d77f74
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 899531ab2345982d57143647710ef83435465589
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693006"
---
# <a name="resolve-ambiguity-dialog-box"></a>Belirsizliği Çöz İletişim Kutusu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [çözmek belirsizlik iletişim kutusu](https://docs.microsoft.com/visualstudio/debugger/resolve-ambiguity-dialog-box).  
  
`Resolve Ambiguity` İletişim kutusu, hata ayıklayıcı görüntüleneceği konumun seçtiğinizde görüntülenir. Örneğin, C++ şablonları kullanıyorsanız, tek işlevi şablondan birden çok işlevler oluşturabilirsiniz. Şablonu kaynak konumda hata ayıklayıcıyı durdurur ve seçtiğiniz `Go To Disassembly`, hata ayıklayıcı birden çok seçenek vardır. Şablondan oluşturulan her işlev kendi ayrıştırılmış kodu bulunur ve hata ayıklayıcı, görüntülemek istediğiniz hangi kodun bilmez. `Resolve Ambiguity` İletişim kutusunda istediğiniz konuma karşılık gelen tüm konumlara listesinden seçmenize imkan tanır.  
  
 `Choose the specific location`  
 Komutunuz için karşılık gelen tüm konumlarda listeler.  
  
 `Address`  
 Her işlev için bellek adresleri gösterilir.  
  
 `Function`  
 Her işlevin adını gösterir.  
  
 `Module`  
 Modülü (EXE veya DLL) gösterir işlev için nesne kodu içeren.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcıdaki ifadeler](../debugger/expressions-in-the-debugger.md)



