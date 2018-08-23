---
title: 'Nasıl yapılır: yerel çerçeveler eksik çağrı yığını penceresinde olmadığında yönetilen kodların dışına Adımlama | Microsoft Docs'
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
- JScript
- SQL
- VB
- CSharp
- C++
helpviewer_keywords:
- Call Stack window, missing native frames
- code, managed code
- native frames
- stepping, out of managed code
- managed code, stepping out of
ms.assetid: 97cdd2a8-02a9-4a06-a5b1-c92b1e431979
caps.latest.revision: 24
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 682d4f9c8973f8deee65efa0cd8c0d78061ee00a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630291"
---
# <a name="how-to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-window"></a>Nasıl Yapılır: Yerel Çerçeveler Çağrı Yığını Penceresinde Olmadığında Yönetilen Kodların Dışına Adımlama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: yerel çerçeveler eksik çağrı yığını penceresinde olmadığında yönetilen kodların dışına Adımlama](https://docs.microsoft.com/visualstudio/debugger/how-to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-window).  
  
Kodunuzu görünmez yerel çerçeveler varsa **çağrı yığını** yönetilen kodların dışına Adımlama penceresi, beklenmeyen sonuçlar verebilir. Geçici çözüm olarak, bir kesme noktası yerine kullanabileceğiniz **Step Out**.  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için seçin **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için [Visual Studio'da geliştirme ayarlarını özelleştirme](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-display"></a>Yerel çerçeveler çağrı yığını görüntüden eksik olmadığında yönetilen kodların dışına geçirmek  
  
1.  Yerel kodda, yönetilen kod çağrısından sonra bir konum kesme noktası ayarlayın.  
  
2.  Üzerinde **hata ayıklama** menüsünde seçin **devam**.  
  
     Yönetilen çağrı yapıldığında yürütme yerel kodda kesme noktasında durur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: çağrı yığını penceresini kullanma](../debugger/how-to-use-the-call-stack-window.md)





