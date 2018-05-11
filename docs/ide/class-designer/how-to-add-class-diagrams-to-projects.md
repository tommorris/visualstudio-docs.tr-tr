---
title: 'Nasıl Yapılır: Projelere Sınıf Diyagramları Ekleme (Sınıf Tasarımcısı)'
ms.date: 05/08/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- class diagrams, creating
- Class Designer [Visual Studio], opening
ms.assetid: 0eac1b54-2711-4e4b-9654-a0c429c08c8f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 94e13d4c1dbda200c2e2660e4b3b44e62ed99496
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/10/2018
---
# <a name="how-to-add-class-diagrams-to-projects"></a>Nasıl yapılır: projelere sınıf diyagramları ekleme

Tasarlama, düzenleme ve sınıfları ve diğer türleri yeniden düzenlemeniz için bir sınıf diyagramı C#, Visual Basic veya C++ projenize ekleyin. Bir proje kodda farklı kısımlarını görselleştirmek için birden çok sınıf diyagramları projeye ekleyin.

Sınıf diyagramları kod birden çok uygulama arasında paylaşmak projelerden oluşturulamıyor. UML sınıf diyagramları oluşturmak için bkz: [oluşturma UML modelleme projeleri ve diyagramları](../../modeling/create-uml-modeling-projects-and-diagrams.md).

## <a name="install-the-class-designer-component"></a>Sınıf Tasarımcısı bileşen yüklemesi

Visual Studio 2017 çalıştırıyorsanız ve yüklü henüz **Sınıf Tasarımcısı** bileşeni yüklemek için aşağıdaki adımları izleyin.

1. Açık **Visual Studio yükleyicisi** Windows Başlat menüsünden veya seçerek **Araçları** > **alma araçları ve özelliklerinin** Visual Studio menü çubuğundan.

   **Visual Studio yükleyicisi** açar.

1. Seçin **bileşenleri tek tek** sekmesini tıklatın ve sonra aşağı kaydırarak **kod Araçları** kategorisi.

1. Seçin **Sınıf Tasarımcısı** ve ardından **Değiştir**.

   ![Visual Studio yükleyicisinde Tasarımcısı bileşen sınıfı](media/class-designer-component.png)

   **Sınıf Tasarımcısı** bileşeni yükleme başlar.

## <a name="add-a-blank-class-diagram-to-a-project"></a>Bir projeye boş sınıf diyagramında ekleyin

1. İçinde **Çözüm Gezgini**, proje düğümüne sağ tıklayın ve ardından **Ekle** > **yeni öğe**. Veya basın **Ctrl**+**Shift**+**A**.

   **Yeni Öğe Ekle** iletişim kutusunu açar.

2. Genişletme **ortak öğeler** > **genel**ve ardından **sınıf diyagramı** şablonu listesinden. Visual C++ projeleri için konum **yardımcı programı** bulmak için kategori **sınıf diyagramı** şablonu.

   > [!NOTE]
   > Görmüyorsanız, **sınıf diyagramı** şablon [adımları](#install-the-class-designer-component) yüklemek için **Sınıf Tasarımcısı** Visual Studio için bileşen.

   Sınıf diyagramında Sınıf Tasarımcısı'nda açılır ve sahip bir dosya görünür bir *.cd* uzantısı'nda **Çözüm Gezgini**. Diyagramdan için şekilleri ve çizgileri sürükleyebilirsiniz **araç**.

Birden fazla sınıf diyagramı eklemek için bu yordamdaki adımları yineleyin.

## <a name="add-a-class-diagram-based-on-existing-types"></a>Varolan türlerine göre bir sınıf diyagramı ekleyin

İçinde **Çözüm Gezgini**, sınıf dosya bağlam menüsünü açın ve ardından **görünüm sınıfı diyagramı**.

-veya-

İçinde **sınıf görünümü**, ad alanı veya tür bağlam menüsünü açın ve ardından **görünüm sınıfı diyagramı**.

## <a name="to-display-the-contents-of-a-complete-project-in-a-class-diagram"></a>Sınıf diyagramında tam bir projesini içeriğini görüntülemek için

İçinde **Çözüm Gezgini** veya sınıf görünümü projeye sağ tıklayın ve seçin, **Görünüm**, ardından **görünüm sınıfı diyagramı**.

Bir otomatik olarak doldurulmuş sınıf diyagramı oluşturulur.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: Sınıf Tasarımcısı'nı kullanarak türleri oluşturma](how-to-create-types.md)
- [Nasıl yapılır: Varolan türleri görüntüleme](how-to-view-existing-types.md)
- [Tasarım ve görünüm sınıfları ve türleri](designing-and-viewing-classes-and-types.md)
- [Görünüm türleri ve ilişkileri](viewing-types-and-relationships.md)
- [Sınıf diyagramları ile çalışma](working-with-class-diagrams.md)
