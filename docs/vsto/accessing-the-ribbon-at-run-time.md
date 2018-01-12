---
title: "Şerit çalışma zamanında erişme | Microsoft Docs"
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
- Globals class, Ribbon
- Ribbon [Office development in Visual Studio], accessing
- RibbonManager class
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 1c0f3e4d20cbb04cbcfac5123a71b3fdf03d2a26
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="accessing-the-ribbon-at-run-time"></a>Çalışma Zamanında Şerite Erişme
  Gösterme, gizleme ve Şerit değiştirmek için kod yazma ve kullanıcıların özel görev bölmesi, Eylemler bölmesinde veya Outlook form bölgesi denetimlerinde kodu çalıştırmasına etkinleştirin.  
  
 Şerit'i kullanarak erişebilirsiniz `Globals` sınıfı. Outlook projeleri için belirli bir Outlook Inspector veya Outlook Explorer penceresinde görünen Şerit erişebilir.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
## <a name="accessing-the-ribbon-by-using-the-globals-class"></a>Globals sınıfı kullanarak Şerit erişme  
 Kullanabileceğiniz `Globals` belge düzeyi projesi veya VSTO eklenti projesindeki Şerit yerinden erişmek için sınıf projesinde.  
  
 Hakkında daha fazla bilgi için `Globals` sınıfı için bkz: [Office projelerindeki nesnelere genel erişim](../vsto/global-access-to-objects-in-office-projects.md).  
  
 Aşağıdaki örnek kullanır `Globals` adlı özel bir Şerit erişmek için sınıf `Ribbon1` ve Şerit üzerindeki açılan kutusunda görüntülenen metni ayarlama `Hello World`.  
  
 [!code-vb[Trin_Outlook_FR_Access#4](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Access_O12/ThisAddIn.vb#4)]
 [!code-csharp[Trin_Outlook_FR_Access#4](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Access_O12/ThisAddIn.cs#4)]  
  
## <a name="accessing-a-collection-of-ribbons-that-appear-in-a-specific-outlook-inspector-window"></a>Belirli Outlook Inspector penceresinde görünen Şerit koleksiyonuna erişme  
 Outlook içinde görünen Şerit koleksiyonuna erişebilirsiniz *denetçiler*. Bir denetleyici kullanıcıların e-posta iletileri oluşturmak gibi belirli görevleri gerçekleştirdiğinizde, Outlook'ta açılan bir penceredir. Bir denetleyici penceresinin Şerit erişmek için arama `Ribbons` özelliği `Globals` sınıfı ve geçirin bir <xref:Microsoft.Office.Interop.Outlook.Inspector> denetçisi temsil eden nesne.  
  
 Aşağıdaki örnek, geçerli olarak odaklanmış Inspector Şerit koleksiyonunu alır. Bu örnek daha sonra adlandırılmış bir Şerit erişen `Ribbon1` ve Şerit üzerindeki açılan kutusunda görüntülenen metni ayarlar `Hello World`.  
  
 [!code-vb[Trin_Outlook_FR_Access#5](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Access_O12/ThisAddIn.vb#5)]
 [!code-csharp[Trin_Outlook_FR_Access#5](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Access_O12/ThisAddIn.cs#5)]  
  
## <a name="accessing-a-collection-of-ribbons-that-appear-for-a-specific-outlook-explorer"></a>Belirli bir Outlook Explorer'da için görünen Şerit koleksiyonuna erişme  
 Outlook içinde görünen Şerit koleksiyonuna erişebilirsiniz *Explorer*. Bir Explorer Outlook örneği için ana uygulama kullanıcı arabirimi (UI) ' dir. Bir Gezgini penceresinin Şerit erişmek için arama `Ribbons` özelliği `Globals` sınıfı ve geçirin bir <xref:Microsoft.Office.Interop.Outlook.Explorer> Explorer temsil eden nesne.  
  
 Aşağıdaki örnek, geçerli olarak odaklanmış Explorer Şerit koleksiyonunu alır. Bu örnek daha sonra adlandırılmış bir Şerit erişen `Ribbon1` ve Şerit üzerindeki açılan kutusunda görüntülenen metni ayarlar `Hello World`.  
  
 [!code-vb[Trin_Outlook_FR_Access#6](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Access_O12/ThisAddIn.vb#6)]
 [!code-csharp[Trin_Outlook_FR_Access#6](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Access_O12/ThisAddIn.cs#6)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Şerite Genel Bakış](../vsto/ribbon-overview.md)   
 [Şerit Tasarımcısı](../vsto/ribbon-designer.md)   
 [Şerit XML](../vsto/ribbon-xml.md)   
 [Şerit nesne modeline genel bakış](../vsto/ribbon-object-model-overview.md)   
 [İzlenecek yol: Şerit Tasarımcısını kullanarak özel sekme oluşturma](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [İzlenecek yol: Şerit denetimlerini çalışma zamanında güncelleme](../vsto/walkthrough-updating-the-controls-on-a-ribbon-at-run-time.md)   
 [Outlook için Şerit özelleştirme](../vsto/customizing-a-ribbon-for-outlook.md)   
 [Form Bölgesine Çalışma Zamanında Erişme](../vsto/accessing-a-form-region-at-run-time.md)  
  
  