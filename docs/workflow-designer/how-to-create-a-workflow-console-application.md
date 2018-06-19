---
title: 'İş Akışı Tasarımcısı - nasıl yapılır: bir iş akışı konsol uygulaması oluşturun'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: 51a2eea7-921c-49f1-b358-68afc27f1ee9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6461a644bdedd3d391059cd8a3a17f887e77c6b3
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31970906"
---
# <a name="how-to-create-a-workflow-console-application"></a>Nasıl yapılır: bir iş akışı konsol uygulaması oluşturun

Windows Workflow Foundation (WF), sistem veya İnsan işlemler yürütme iş akışları oluşturmanıza olanak sağlar. Windows iş akışı Tasarımcısı, bu iş akışları oluşturmak için tasarım yüzeyi sağlar. İş Akışı Tasarımcısı ' dan Visual Studio içinde iş akışları oluşturmak için kullanılabilir veya tasarımcı yeniden barındırma diğer uygulamalara tümleştirilebilir.

Bu konuda, bir konsol uygulamasında bir iş akışı oluşturmak için Visual Studio 2010'iş akışı Tasarımcısı kullanmayı açıklar.

## <a name="to-create-a-workflow-console-application"></a>Bir iş akışı konsol uygulaması oluşturmak için

1.  Visual Studio 2010'u başlatın.

2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**.

     **Yeni proje** iletişim kutusu açılır.

3.  İçinde **yüklü şablonlar** bölmesinde, **iş akışı** da **Visual C#** veya **Visual Basic** gruplandırmaları, bağlı olarak, tercih dili.

4.  Orta bölmede seçin **iş akışı konsol uygulaması**.

5.  İçinde **adı** kutusuna, projenizin tanınmasını kolaylaştırmak için açıklayıcı bir ad girin.

6.  İçinde **konumu** kutusunda, istediğiniz tıklayın veya projenizi kaydetmek istediğiniz dizini girin **Gözat** gitmek için.

7.  İçinde **çözüm** kutusunda, yeni bir çözüm için bir ad girin. Tıklatın **Tamam** uygulaması oluşturmak için.

    > [!NOTE]
    > Varolan bir çözümü bir iş akışı konsol uygulama eklemek istiyorsanız, bu çözüm Visual Studio 2010'da açın, çözüme sağ tıklayın **Çözüm Gezgini**seçip **Ekle**, ardından  **Yeni proje** açmak için **yeni proje** iletişim kutusu. Bu yordamda yukarıda açıklandığı gibi devam edin.

8.  Proje şablonu bir iş akışı tanımı XAML'de oluşturur ve kaynak kodunda konsol uygulaması tanımıdır. İş Akışı Tasarımcısı açılır ve oluşturduğunuz iş akışı için tuvale görüntüler.

9. Bir iş akışı oluşturmak için etkinlikler veya diğer iş akışı öğeleri sürükleyin **araç** iş akışınızda tasarım yüzeyine.

## <a name="see-also"></a>Ayrıca bkz.

- [İş Akışı Projesi Oluşturma](../workflow-designer/creating-a-workflow-project.md)