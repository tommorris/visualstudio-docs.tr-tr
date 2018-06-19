---
title: Şerit çalışma zamanında erişme
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Globals class, Ribbon
- Ribbon [Office development in Visual Studio], accessing
- RibbonManager class
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: abeffdbc61861aae3c0c9c53cb07d597abaa31c9
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34263219"
---
# <a name="access-the-ribbon-at-runtime"></a>Şerit çalışma zamanında erişme
  Gösterme, gizleme ve Şerit değiştirmek için kod yazma ve kullanıcıların özel görev bölmesi, Eylemler bölmesinde veya Outlook form bölgesi denetimlerinde kodu çalıştırmasına etkinleştirin.  

 Şerit'i kullanarak erişebilirsiniz `Globals` sınıfı. Outlook projeleri için belirli bir Outlook Inspector veya Outlook Explorer penceresinde görünen Şerit erişebilir.  

 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  

## <a name="access-the-ribbon-by-using-the-globals-class"></a>Globals sınıfı kullanarak Şerit erişim  
 Kullanabileceğiniz `Globals` belge düzeyi projesi veya VSTO eklenti projesindeki Şerit yerinden erişmek için sınıf projesinde.  

 Hakkında daha fazla bilgi için `Globals` sınıfı için bkz: [Office projelerindeki nesnelere genel erişim](../vsto/global-access-to-objects-in-office-projects.md).  

 Aşağıdaki örnek kullanır `Globals` adlı özel bir Şerit erişmek için sınıf `Ribbon1` ve Şerit üzerindeki açılan kutusunda görüntülenen metni ayarlama `Hello World`.  

 [!code-vb[Trin_Outlook_FR_Access#4](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Access_O12/ThisAddIn.vb#4)]
 [!code-csharp[Trin_Outlook_FR_Access#4](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Access_O12/ThisAddIn.cs#4)]  

## <a name="access-a-collection-of-ribbons-that-appear-in-a-specific-outlook-inspector-window"></a>Belirli bir Outlook Inspector penceresinde görünen Şerit koleksiyonuna erişme  
 Outlook içinde görünen Şerit koleksiyonuna erişebilirsiniz *denetçiler*. Bir denetleyici kullanıcıların e-posta iletileri oluşturmak gibi belirli görevleri gerçekleştirdiğinizde, Outlook'ta açılan bir penceredir. Bir denetleyici penceresinin Şerit erişmek için arama `Ribbons` özelliği `Globals` sınıfı ve geçirin bir <xref:Microsoft.Office.Interop.Outlook.Inspector> denetçisi temsil eden nesne.  

 Aşağıdaki örnek, geçerli olarak odaklanmış Inspector Şerit koleksiyonunu alır. Bu örnek daha sonra adlandırılmış bir Şerit erişen `Ribbon1` ve Şerit üzerindeki açılan kutusunda görüntülenen metni ayarlar `Hello World`.  

 [!code-vb[Trin_Outlook_FR_Access#5](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Access_O12/ThisAddIn.vb#5)]
 [!code-csharp[Trin_Outlook_FR_Access#5](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Access_O12/ThisAddIn.cs#5)]  

## <a name="access-a-collection-of-ribbons-that-appear-for-a-specific-outlook-explorer"></a>Belirli bir Outlook Explorer'da görünen Şerit koleksiyonuna erişme  
 Outlook içinde görünen Şerit koleksiyonuna erişebilirsiniz *Explorer*. Bir Explorer Outlook örneği için ana uygulama kullanıcı arabirimi (UI) ' dir. Bir Gezgini penceresinin Şerit erişmek için arama `Ribbons` özelliği `Globals` sınıfı ve geçirin bir <xref:Microsoft.Office.Interop.Outlook.Explorer> Explorer temsil eden nesne.  

 Aşağıdaki örnek, geçerli olarak odaklanmış Explorer Şerit koleksiyonunu alır. Bu örnek daha sonra adlandırılmış bir Şerit erişen `Ribbon1` ve Şerit üzerindeki açılan kutusunda görüntülenen metni ayarlar `Hello World`.  

 [!code-vb[Trin_Outlook_FR_Access#6](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Access_O12/ThisAddIn.vb#6)]
 [!code-csharp[Trin_Outlook_FR_Access#6](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Access_O12/ThisAddIn.cs#6)]  

## <a name="see-also"></a>Ayrıca bkz.  
 [Şerite Genel Bakış](../vsto/ribbon-overview.md)   
 [Şerit Tasarımcısı](../vsto/ribbon-designer.md)   
 [Şerit XML](../vsto/ribbon-xml.md)   
 [Şerit nesne modeline genel bakış](../vsto/ribbon-object-model-overview.md)   
 [İzlenecek yol: Şerit Tasarımcısını kullanarak özel sekme oluşturma](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [İzlenecek yol: çalışma zamanında Şerit denetimlerini güncelleştirme](../vsto/walkthrough-updating-the-controls-on-a-ribbon-at-run-time.md)   
 [Outlook için Şerit özelleştirme](../vsto/customizing-a-ribbon-for-outlook.md)   
 [Form bölgesine çalışma zamanında erişme](../vsto/accessing-a-form-region-at-run-time.md)  
