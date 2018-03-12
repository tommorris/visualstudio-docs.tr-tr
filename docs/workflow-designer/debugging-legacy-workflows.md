---
title: "Eski iş akışları hata ayıklama | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- workflows, debugging
- debugging, workflows
- debugging workflows
ms.assetid: e6097b47-760a-4b30-a92c-ae70cdbda49f
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 4898e8f720143bd60337c9fe6bed20a7489c0d04
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="debugging-legacy-workflows"></a>Hata ayıklama eski iş akışları

Eski Windows iş akışı Tasarımcısı'nda kullanıyorsanız [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)] oluşturmak için [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] target.NET Framework 3.0 veya 3.5, başka bir programı gibi iş akışlarınızı kesme noktalarını ayarlama işlemlere ekleme ve inceleyerek ayıklanabilmesi, uygulamaları iş parçacıkları ve çağrı yığını. Uzaktan hata ayıklama seçeneğiniz de vardır.

> [!NOTE]
> Visual Studio birden fazla sürümünü yüklediyseniz ve makinenizde kaldırılması WF3 hata ayıklama iki aşağıdaki olasılıkları biriyle başarısız olabilir:
>
> -   Noktalarınıza isabet değil.
> -   Aşağıdaki ileti görüntülenir:
>
> **Web sunucusunda hata ayıklama başlatılamıyor. Hata ayıklayıcı düzgün şekilde yüklenmemiş.  İstenen tür kod hata ayıklaması yapılamıyor.  Yüklemek veya hata ayıklayıcı onarmak için Kurulumu çalıştırın.**
>
> Bu senaryolardan biri oluşursa, .NET Framework 3.0 veya 3.5 iş akışları hata ayıklarken, Visual Studio yüklemesinin bir onarım gerçekleştirin.

 [!INCLUDE[wf2](../workflow-designer/includes/wf2_md.md)] Aşağıdaki standart ile tümleşir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] windows hata ayıklama:

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