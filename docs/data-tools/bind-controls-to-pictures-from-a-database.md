---
title: "Veritabanından resimlere denetimler bağlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: bc71529f852e87ca206509e06cb80940c11ac36d
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2017
---
# <a name="bind-controls-to-pictures-from-a-database"></a>Veritabanından resimlere denetimler bağlama
Kullanabileceğiniz **veri kaynakları** görüntüyü uygulamanızda bir denetimin bir veritabanına bağlamak için penceresi. Örneğin, bir görüntüye bağlayabileceğiniz bir <xref:System.Windows.Controls.Image> bir WPF uygulamasında veya çok kontrol bir <xref:System.Windows.Forms.PictureBox> bir Windows Forms uygulamasında denetim.  
  
Bir veritabanında resimler genellikle bayt dizileri depolanır. Öğeler **veri kaynakları** bayt dizileri yazın kendi denetiminiz gibi depolanan penceresi kümesine **hiçbiri** varsayılan olarak, herhangi bir şeyin basit bir yürütülebilir dosya için bir bayt dizisi bayt dizileri içerebileceğinden büyük bir uygulaması. Bir bayt dizisi öğesi için veri bağlama denetimi oluşturmak için **veri kaynakları** bir resmi temsil eden penceresini oluşturmak için Denetim seçmelisiniz.  
  
Aşağıdaki yordam varsayar **veri kaynakları** penceresi görüntüye bağlı bir öğesiyle zaten doldurulur. 
  
### <a name="to-bind-a-picture-in-a-database-to-a-control"></a>Bir resmi bir veritabanında bir denetime bağlamak için  
  
1.  Denetime eklemek istediğiniz tasarım yüzeyine WPF Tasarımcısı'nı veya Windows Forms Tasarımcısı'nda açık olduğundan emin olun.  
  
2.  İçinde **veri kaynakları** penceresinde, istenen tablosunu genişletin veya sütunları veya özelliklerini görüntülemek için nesne.  
  
3.  Sütun veya görüntü verilerinizi içeren özellik seçin ve aşağıdaki denetimleri, aşağı açılır listeden seçin:  
  
    -   WPF Tasarımcısı açıksa seçin **görüntü**.  
  
    -   Windows Form Tasarımcısı açıksa seçin **PictureBox**.  
  
    -   Alternatif olarak, veri bağlamayı destekleyen ve görüntüleri gösterebilmek için farklı bir denetim seçebilirsiniz. Kullanmak istediğiniz denetim denetim listesinde, kullanılabilir durumda değilse, listeye ekleyin ve ardından seçin. Daha fazla bilgi için bkz: [veri kaynakları penceresine özel denetimler ekleme](../data-tools/add-custom-controls-to-the-data-sources-window.md).  
  
## <a name="see-also"></a>Ayrıca bkz.
[Visual Studio'da verilere WPF denetimleri bağlama](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)