---
title: 'Nasıl yapılır: sayfa yukarı veya aşağı bellekte | Microsoft Docs'
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
- JScript
helpviewer_keywords:
- debugger, paging up or down in memory
- memory, paging up or down
- Disassembly window, viewing memory space
- Memory window, paging up or down in memory
ms.assetid: 50b30a68-66f6-43f8-a48b-59ce12c95471
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 453ae335be43015336f04e446f950580f09b6906
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-page-up-or-down-in-memory"></a>Nasıl Yapılır: Bellekte Sayfa Yukarı veya Aşağı Gitme
Bellek içeriğini görüntülerken bir **bellek** penceresi veya **ayrıştırılmış** penceresinde bellek alanı yukarı veya aşağı taşımak için dikey kaydırma çubuğu kullanabilirsiniz.  
  
### <a name="to-page-up-or-down-in-memory"></a>Yukarı veya aşağı bellek sayfası  
  
1.  Page DOWN (daha yüksek bellek adresini Git) için dikey kaydırma çubuğu kaydırma kutusunun altına Ek Yardım düğmesini tıklatın.  
  
2.  (Düşük bellek adresini Git) sayfasında için dikey kaydırma çubuğu kaydırma üstünde Ek Yardım düğmesini tıklatın.  
  
 Ayrıca dikey kaydırma çubuğu standart olmayan bir şekilde çalıştığını fark edeceksiniz. Modern bir bilgisayarın adres alanı çok büyükse ve scrollbar Flash ele geçirme ve rastgele bir konuma sürükleyerek kayıp kolaydır. Bu nedenle, Flash "springloaded" olduğundan ve her zaman scrollbar Merkezi'nde kalır. Yerel kod uygulamalarında yukarı veya aşağı sayfasında ancak hakkında serbestçe kaydırma yapamıyorsunuz.  
  
 Yönetilen uygulamalarda ayrıştırılmış bir işleve sınırlıdır ve normal şekilde kaydırın.  
  
 Daha yüksek adresleri penceresinin en altında göründüğünü fark edeceksiniz. Daha yüksek bir adresi görüntülemek için aşağı, değil kadar taşımanız gerekir.  
  
#### <a name="to-move-up-or-down-one-instruction"></a>Bir yönerge aşağı yukarı taşımak için  
  
-   Üst veya alt dikey kaydırma çubuğu oka tıklayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bellek pencereleri](../debugger/memory-windows.md)   
 [Nasıl yapılır: Ayrıştırılmış kod penceresini kullanma](../debugger/how-to-use-the-disassembly-window.md)   
 [Hata ayıklayıcıda verileri görüntüleme](../debugger/viewing-data-in-the-debugger.md)