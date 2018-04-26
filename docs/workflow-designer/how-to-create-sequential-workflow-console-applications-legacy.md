---
title: 'İş Akışı Tasarımcısı - nasıl yapılır: Sıralı iş akışı konsol uygulamaları (eski) oluşturma'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- workflows, console applications
- sequential workflows, console applications
- console applications, sequential workflow
ms.assetid: 9f7be7fa-551f-42c6-a9bb-f5ae8ab83625
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fb4e048fdf8eb8fee541f84656a29427b5a07a1d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-sequential-workflow-console-applications-legacy"></a>Nasıl yapılır: Sıralı iş akışı konsol uygulamaları (eski) oluşturma

Windows iş akışı Tasarımcısı sağlanan eski Visual Studio 2010 tarafından kullanarak bir sıralı iş akışı konsol uygulama projesi oluşturmak için aşağıdaki adımları izleyin. .NET Framework sürüm 3.5 veya WinFX hedeflemek gerektiğinde eski iş akışı Tasarımcısı kullanın.

## <a name="to-create-a-sequential-workflow-console-application"></a>Sıralı iş akışı konsol uygulaması oluşturmak için

1.  Visual Studio'yu başlatın.

2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**.

     **Yeni proje** iletişim kutusu açılır.

3.  Şunlardan birini seçin **.NET Framework 3.0** seçeneği veya **.NET Framework 3.5** aşağı açılan listeden en üstündeki seçeneğinde **yeni proje** eski Tasarımcısı erişmek için penceresi.

    > [!NOTE]
    > Visual Studio 2010 varsayılan seçenektir **.NET Framework 4**. Bu seçenek, hedef .NET Framework 4 Windows Workflow Foundation (WF) uygulamaları oluşturmak için kullanılır ve eski Tasarımcısı'nı kullanmaz.

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