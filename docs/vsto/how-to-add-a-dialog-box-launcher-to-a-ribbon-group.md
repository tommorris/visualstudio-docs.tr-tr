---
title: "Nasıl yapılır: Şerit grubuna iletişim kutusu başlatıcısı ekleme | Microsoft Docs"
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
- dialog box launcher [Office development in Visual Studio]
- Ribbon [Office development in Visual Studio], dialog box launcher
ms.assetid: 5972664f-4e37-4dc6-90d0-69cedd057e60
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a8b5158bb17470ce63dbc22dc5b501a314ebda8b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-a-dialog-box-launcher-to-a-ribbon-group"></a>Nasıl Yapılır: Şerit Grubuna İletişim Kutusu Başlatıcısı Ekleme
  Herhangi bir Şerit grubuna iletişim kutusu başlatıcısı ekleyebilirsiniz. Bir iletişim kutusu başlatıcısı bir grupta görüntülenen küçük bir simgedir. Kullanıcılar ilgili iletişim kutuları veya gruba ile ilgili daha fazla seçenek sağlamak görev bölmeleri açmak için bu simgeyi tıklatın.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
### <a name="to-add-a-dialog-box-launcher-to-a-ribbon-group"></a>Şerit grubuna iletişim kutusu başlatıcısı ekleme  
  
1.  Şerit kod dosyası (.vb veya .cs dosyası) seçin **Çözüm Gezgini**.  
  
2.  Üzerinde **Görünüm** menüsünde tıklatın **Tasarımcısı**.  
  
3.  Şerit Tasarımcısı'nda tüm grubuna sağ tıklayın ve ardından **İletişimKutusuBaşlatıcı Ekle**.  
  
     Kodu ekleyin <xref:Microsoft.Office.Tools.Ribbon.RibbonGroup.DialogLauncherClick> olay grubunun yerleşik veya özel iletişim kutusunu açın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Şerite Genel Bakış](../vsto/ribbon-overview.md)   
 [Şerit çalışma zamanında erişme](../vsto/accessing-the-ribbon-at-run-time.md)   
 [Office geliştirme örnekleri ve izlenecek yollar](../vsto/office-development-samples-and-walkthroughs.md)   
 [Şerit Tasarımcısı](../vsto/ribbon-designer.md)   
 [Şerit nesne modeline genel bakış](../vsto/ribbon-object-model-overview.md)   
 [Şerit XML](../vsto/ribbon-xml.md)   
 [Nasıl yapılır: Şerit Şerit Tasarımcısından Şerit XML dışarı aktarma](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)   
 [Nasıl yapılır: Şeritteki sekmenin konumunu değiştirme](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md)   
 [Nasıl yapılır: yerleşik bir sekmeyi özelleştirme](../vsto/how-to-customize-a-built-in-tab.md)   
 [Nasıl yapılır: Backstage görünümüne denetimler ekleme](../vsto/how-to-add-controls-to-the-backstage-view.md)   
 [Outlook için Şerit özelleştirme](../vsto/customizing-a-ribbon-for-outlook.md)   
 [Nasıl yapılır: Şerit özelleştirmeye başlama](../vsto/how-to-get-started-customizing-the-ribbon.md)   
 [Nasıl yapılır: eklenti kullanıcı arayüzü hatalarını gösterme](../vsto/how-to-show-add-in-user-interface-errors.md)   
 [İzlenecek yol: Şerit Tasarımcısını kullanarak özel sekme oluşturma](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [İzlenecek yol: Şerit denetimlerini çalışma zamanında güncelleme](../vsto/walkthrough-updating-the-controls-on-a-ribbon-at-run-time.md)   
 [İzlenecek yol: Şerit XML kullanarak özel sekme oluşturma](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)  
  
  