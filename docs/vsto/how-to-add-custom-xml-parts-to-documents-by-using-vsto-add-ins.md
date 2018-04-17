---
title: 'Nasıl yapılır: VSTO eklentilerini kullanarak belgelere özel XML bölümleri ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- add-ins [Office development in Visual Studio], custom XML parts
- Office documents [Office development in Visual Studio, custom XML parts
- Word [Office development in Visual Studio], custom XML parts
- PowerPoint [Office development in Visual Studio], custom XML parts
- Excel [Office development in Visual Studio], custom XML parts
- custom XML parts [Office development in Visual Studio], adding
- documents [Office development in Visual Studio], custom XML parts
- application-level add-ins [Office development in Visual Studio], custom XML parts
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d06918a9b1d2bf1bec3f39d3e58352665d07e5c8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-custom-xml-parts-to-documents-by-using-vsto-add-ins"></a>Nasıl Yapılır: VSTO Eklentilerini Kullanarak Belgelere Özel XML Bölümleri Ekleme
  Bir VSTO eklenti özel bir XML parçasına oluşturarak belgelerin aşağıdaki türlerden XML veri depolayabilirsiniz:  
  
-   Microsoft Office Excel çalışma kitabı.  
  
-   Microsoft Office Word belgesi.  
  
-   Microsoft Office PowerPoint sunusu.  
  
 Daha fazla bilgi için bkz: [özel XML bölümlerine genel bakış](../vsto/custom-xml-parts-overview.md).  
  
 **Uygulandığı öğe:** Bu konu başlığı altındaki bilgiler Excel, PowerPoint ve Word için uygulama düzeyi projelerine yöneliktir. Daha fazla bilgi için bkz: [Office uygulaması ve proje türüne göre kullanılabilen özellikler](../vsto/features-available-by-office-application-and-project-type.md).  
  
### <a name="to-add-a-custom-xml-part-to-an-excel-workbook"></a>Bir Excel çalışma kitabı için özel bir XML parçasına eklemek için  
  
1.  Yeni bir ekleme <xref:Microsoft.Office.Core.CustomXMLPart> nesnesine <xref:Microsoft.Office.Interop.Excel._Workbook.CustomXMLParts%2A> çalışma kitabı koleksiyonu. <xref:Microsoft.Office.Core.CustomXMLPart> Çalışma kitabında saklamak istediğiniz XML dizesini içerir.  
  
     Aşağıdaki kod örneğinde, belirli bir çalışma kitabına özel bir XML parçasına ekler.  
  
     [!code-vb[Trin_AddCustomXmlPartExcelAppLevel#1](../vsto/codesnippet/VisualBasic/trin_addcustomxmlpartexcelapplevel/ThisAddIn.vb#1)]
     [!code-csharp[Trin_AddCustomXmlPartExcelAppLevel#1](../vsto/codesnippet/CSharp/Trin_AddCustomXmlPartExcelAppLevel/ThisAddIn.cs#1)]  
  
2.  Ekle `AddCustomXmlPartToWorkbook` yönteme `ThisAddIn` Excel için VSTO eklenti projesindeki sınıfı.  
  
3.  Projenizdeki başka koddan yöntemi çağırın. Örneğin, bir çalışma kitabı kullanıcı oturum açtığında özel XML parçaları oluşturmak için yöntemi için bir olay işleyicisi çağırmanıza <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.WorkbookOpen> olay.  
  
### <a name="to-add-a-custom-xml-part-to-a-word-document"></a>Özel bir XML parçasına Word belgesine eklemek için  
  
1.  Yeni bir ekleme <xref:Microsoft.Office.Core.CustomXMLPart> nesnesine <xref:Microsoft.Office.Interop.Word._Document.CustomXMLParts%2A> belge koleksiyonu. <xref:Microsoft.Office.Core.CustomXMLPart> Belgede depolamak istediğiniz XML dizesini içerir.  
  
     Aşağıdaki kod örneğinde, belirli bir belgeye özel bir XML parçasına ekler.  
  
     [!code-vb[Trin_AddCustomXmlPartWordAppLevel#1](../vsto/codesnippet/VisualBasic/Trin_AddCustomXmlPartWordAppLevel/ThisAddIn.vb#1)]
     [!code-csharp[Trin_AddCustomXmlPartWordAppLevel#1](../vsto/codesnippet/CSharp/Trin_AddCustomXmlPartWordAppLevel/ThisAddIn.cs#1)]  
  
2.  Ekle `AddCustomXmlPartToDocument` yönteme `ThisAddIn` Word için VSTO eklenti projesindeki sınıfı.  
  
3.  Projenizdeki başka koddan yöntemi çağırın. Örneğin, kullanıcı bir belgeyi açtığında özel XML parçaları oluşturmak için yöntemi için bir olay işleyicisi çağırmanıza <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentOpen> olay.  
  
### <a name="to-add-a-custom-xml-part-to-a-powerpoint-presentation"></a>Özel bir XML parçasına PowerPoint sunusunu eklemek için  
  
1.  Yeni bir ekleme <xref:Microsoft.Office.Core.CustomXMLPart> nesnesine <xref:Microsoft.Office.Interop.PowerPoint._Presentation.CustomXMLParts%2A> sunu koleksiyonu. <xref:Microsoft.Office.Core.CustomXMLPart> Sunuya depolamak istediğiniz XML dizesini içerir.  
  
     Aşağıdaki kod örneğinde, belirli bir sunuya özel bir XML parçasına ekler.  
  
     [!code-csharp[Trin_AddCustomXmlPartPowerPointAppLevel#1](../vsto/codesnippet/CSharp/Trin_AddCustomXmlPartPowerPointAppLevel/ThisAddIn.cs#1)]
     [!code-vb[Trin_AddCustomXmlPartPowerPointAppLevel#1](../vsto/codesnippet/VisualBasic/Trin_AddCustomXmlPartPowerPointAppLevel/ThisAddIn.vb#1)]  
  
2.  Ekle `AddCustomXmlPartToPresentation` yönteme `ThisAddIn` PowerPoint için VSTO eklenti projesindeki sınıfı.  
  
3.  Projenizdeki başka koddan yöntemi çağırın. Örneğin, bir sunu kullanıcı oturum açtığında özel XML parçaları oluşturmak için yöntemi için bir olay işleyicisi çağırmanıza <xref:Microsoft.Office.Interop.PowerPoint.EApplication_Event.AfterPresentationOpen> olay.  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Kolaylık olması için bu örnek bir yerel değişken yöntemi olarak tanımlanan bir XML dizesini kullanır. Genellikle, bir dosya veya veritabanı gibi bir dış kaynaktan XML edinmeniz gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel XML bölümlerine genel bakış](../vsto/custom-xml-parts-overview.md)   
 [Nasıl Yapılır: Belge Düzeyi Özelleştirmelerine Özel XML Bölümleri Ekleme](../vsto/how-to-add-custom-xml-parts-to-document-level-customizations.md)  
  
  