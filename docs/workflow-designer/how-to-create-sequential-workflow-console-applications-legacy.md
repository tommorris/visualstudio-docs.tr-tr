---
title: "Nasıl yapılır: Sıralı iş akışı konsol uygulamaları (eski) oluşturma | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- workflows, console applications
- sequential workflows, console applications
- console applications, sequential workflow
ms.assetid: 9f7be7fa-551f-42c6-a9bb-f5ae8ab83625
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 211c750dd0baa1dad0a365310b3636c0d0922882
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-create-sequential-workflow-console-applications-legacy"></a>Nasıl yapılır: Sıralı iş akışı konsol uygulamaları (eski) oluşturma
Eski Windows iş akışı tarafından sağlanan Tasarımcısı'nı kullanarak bir sıralı iş akışı konsol uygulama projesi oluşturmak için bu adımları [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]. Eski kullanmak [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] ya da hedeflemek gerektiğinde [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] veya [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].

### <a name="to-create-a-sequential-workflow-console-application"></a>Sıralı iş akışı konsol uygulaması oluşturmak için

1.  Visual Studio'yu başlatın.

2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**.

     **Yeni proje** iletişim kutusu açılır.

3.  Şunlardan birini seçin **.NET Framework 3.0** seçeneği veya **.NET Framework 3.5** aşağı açılan listeden en üstündeki seçeneğinde **yeni proje** eski Tasarımcısı erişmek için penceresi.

    > [!NOTE]
    > Varsayılan seçenek [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] olan **.NET Framework 4**. Bu seçenek oluşturmak için kullanılan [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] hedefleyen uygulamalar [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] ve eski Tasarımcısı'nı kullanmaz.

4.  İçinde **proje türleri** bölmesi, select Visual C# projeleri veya Visual Basic projeleri (altında **diğer diller**) ve ardından **iş akışı**.

5.  İçinde **şablonları** bölmesinde, **sıralı iş akışı konsol uygulaması**.

6.  İçinde **adı** kutusuna, projenizin tanınmasını kolaylaştırmak için açıklayıcı bir ad girin.

7.  İçinde **konumu** kutusunda, istediğiniz tıklayın veya projenizi kaydetmek istediğiniz dizini girin **Gözat** gitmek için.

     Windows Form Tasarımcısı açılır ve oluşturduğunuz Proje Form1 görüntüler.

8.  **Tamam**'ı tıklatın.

     İş Akışı Tasarımcısı açılır ve oluşturduğunuz sıralı iş akışı iş akışı tasarım yüzeyini görüntüler.

9. Bir etkinlikten sürükleyin **araç** tasarım yüzeyine **etkinliğini Drop** alanı belirlenmiş.

## <a name="see-also"></a>Ayrıca bkz.

- [Eski İş Akışı Projeleri Oluşturma](../workflow-designer/creating-legacy-workflow-projects.md)
- [İş akışları geliştirme](http://msdn.microsoft.com/en-us/557bcb1f-a7ab-49f6-8df7-2706b7001301)