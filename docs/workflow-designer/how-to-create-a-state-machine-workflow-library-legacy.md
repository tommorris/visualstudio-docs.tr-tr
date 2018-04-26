---
title: 'İş Akışı Tasarımcısı - nasıl yapılır: bir Durum makinesi iş akışı kitaplığı (eski) oluşturun'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- projects, state machine workflow library
- state machine workflow libraries
- workflows, state machine workflow library
ms.assetid: 5bd68c6e-6a98-47d9-826d-9bb7a4fd72f8
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2bf8a68cb0bf86a42a31cbd0f20c156dc1dafcb1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-state-machine-workflow-library-legacy"></a>Nasıl yapılır: bir Durum makinesi iş akışı kitaplığı (eski) oluşturun

Windows iş akışı Tasarımcısı sağlanan eski Visual Studio 2010 tarafından kullanarak bir Durum makinesi iş akışı kitaplık projesi oluşturmak için aşağıdaki adımları izleyin. .NET Framework sürüm 3.5 veya WinFX hedeflemek gerektiğinde eski iş akışı Tasarımcısı kullanın.

## <a name="to-create-a-state-machine-workflow-library-project"></a>Bir Durum makinesi iş akışı kitaplık projesi oluşturmak için

1.  Visual Studio'yu başlatın.

2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**.

     **Yeni proje** iletişim kutusu açılır.

3.  Şunlardan birini seçin **.NET Framework 3.0** seçeneği veya **.NET Framework 3.5** aşağı açılan listeden en üstündeki seçeneğinde **yeni proje** eski Tasarımcısı erişmek için penceresi.

    > [!NOTE]
    > Visual Studio 2010 varsayılan seçenektir **.NET Framework 4**. Bu seçenek, hedef .NET Framework 4 Windows Workflow Foundation (WF) uygulamaları oluşturmak için kullanılır ve eski Tasarımcısı'nı kullanmaz.

4.  İçinde **proje türleri** bölmesinde, select Visual C# veya Visual Basic (altında **diğer diller**) ve ardından **iş akışı**.

5.  İçinde **şablonları** bölmesinde, **Durum makinesi iş akışı Kitaplığı**.

6.  İçinde **adı** kutusuna, projenizin tanınmasını kolaylaştırmak için açıklayıcı bir ad girin.

7.  İçinde **konumu** kutusunda, istediğiniz tıklayın veya projenizi kaydetmek istediğiniz dizini girin **Gözat** gitmek için.

     Proje için oluşturulan bir çözüm dizin istiyorsanız seçin **çözüm için dizin oluştur** onay kutusunu işaretleyin ve bir ad girin **çözüm adı** kutusu.

8.  **Tamam**'ı tıklatın.

## <a name="see-also"></a>Ayrıca bkz.

- [Eski İş Akışı Projeleri Oluşturma](../workflow-designer/creating-legacy-workflow-projects.md)
- [Durum Makinesi İş Akışları](/dotnet/framework/windows-workflow-foundation/state-machine-workflows)