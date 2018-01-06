---
title: "Nasıl yapılır: Şerit Şerit Tasarımcısından Şerit XML verme | Microsoft Docs"
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
- custom Ribbon, XML
- customizing the Ribbon, XML
- Ribbon [Office development in Visual Studio], XML
- Ribbon [Office development in Visual Studio], exporting
- XML [Office development in Visual Studio], Ribbon
- Ribbon Designer [Office development in Visual Studio]
- exporting Ribbon
ms.assetid: 96e0e9ed-4392-4f45-ac33-b6f7c22ea321
caps.latest.revision: "37"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: d7cbdf38b3debd7710ed036d008d52b8ef080d37
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml"></a>Nasıl Yapılır: Şerit Tasarımcısından Şerit XML'ine Dışarıya Şerit Aktarma
  **Şerit (Görsel Tasarımcı)** öğesi olası tüm Şerit özelleştirme türlerini desteklemiyor. Şerit gelişmiş yollardan özelleştirmek için Şerit Tasarımcısından Şerit XML'ine verebilir ve XML doğrudan düzenleyin.  
  
> [!NOTE]  
>  Tüm özellik değerlerini Şerit XML dosyasında görünür. Daha fazla bilgi için bkz: [Şerite Genel Bakış](../vsto/ribbon-overview.md).  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
### <a name="to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml"></a>Şerit Şerit Tasarımcısından Şerit XML'ine dışarı aktarmak için  
  
1.  Şerit kod dosyasını sağ tıklatın **Çözüm Gezgini**ve ardından **Görünüm Tasarımcısı**.  
  
2.  Şerit Tasarımcısı sağ tıklayın ve ardından **XML'e Şerit Ver**.  
  
     Visual Studio projenize Şerit XML dosyası ve bir Şerit XML kod dosyası ekler.  
  
3.  Şerit kod sınıfında ile başlayan yorumları bulun `TODO:`.  
  
4.  Bu açıklamalar, kod bloğunu kopyalayın **ThisAddIn**, **ThisWorkbook**, veya **ThisDocument** sınıfı, hangi tür çözüm geliştirdiğinize bağlı olarak.  
  
     Bu kod bulmak ve özel Şerit'i yüklemek Microsoft Office uygulamasını sağlar. Daha fazla bilgi için bkz: [Şerit XML](../vsto/ribbon-xml.md).  
  
5.  İçinde **ThisAddIn**, **ThisWorkbook**, veya **ThisDocument** sınıfı, kod bloğunun açıklamadan çıkarın.  
  
     Kodun açıklamasını kaldırın sonra aşağıdaki örneğe benzemelidir. Bu örnekte, Şerit sınıfı adlı `MyRibbon`.  
  
     [!code-csharp[Trin_Ribbon_Custom_Tab_XML#1](../vsto/codesnippet/CSharp/Trin_Ribbon_Custom_Tab_XML_O12/ThisAddIn.cs#1)]
     [!code-vb[Trin_Ribbon_Custom_Tab_XML#1](../vsto/codesnippet/VisualBasic/Trin_Ribbon_Custom_Tab_XML_O12/ThisAddIn.vb#1)]  
  
6.  Şerit XML kod dosyasına anahtarını ve Bul `Ribbon Callbacks` bölge.  
  
     Burada bir düğmeye tıklanması gibi kullanıcı eylemleri işlemek için geri çağırma yöntemleri yazma budur.  
  
7.  Şerit Tasarımcısı kodunda yazdığınız her olay işleyicisi için bir geri çağırma yöntemi oluşturun.  
  
8.  Tüm olay işleyicisi kodunuzu olay işleyicilerini geri arama yöntemleri taşıyın ve Şerit genişletilebilirlik (RibbonX) programlama modeli çalışmak için kodu değiştirin.  
  
     Geri arama yöntemleri yazma ve RibbonX programlama modelini kullanma hakkında daha fazla bilgi için bkz: [Şerit XML](../vsto/ribbon-xml.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Şerite Genel Bakış](../vsto/ribbon-overview.md)   
 [Şerit Tasarımcısı](../vsto/ribbon-designer.md)   
 [Şerit XML](../vsto/ribbon-xml.md)   
 [İzlenecek yol: Şerit Tasarımcısını kullanarak özel sekme oluşturma](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [İzlenecek Yol: Şerit XML Kullanarak Özel Sekme Oluşturma](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)  
  
  