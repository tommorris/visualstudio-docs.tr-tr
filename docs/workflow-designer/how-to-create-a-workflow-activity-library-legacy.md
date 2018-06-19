---
title: 'İş Akışı Tasarımcısı - nasıl yapılır: bir iş akışı etkinlik kitaplığı (eski) oluşturun'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- workflows, activity library projects
- workflow activity libraries
- projects, workflow activity libraries
ms.assetid: fb5aa940-2ae8-4b52-b52c-51c20861a7b4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 432766e60ee1384db0f8cd5bad1f369e80ddd20a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31973173"
---
# <a name="how-to-create-a-workflow-activity-library-legacy"></a>Nasıl yapılır: bir iş akışı etkinlik kitaplığı (eski) oluşturun

Windows iş akışı Tasarımcısı sağlanan eski Visual Studio 2010 tarafından kullanarak bir iş akışı etkinlik kitaplığı proje oluşturmak için aşağıdaki adımları izleyin. .NET Framework sürüm 3.5 veya WinFX hedeflemek gerektiğinde eski iş akışı Tasarımcısı kullanın.

## <a name="to-create-a-workflow-activity-library-project"></a>Bir iş akışı etkinlik kitaplığı projesi oluşturmak için

1.  Visual Studio'yu başlatın.

2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**.

     **Yeni proje** iletişim kutusu açılır.

3.  Şunlardan birini seçin **.NET Framework 3.0** seçeneği veya **.NET Framework 3.5** aşağı açılan listeden en üstündeki seçeneğinde **yeni proje** eski Tasarımcısı erişmek için penceresi.

    > [!NOTE]
    > Visual Studio 2010 varsayılan seçenektir **.NET Framework 4**. Bu seçenek, hedef .NET Framework 4 Windows Workflow Foundation (WF) uygulamaları oluşturmak için kullanılır ve eski Tasarımcısı'nı kullanmaz.

4.  İçinde **proje türleri** bölmesinde, select Visual C# veya Visual Basic (altında **diğer diller**) ve ardından **iş akışı**.

5.  İçinde **şablonları** bölmesinde, **iş akışı etkinlik kütüphanesini**.

6.  İçinde **adı** kutusuna, projenizin tanınmasını kolaylaştırmak için açıklayıcı bir ad girin.

7.  İçinde **konumu** kutusunda, istediğiniz tıklayın veya projenizi kaydetmek istediğiniz dizini girin **Gözat** gitmek için.

     Proje için oluşturulan bir çözüm dizin istiyorsanız seçin **çözüm için dizin oluştur** onay kutusunu işaretleyin ve bir ad girin **çözüm adı** kutusu.

8.  **Tamam**'ı tıklatın.

## <a name="see-also"></a>Ayrıca bkz.

- [Eski İş Akışı Projeleri Oluşturma](../workflow-designer/creating-legacy-workflow-projects.md)
- [Eski Etkinlik Tasarımcısını Kullanma](../workflow-designer/using-the-legacy-activity-designer.md)
- [Eski İş Akışı Etkinlikleri ](../workflow-designer/legacy-workflow-activities.md)
- [İş akışı etkinliklerini geliştirme](http://msdn.microsoft.com/en-us/19876dfc-dfa5-4d52-b1f5-1d087474cc52)
- [Windows Workflow Foundation etkinlikleri](http://msdn.microsoft.com/en-us/192c4c1e-afb6-4f58-ab11-2b5bbbc2d2c0)