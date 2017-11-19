---
title: "F # hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Debugging [F#]
- F#, debugging
ms.assetid: 20bcd51c-2d06-4281-9a1e-ef2b91d1a779
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 51eaed204db7b50e75a18dfac104a00546770abc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="debugging-f"></a>F# Hata Ayıklama
F # hata ayıklama birkaç istisna dışında herhangi bir yönetilen dil hata ayıklama için benzer:  
  
-   **Otomobiller** penceresi F # değişkenleri görüntülemez.  
  
-   Düzenle ve devam et desteklenmiyor F # için. F # kodunda hata ayıklama oturumu sırasında düzenleme mümkündür, ancak kaçınılmalıdır. Kod değişiklikleri hata ayıklama oturumu sırasında uygulanmaz olduğundan, F # kodunda hata ayıklama sırasında düzenleme kaynak kodunu ayıklanacak kodu arasında uyumsuzluğa neden olur.  
  
-   Hata ayıklayıcı F # ifadeleri tanımıyor. F # hata ayıklama sırasında bir hata ayıklayıcı penceresini veya bir iletişim kutusu bir ifade girmek için C# sözdizimi ifadesine Çevir gerekir. F # ifadenin içine C# Çevir, C# kullandığını unutmayın emin olmak için eşitlik ve o F # karşılaştırma işlecini kullanan gibi tek bir = ==.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen kodda hata ayıklama](../debugger/debugging-managed-code.md)
