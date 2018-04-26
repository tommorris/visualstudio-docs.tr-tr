---
title: 'İş Akışı Tasarımcısı - nasıl yapılır: bir sıralı iş akışı kitaplığı (eski) oluşturun'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- sequential workflows, creating library
- workflows, sequential workflow library
- projects, sequential workflow library
- sequential workflow libraries
ms.assetid: 9433ccf3-1eab-4d53-90ff-2e7b2341676c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2ed341481ec3e82165a9f4cefd71eb362781d96c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-sequential-workflow-library-legacy"></a>Nasıl yapılır: bir sıralı iş akışı kitaplığı (eski) oluşturun

Windows iş akışı Tasarımcısı sağlanan eski Visual Studio 2010 tarafından kullanarak bir sıralı iş akışı kitaplık projesi oluşturmak için aşağıdaki adımları izleyin. .NET Framework sürüm 3.5 veya WinFX hedeflemek gerektiğinde eski iş akışı Tasarımcısı kullanın.

## <a name="to-create-a-sequential-workflow-library-project"></a>Sıralı iş akışı kitaplık projesi oluşturmak için

1.  Visual Studio'yu başlatın.

2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**.

     **Yeni proje** iletişim kutusu açılır.

3.  Şunlardan birini seçin **.NET Framework 3.0** seçeneği veya **.NET Framework 3.5** aşağı açılan listeden en üstündeki seçeneğinde **yeni proje** eski Tasarımcısı erişmek için penceresi.

    > [!NOTE]
    > Visual Studio 2010 varsayılan seçenektir **.NET Framework 4**. Bu seçenek, hedef .NET Framework 4 Windows Workflow Foundation (WF) uygulamaları oluşturmak için kullanılır ve eski Tasarımcısı'nı kullanmaz.

4.  İçinde **proje türleri** bölmesinde, select Visual C# veya Visual Basic (altında **diğer diller**) ve ardından **iş akışı**.

5.  İçinde **şablonları** bölmesinde, **sıralı iş akışı Kitaplığı**.

6.  İçinde **adı** kutusuna, projenizin tanınmasını kolaylaştırmak için açıklayıcı bir ad girin.

7.  İçinde **konumu** kutusunda, istediğiniz tıklayın veya projenizi kaydetmek istediğiniz dizini girin **Gözat** gitmek için.

     Proje için oluşturulan bir çözüm dizin istiyorsanız seçin **çözüm için dizin oluştur** onay kutusunu işaretleyin ve bir ad girin **çözüm adı** kutusu.

8.  **Tamam**'ı tıklatın.

## <a name="see-also"></a>Ayrıca bkz.

- [Eski İş Akışı Projeleri Oluşturma](../workflow-designer/creating-legacy-workflow-projects.md)
- [İş akışı yazma stilleri](http://msdn.microsoft.com/en-us/aacf4ec6-da05-4974-958a-974769dda739)