---
title: Hata ayıklama altyapısı uygulama stratejisi seçme | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debug engines, implementation strategies
ms.assetid: 90458fdd-2d34-4f10-82dc-6d8f31b66d8b
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8a9e449fddad18c3ff0e95786ab852745407e6a1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42676210"
---
# <a name="choosing-a-debug-engine-implementation-strategy"></a>Hata Ayıklama Altyapısı Uygulama Stratejisi Seçme
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [hata ayıklama altyapısı uygulama stratejisi seçme](https://docs.microsoft.com/visualstudio/extensibility/debugger/choosing-a-debug-engine-implementation-strategy).  
  
Hata ayıklama altyapısı (DE) uygulaması stratejinizi belirleme için çalışma zamanı mimarisi kullanın. Hata ayıklama altyapısı, işlemdeki hata ayıklaması, olmasını program işlemdeki Visual Studio oturumu hata ayıklama Yöneticisi (SDM) ya da giden işlem her ikisine de oluşturulabilir. Aşağıdaki yönergeler bu üç stratejiler arasında seçmenize yardımcı olmalıdır.  
  
## <a name="guidelines"></a>Kuralları  
 İşlem dışı olması için DE mümkün olmakla birlikte SDM hem program için hata ayıklama işlemi, genellikle Bunu yapmak için bir neden yoktur. Çağrıları işlem sınırları boyunca görece yavaş yükleniyor.  
  
 Hata ayıklama altyapıları ve ortak dil çalışma zamanı ortamı Win32 yerel çalışma zamanı ortamı için zaten sağlanır. Ya da bu ortamların DE değiştirmeniz gerekir, işlemdeki DE SDM ile oluşturmanız gerekir.  
  
 Aksi takdirde, işlem içinde SDM veya işlemdeki ayıklanacak programın DE oluşturma arasında seçim yapabilirsiniz. Olup ifade değerlendiricisi ' DE, program simge deposuna sık erişmesi ve hızlı erişim için belleğe simge deposundaki olup yüklenebilir göz önünde bulundurmanız önemlidir. Ayrıca aşağıdakileri dikkate alın:  
  
-   İfade değerlendirici ve sembol deposundaki arasında birçok çağrı varsa veya sembol deposu SDM bellek alanı okunabiliyorsa DE işlem içinde SDM oluşturun. Programınızı ekler, SDM için hata ayıklama altyapısı CLSID değeri döndürmesi gerekir. SDM bu CLSID DE bir işlem örneğini oluşturmak için kullanır.  
  
-   Sembol deposuna erişmek için program DE çağırmanız gerekir, işlemdeki DE programla oluşturun. Bu durumda, program DE örneğini oluşturur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Hata Ayıklayıcı Genişletilebilirliği](../../extensibility/debugger/visual-studio-debugger-extensibility.md)

