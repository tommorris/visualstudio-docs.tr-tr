---
title: "Nasıl yapılır: çalışma sayfasındaki veritabanı kayıtları arasında kaydırma | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- databases [Office development in Visual Studio], scrolling records
- records [Office development in Visual Studio], scrolling
- data [Office development in Visual Studio], scrolling database records
- worksheets [Office development in Visual Studio], scrolling records
ms.assetid: aea4c86c-9d6d-47dd-8977-066e21945dab
caps.latest.revision: "33"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 6e3dcc6d0ed711d41fd47f043177e5d172193249
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-scroll-through-database-records-in-a-worksheet"></a>Nasıl Yapılır: Çalışma Sayfasındaki Veritabanı Kayıtları Arasında Kaydırma
  Aşağıdaki yordam Tasarımcı tüm kayıtlar arasında gezinmek son kullanıcı etkinleştirme denetimleri ile bir Microsoft Office Excel çalışma sayfasındaki veritabanı tablosundan tek bir alanı görüntülemek için nasıl kullanılacağını gösterir.  
  
 Yalnızca belge düzeyi projelerine tasarımcısını kullanabilirsiniz. Ancak, ayrıca denetimleri ekleme ve bunları verilere çalışma zamanında program aracılığıyla bağlayın. Daha fazla bilgi için bkz: [izlenecek yol: Basit Veri bağlamada VSTO eklenti proje](../vsto/walkthrough-simple-data-binding-in-vsto-add-in-project.md).  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
### <a name="to-scroll-through-database-records-in-a-worksheet"></a>Çalışma sayfasındaki veritabanı kayıtları arasında kaydırma yapma  
  
1.  Bir Excel uygulama projesini Visual Studio'da açın.  
  
2.  Açık **veri kaynakları** penceresi ve veritabanından veri kaynağı oluşturun. Daha fazla bilgi için bkz: [yeni bağlantılar eklemek](../data-tools/add-new-connections.md).  
  
3.  Göstermek istediğiniz verileri içeren tablo genişletin ve belirli sütunu seçin.  
  
4.  Denetimleri ve select listesini açmak **NamedRange**.  
  
5.  Sürükleme <xref:Microsoft.Office.Tools.Excel.NamedRange> verinin görünmesini istediğiniz yere hücre üzerine denetim.  
  
6.  Gelen **Windows Forms** sekmesinde **araç**, ekleme bir <xref:System.Windows.Forms.BindingNavigator> denetlemek için çalışma ve kullanmak istediğiniz denetimlerini ayarlayın. Daha fazla bilgi için bkz: [BindingNavigator denetimine genel bakış &#40; Windows Forms &#41; ](/dotnet/framework/winforms/controls/bindingnavigator-control-overview-windows-forms).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office Çözümlerinde Verileri Denetimlere Bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)  
  
  