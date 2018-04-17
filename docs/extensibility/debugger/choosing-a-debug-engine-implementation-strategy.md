---
title: Hata ayıklama Engine uygulaması stratejisini seçme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, implementation strategies
ms.assetid: 90458fdd-2d34-4f10-82dc-6d8f31b66d8b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3c3715bac00b25cd2080a1162c8e2ce8cb33e63a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="choosing-a-debug-engine-implementation-strategy"></a>Hata ayıklama Engine uygulaması stratejisini seçme
Hata ayıklama altyapısı (DE) uygulaması stratejinizi belirleme için çalışma zamanı mimarisi kullanın. Hata ayıklama altyapısı işlemdeki hata ayıklaması, olması için program işlemdeki Visual Studio oturumu hata ayıklama Yöneticisi (SDM) ya da zaman, işlem her ikisine de oluşturulabilir. Aşağıdaki yönergeler, bu üç stratejileri arasında seçim yapmanızı yardımcı olmalıdır.  
  
## <a name="guidelines"></a>Kuralları  
 İşlem dışı olması için DE mümkün olmakla birlikte hem SDM ve program için ayıklanacak genellikle Bunu yapmak için bir neden yoktur. İşlem sınırları boyunca çağrıları görece yavaş.  
  
 Hata ayıklama motorları zaten ortak dil çalışma zamanı ortamı ve Win32 yerel çalışma zamanı ortamı için sağlanan. Ya da bu ortamları DE değiştirmeniz gerekir, işlemdeki DE SDM ile oluşturmanız gerekir.  
  
 Aksi takdirde, işlem içi SDM olarak veya işlemdeki ayıklanacak programa DE oluşturma arasında tercih edebilirsiniz. Olup DE ifade değerlendiricisi sık program sembol deposu erişmesi ve hızlı erişim için bellek sembol deposu olup yüklenebilir dikkate almak önemlidir. Ayrıca aşağıdakileri dikkate alın:  
  
-   İfade değerlendirici ve sembol deposu arasındaki birçok aramaları değilse veya sembol deposu SDM bellek alanına okunabiliyorsa DE işlem içi olarak SDM oluşturun. Programınıza iliştirir bulunduğunda SDM hata ayıklama altyapısı CLSID döndürmelidir. SDM bu CLSID DE işlemdeki örneği oluşturmak için kullanır.  
  
-   Sembol deposu erişmek için program DE çağırmanız gerekir, işlemdeki DE programla oluşturun. Bu durumda, program DE örneğini oluşturur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Hata Ayıklayıcı Genişletilebilirliği](../../extensibility/debugger/visual-studio-debugger-extensibility.md)