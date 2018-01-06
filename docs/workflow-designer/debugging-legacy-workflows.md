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
ms.workload: multiple
ms.openlocfilehash: d15236de90af6a8749482f2b159d66c28a1b8c9f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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
 [Windows Workflow Foundation için Visual Studio Hata Ayıklayıcısını Çağırma (Eski)](../workflow-designer/invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy.md)  
  
 [Windows Workflow Foundation için Visual Studio Hata Ayıklayıcısını Devre Dışı Bırakma (Eski)](../workflow-designer/disabling-the-visual-studio-debugger-for-windows-workflow-foundation-legacy.md)  
  
 [Nasıl Yapılır: ASP.NET Tabanlı İş Akışlarında Hata Ayıklama (Eski)](../workflow-designer/how-to-debug-aspnet-based-workflows-legacy.md)  
  
 [Nasıl Yapılır: İş Akışlarında Kesme Noktası Ayarlama (Eski)](../workflow-designer/how-to-set-breakpoints-in-workflows-legacy.md)  
  
 [Uzak Bir Bilgisayardan İş Akışlarında Hata Ayıklama (Eski)](../workflow-designer/debugging-workflows-from-a-remote-computer-legacy.md)  
  
 [Hata Ayıklama Adımlama Seçenekleri (Eski)](../workflow-designer/debug-stepping-options-legacy.md)  
  
 [Nasıl Yapılır: Hata Ayıklama Adımlama Seçeneğini Değiştirme (Eski)](../workflow-designer/how-to-change-the-debug-stepping-option-legacy.md)