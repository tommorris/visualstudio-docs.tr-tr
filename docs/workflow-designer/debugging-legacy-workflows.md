---
title: İş Akışı Tasarımcısı - eski iş akışları hata ayıklama
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- workflows, debugging
- debugging, workflows
- debugging workflows
ms.assetid: e6097b47-760a-4b30-a92c-ae70cdbda49f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 33a8358c5d62b938fc64d608c9b4546ab1745aaa
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="debugging-legacy-workflows"></a>Hata ayıklama eski iş akışları

Bu target.NET Framework 3.0 veya 3.5 Windows Workflow Foundation (WF) uygulamaları geliştirmek için Visual Studio'da eski Windows iş akışı Tasarımcısı kullanıyorsanız, başka bir programı gibi iş akışlarınızı kesme noktaları, ayarlayarak işlemlere ekleme ayıklanabilmesi, ve iş parçacıkları ve çağrı yığını inceleniyor. Uzaktan hata ayıklama seçeneğiniz de vardır.

> [!NOTE]
> Visual Studio birden fazla sürümünü yüklediyseniz ve makinenizde kaldırılması WF3 hata ayıklama iki aşağıdaki olasılıkları biriyle başarısız olabilir:
>
> -   Noktalarınıza isabet değil.
> -   Aşağıdaki ileti görüntülenir:
>
> **Web sunucusunda hata ayıklama başlatılamıyor. Hata ayıklayıcı düzgün şekilde yüklenmemiş.  İstenen tür kod hata ayıklaması yapılamıyor.  Yüklemek veya hata ayıklayıcı onarmak için Kurulumu çalıştırın.**
>
> Bu senaryolardan biri oluşursa, .NET Framework 3.0 veya 3.5 iş akışları hata ayıklarken, Visual Studio yüklemesinin bir onarım gerçekleştirin.

 Windows Workflow Foundation ile aşağıdaki standart Visual Studio hata ayıklama windows entegre olur:

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