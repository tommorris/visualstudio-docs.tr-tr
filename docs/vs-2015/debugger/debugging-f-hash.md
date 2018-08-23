---
title: 'F # hata ayıklama | Microsoft Docs'
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
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Debugging [F#]
- F#, debugging
ms.assetid: 20bcd51c-2d06-4281-9a1e-ef2b91d1a779
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a5790b81eedb1a1bb9dc65b7ce053089c3bc1470
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633667"
---
# <a name="debugging-f"></a>F# Hata Ayıklama #
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [hata ayıklama F #](https://docs.microsoft.com/visualstudio/debugger/debugging-f-hash).  
  
F # hata ayıklama birkaç istisna dışında herhangi bir yönetilen dil hatalarının ayıklanmasına benzer:  
  
-   **Otolar** pencere, F # değişkenleri görüntülemez.  
  
-   Düzenle ve devam et desteklenmez F # için. F # kodunda hata ayıklama oturumu sırasında düzenleme mümkündür, ancak kaçınılmalıdır. Hata ayıklama sırasında F # kod düzenleme, hata ayıklama oturumu sırasında kod değişikliklerini uygulanmamış olduğundan, kaynak kodu ve hata ayıklaması yapılan kod arasında bir uyuşmazlık neden olur.  
  
-   Hata ayıklayıcı, F # ifadelerini algılamaz. F # hata ayıklama sırasında bir hata ayıklayıcı penceresi ya da iletişim kutusunda bir ifade girmek için C# sözdizimi ifadesine Çevir gerekir. Bir F # ifadesi C# içinde Çevir, C# kullandığını hatırlamak emin olmak için eşitlik ve bu F # karşılaştırma işleci kullandığından tek = ==.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen kodda hata ayıklama](../debugger/debugging-managed-code.md)



