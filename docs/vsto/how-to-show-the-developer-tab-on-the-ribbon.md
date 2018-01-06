---
title: "Nasıl yapılır: Şeritte Geliştirici sekmesini gösterme | Microsoft Docs"
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
- Ribbon [Office development in Visual Studio], tabs
- Developer tab [Office development in Visual Studio]
ms.assetid: ce7cb641-44f2-4a40-867e-a7d88f8e98a9
caps.latest.revision: "35"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 3885ce387aa27857e59fb3af74990d953c047225
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-show-the-developer-tab-on-the-ribbon"></a>Nasıl Yapılır: Şeritte Geliştirici Sekmesini Gösterme
  Erişim için **Geliştirici** sekmesinde bir Office uygulaması Şerit'te, varsayılan olarak görünmez olduğundan bu sekme göstermek için yapılandırmanız gerekir. Örneğin, eklemek istediğiniz sekmenin Göster gerekir bir <xref:Microsoft.Office.Tools.Word.GroupContentControl> Word için belge düzeyi özelleştirme için.  
  
> [!NOTE]  
>  Bu kılavuz, Office 2010 veya yalnızca daha sonraki uygulamalar için geçerlidir. Bu sekme 2007 Microsoft Office sistemi göstermek istiyorsanız, bu konunun aşağıdaki sürümü bkz [nasıl yapılır: Şeritte Geliştirici sekmesini gösterme](http://msdn.microsoft.com/library/bb608625(v=vs.90).aspx).  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
> [!NOTE]  
>  Erişim yok bir **Geliştirici** sekmesi.  
  
### <a name="to-show-the-developer-tab"></a>Geliştirici sekmesini göstermek için  
  
1.  Bu konuda tarafından desteklenen Office uygulamalarından herhangi birini başlatın. Bkz: **için geçerlidir:** bu konunun önceki kısımlarında Not.  
  
2.  Üzerinde **dosya** sekmesinde, seçin **seçenekleri** düğmesi.  
  
     Aşağıdaki şekil gösterir **dosya** sekmesi ve **seçenekleri** Office 2010 düğmesi.  
  
     ![Dosya seçme, Outlook 2010'da seçenekleri](../vsto/media/vsto-office-file-tab.png "dosya seçme, Outlook 2010'da seçenekleri")  
  
     Aşağıdaki şekil gösterir **dosya** Office 2013 sekmesindedir.  
  
     ![Outlook 2013'te Dosya sekmesini](../vsto/media/vsto-office2013-filetab.png "Outlook 2013'te dosya sekmesi")  
  
     Aşağıdaki şekil gösterir **seçenekleri** Office 2013'te düğmesi.  
  
     ![Outlook 2013 Önizleme Seçenekler düğmesini](../vsto/media/vsto-office2013-optionsbutton.png "Outlook 2013 Önizleme Seçenekleri düğmesi")  
  
3.  İçinde *ApplicationName***seçenekleri** iletişim kutusunda, seçin **Şeridi Özelleştir** düğmesi.  
  
     Aşağıdaki şekil gösterir **seçenekleri** iletişim kutusu ve **Şeridi Özelleştir** Excel 2010 düğmesini. Bu düğme konumunu, bu konunun ilk "uygulandığı" bölümünde listelenen tüm diğer uygulamalarda benzer.  
  
     ![Özelleştirme Şerit düğmesi](../vsto/media/vsto-office2010-customizeribbonbutton.png "özelleştirme Şerit düğmesi")  
  
4.  Ana sekmeler listesinde seçin **Geliştirici** onay kutusu.  
  
     Aşağıdaki şekil gösterir **Geliştirici** Word 2010 onay kutusuna ve [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)]. Bu onay kutusunu konumunu, bu konunun ilk "uygulandığı" bölümünde listelenen tüm diğer uygulamalarda benzer.  
  
     ![Word Seçenekleri iletişim Geliştirici onay kutusuna](../vsto/media/vsto-office2010-developercheckbox.png "Geliştirici iletişim kutusundaki onay kutusunu Word Seçenekleri")  
  
5.  Seçin **Tamam** kapatmak için düğmesini **seçenekleri** iletişim kutusu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office Kullanıcı Arabirimini Özelleştirme](../vsto/office-ui-customization.md)  
  
  