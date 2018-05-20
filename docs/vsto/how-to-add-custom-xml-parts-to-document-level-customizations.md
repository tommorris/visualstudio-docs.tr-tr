---
title: 'Nasıl yapılır: belge düzeyi özelleştirmelerine özel XML bölümleri ekleme'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- document-level customizations [Office development in Visual Studio], custom XML parts
- Office documents [Office development in Visual Studio, custom XML parts
- Word [Office development in Visual Studio], custom XML parts
- Excel [Office development in Visual Studio], custom XML parts
- custom XML parts [Office development in Visual Studio], adding
- documents [Office development in Visual Studio], custom XML parts
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: ad9e78d6b87f85e09cbba68a4fd4297e09acf18e
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="how-to-add-custom-xml-parts-to-document-level-customizations"></a>Nasıl yapılır: belge düzeyi özelleştirmelerine özel XML bölümleri ekleme
  Belge düzeyi özelleştirmelerinde özel bir XML parçasına oluşturarak, bir Microsoft Office Excel çalışma kitabı veya Microsoft Office Word belgesi XML verilerini depolayabilir. Daha fazla bilgi için bkz: [özel XML bölümlerine genel bakış](../vsto/custom-xml-parts-overview.md).  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
> [!NOTE]  
>  Visual Studio, Microsoft Office PowerPoint için belge düzeyi projelerine sağlamaz. Bir VSTO eklenti kullanarak özel bir XML parçasına PowerPoint sunusunu ekleme hakkında daha fazla bilgi için bkz: [nasıl yapılır: VSTO eklentileri kullanarak belgelere özel XML bölümleri ekleme](../vsto/how-to-add-custom-xml-parts-to-documents-by-using-vsto-add-ins.md).  
  
### <a name="to-add-a-custom-xml-part-to-an-excel-workbook"></a>Bir Excel çalışma kitabı için özel bir XML parçasına eklemek için  
  
1.  Yeni bir ekleme <xref:Microsoft.Office.Core.CustomXMLPart> nesnesine <xref:Microsoft.Office.Core.CustomXMLParts> çalışma kitabı koleksiyonu. <xref:Microsoft.Office.Core.CustomXMLPart> Çalışma kitabında saklamak istediğiniz XML dizesini içerir.  
  
     [!code-csharp[Trin_AddCustomXmlPartExcelDocLevel#1](../vsto/codesnippet/CSharp/Trin_AddCustomXmlPartExcelDocLevel/ThisWorkbook.cs#1)]
     [!code-vb[Trin_AddCustomXmlPartExcelDocLevel#1](../vsto/codesnippet/VisualBasic/Trin_AddCustomXmlPartExcelDocLevel/ThisWorkbook.vb#1)]  
  
2.  Ekleme `AddCustomXmlPartToWorkbook` yönteme `ThisWorkbook` Excel için belge düzeyi projede sınıfı.  
  
3.  Projenizdeki başka koddan yöntemi çağırın. Örneğin, çalışma kitabını kullanıcı oturum açtığında özel XML parçaları oluşturmak için yöntemi çağırın `ThisWorkbook_Startup` olay işleyicisi.  
  
### <a name="to-add-a-custom-xml-part-to-a-word-document"></a>Özel bir XML parçasına Word belgesine eklemek için  
  
1.  Yeni bir ekleme <xref:Microsoft.Office.Core.CustomXMLPart> nesnesine <xref:Microsoft.Office.Core.CustomXMLParts> belge koleksiyonu. <xref:Microsoft.Office.Core.CustomXMLPart> Belgede depolamak istediğiniz XML dizesini içerir.  
  
     [!code-vb[Trin_AddCustomXmlPartWordDocLevel#1](../vsto/codesnippet/VisualBasic/Trin_AddCustomXmlPartWordDocLevel/ThisDocument.vb#1)]
     [!code-csharp[Trin_AddCustomXmlPartWordDocLevel#1](../vsto/codesnippet/CSharp/Trin_AddCustomXmlPartWordDocLevel/ThisDocument.cs#1)]  
  
2.  Ekleme `AddCustomXmlPartToDocument` yönteme `ThisDocument` Word için belge düzeyi projede sınıfı.  
  
3.  Projenizdeki başka koddan yöntemi çağırın. Örneğin, kullanıcı belgeyi açtığında özel XML parçaları oluşturmak için yöntemi çağırın `ThisDocument_Startup` olay işleyicisi.  
  
## <a name="robust-programming"></a>Güçlü programlama  
 Kolaylık olması için bu örnek bir yerel değişken yöntemi olarak tanımlanan bir XML dizesini kullanır. Genellikle, bir dosya veya veritabanı gibi bir dış kaynaktan XML edinmeniz gerekir.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Özel XML bölümlerine genel bakış](../vsto/custom-xml-parts-overview.md)   
 [Nasıl yapılır: VSTO eklentileri kullanarak belgelere özel XML bölümleri ekleme](../vsto/how-to-add-custom-xml-parts-to-documents-by-using-vsto-add-ins.md)  
  
  