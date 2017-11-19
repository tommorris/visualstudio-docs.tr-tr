---
title: "Eski iş akışları hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- workflows, debugging
- debugging, workflows
- debugging workflows
ms.assetid: e6097b47-760a-4b30-a92c-ae70cdbda49f
caps.latest.revision: "8"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2253eb414e58d5168cf6e1d2f4c22880d18d1bd6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="debugging-legacy-workflows"></a>Hata ayıklama eski iş akışları
Eski kullanıyorsanız [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] içinde [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)] oluşturmak için [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] target.NET Framework 3.0 veya 3.5, başka bir programı gibi iş akışlarınızı kesme noktalarını ayarlama işlemlere ekleme ve iş parçacıkları inceleyerek ayıklanabilmesi, uygulamalar ve çağrı yığını. Uzaktan hata ayıklama seçeneğiniz de vardır.  
  
> [!NOTE]
>  Visual Studio birden fazla sürümünü yüklediyseniz ve makinenizde kaldırılması WF3 hata ayıklama iki aşağıdaki olasılıkları biriyle başarısız olabilir:  
>   
>  -   Noktalarınıza isabet değil.  
> -   Aşağıdaki ileti görüntülenir:  
>   
>  **Web sunucusunda hata ayıklama başlatılamıyor. Hata ayıklayıcı düzgün şekilde yüklenmemiş.  İstenen tür kod hata ayıklaması yapılamıyor.  Yüklemek veya hata ayıklayıcı onarmak için Kurulumu çalıştırın.**  
>   
>  Bu senaryolardan biri oluşursa, .NET Framework 3.0 veya 3.5 iş akışları hata ayıklarken, Visual Studio yüklemesinin bir onarım gerçekleştirin.  
  
 [!INCLUDE[wf2](../workflow-designer/includes/wf2_md.md)]Aşağıdaki standart ile tümleşir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] windows hata ayıklama:  
  
-   **Kesme noktası**: beklendiği gibi çalışır, ancak aktivite işlev adı belirtin.  
  
-   **Çağrı yığını**: bir iş akışı örneği'ni imzalayan etkinlikleri bir özetini sağlamak için değiştirilmiş. Girdileri **çağrı yığını** penceresinde etkinlikleri yürütmenin derinliği ilk arama bulunur. Seçili faaliyete odak koymak için bir girişi çift tıklatabilirsiniz.  
  
-   **İş parçacığı**: örnek kimliği ayıklanacak iş akışı örneğini sağlar.  
  
 Visual Studio için Windows Workflow Foundation aşağıdaki hata ayıklama özellikleri desteklemez:  
  
-   Koşullu kesme noktaları Tasarımcı yüzeyinde.  
  
-   QuickWatch.  
  
-   Sonraki deyim ayarlayın.  
  
-   İmleci çalıştırın.  
  
-   Düzenle ve devam et.  
  
-   Tam zamanında hata ayıklama.  
  
-   Karışık mod hata ayıklaması.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Visual Studio hata ayıklayıcısı Windows Workflow Foundation (eski) için çağırma](../workflow-designer/invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy.md)  
  
 [Windows Workflow Foundation (eski) için Visual Studio hata ayıklayıcısı devre dışı bırakma](../workflow-designer/disabling-the-visual-studio-debugger-for-windows-workflow-foundation-legacy.md)  
  
 [Nasıl yapılır: hata ayıklama ASP.NET tabanlı iş akışları (eski)](../workflow-designer/how-to-debug-aspnet-based-workflows-legacy.md)  
  
 [Nasıl yapılır: kesme iş akışları (eski)](../workflow-designer/how-to-set-breakpoints-in-workflows-legacy.md)  
  
 [Hata ayıklama iş akışları uzak bir bilgisayardan (eski)](../workflow-designer/debugging-workflows-from-a-remote-computer-legacy.md)  
  
 [Hata ayıklama sürüm seçenekleri (eski)](../workflow-designer/debug-stepping-options-legacy.md)  
  
 [Nasıl yapılır: hata ayıklama atlama seçeneği (eski) değiştirme](../workflow-designer/how-to-change-the-debug-stepping-option-legacy.md)