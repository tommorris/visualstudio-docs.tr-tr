---
title: 'F # hata ayıklama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Debugging [F#]
- F#, debugging
ms.assetid: 20bcd51c-2d06-4281-9a1e-ef2b91d1a779
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a3a2b2651a8fc7f33ec30edc5d080d6d7e66c17e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="debugging-f"></a>F# Hata Ayıklama
F # hata ayıklama birkaç istisna dışında herhangi bir yönetilen dil hata ayıklama için benzer:  
  
-   **Otomobiller** penceresi F # değişkenleri görüntülemez.  
  
-   Düzenle ve devam et desteklenmiyor F # için. F # kodunda hata ayıklama oturumu sırasında düzenleme mümkündür, ancak kaçınılmalıdır. Kod değişiklikleri hata ayıklama oturumu sırasında uygulanmaz olduğundan, F # kodunda hata ayıklama sırasında düzenleme kaynak kodunu ayıklanacak kodu arasında uyumsuzluğa neden olur.  
  
-   Hata ayıklayıcı F # ifadeleri tanımıyor. F # hata ayıklama sırasında bir hata ayıklayıcı penceresini veya bir iletişim kutusu bir ifade girmek için C# sözdizimi ifadesine Çevir gerekir. F # ifadenin içine C# Çevir, C# kullandığını unutmayın emin olmak için eşitlik ve o F # karşılaştırma işlecini kullanan gibi tek bir = ==.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen kodda hata ayıklama](../debugger/debugging-managed-code.md)
