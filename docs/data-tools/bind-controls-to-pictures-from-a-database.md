---
title: Veritabanından resimlere denetimler bağlama
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- images [Visual Basic], displaying on Windows Forms
- data binding [Windows Forms], pictures
- images [Visual Basic], data binding
- pictures, data binding
- pictures, dragging from Data Sources window
- Data Sources Window, setting controls to display images
- PictureBox control [Windows Forms], data binding
- images [Visual Basic], dragging from Data Sources window
ms.assetid: 9748815e-3556-49e8-86b1-c6aa593c6163
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 00608bae35a9f3272e46e53d7e0205b48c0ea7d9
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="bind-controls-to-pictures-from-a-database"></a>Veritabanından resimlere denetimler bağlama

Kullanabileceğiniz **veri kaynakları** görüntüyü uygulamanızda bir denetimin bir veritabanına bağlamak için penceresi. Örneğin, bir görüntüye bağlayabileceğiniz bir <xref:System.Windows.Controls.Image> bir WPF uygulamasında veya çok kontrol bir <xref:System.Windows.Forms.PictureBox> bir Windows Forms uygulamasında denetim.

Bir veritabanında resimler genellikle bayt dizileri depolanır. Öğeler **veri kaynakları** bayt dizileri yazın kendi denetiminiz gibi depolanan penceresi kümesine **hiçbiri** varsayılan olarak, herhangi bir şeyin basit bir yürütülebilir dosya için bir bayt dizisi bayt dizileri içerebileceğinden büyük bir uygulaması. Bir bayt dizisi öğesi için veri bağlama denetimi oluşturmak için **veri kaynakları** bir resmi temsil eden penceresini oluşturmak için Denetim seçmelisiniz.

Aşağıdaki yordam varsayar **veri kaynakları** penceresi görüntüye bağlı bir öğesiyle zaten doldurulur.

## <a name="to-bind-a-picture-in-a-database-to-a-control"></a>Bir resmi bir veritabanında bir denetime bağlamak için

1.  Denetime eklemek istediğiniz tasarım yüzeyine WPF Tasarımcısı'nı veya Windows Forms Tasarımcısı'nda açık olduğundan emin olun.

2.  İçinde **veri kaynakları** penceresinde, istenen tablosunu genişletin veya sütunları veya özelliklerini görüntülemek için nesne.

3.  Sütun veya görüntü verilerinizi içeren özellik seçin ve aşağıdaki denetimleri, aşağı açılır listeden seçin:

    -   WPF Tasarımcısı açıksa seçin **görüntü**.

    -   Windows Form Tasarımcısı açıksa seçin **PictureBox**.

    -   Alternatif olarak, veri bağlamayı destekleyen ve görüntüleri gösterebilmek için farklı bir denetim seçebilirsiniz. Kullanmak istediğiniz denetim denetim listesinde, kullanılabilir durumda değilse, listeye ekleyin ve ardından seçin. Daha fazla bilgi için bkz: [veri kaynakları penceresine özel denetimler ekleme](../data-tools/add-custom-controls-to-the-data-sources-window.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da verilere WPF denetimleri bağlama](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)