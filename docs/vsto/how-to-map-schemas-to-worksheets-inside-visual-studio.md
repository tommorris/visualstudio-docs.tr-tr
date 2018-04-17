---
title: 'Nasıl yapılır: şemaları Visual Studio içindeki çalışma sayfalarıyla | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XML schemas [Office development in Visual Studio], mapping
- mappings [Office development in Visual Studio], XML schemas to Excel worksheets
- Excel [Office development in Visual Studio], XML schemas
- worksheets [Office development in Visual Studio], XML schemas
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: b2d0caadfc08d7fa1d2ea29d04e84a5d954a42fd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-map-schemas-to-worksheets-inside-visual-studio"></a>Nasıl Yapılır: Şemaları Visual Studio İçindeki Çalışma Sayfalarıyla Eşleştirme
  Çalışma sayfası Visual Studio'da açıkken bir çalışma sayfasına bir XML Şeması eşleyebilirsiniz. Çalışma kitabı Visual Studio dışında açık olduğunda kullandığınız aynı Microsoft Office Excel araçlarını kullanın. Office proje önce çalışma şema eşleme olup olmadığını veya Excel çözümünüzü oluşturduktan sonra aynı nesneleri oluşturur.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
> [!NOTE]  
>  Excel çözümleri, çok parçalı XML şemaları kullanamazsınız.  
  
### <a name="to-map-an-xml-schema-to-an-excel-worksheet-in-visual-studio"></a>Visual Studio'daki Excel çalışma sayfası XML Şeması eşlemek için  
  
1.  Excel çalışma kitabı veya şablon projesini Visual Studio içinde açın.  
  
2.  Çalışma sayfası Odağı tasarımcıya taşımak için tıklatın.  
  
3.  Şerit'te tıklatın **Geliştirici** sekmesi.  
  
    > [!NOTE]  
    >  Varsa **Geliştirici** sekmesi görünür değilse, ilk Göster gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: Şeritte Geliştirici sekmesini gösterme](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
4.  İçinde **XML** grubunda **kaynak**.  
  
     **XML kaynağı** penceresi açılır.  
  
5.  İçinde **XML kaynağı** penceresinde tıklatın **XML eşlemeleri**.  
  
     **XML eşlemeleri** iletişim kutusu açılır.  
  
6.  İçinde **XML eşlemeleri** iletişim kutusu, tıklatın **Ekle**.  
  
7.  Şema dosyasına göz atın, onu seçin ve ardından **açık**.  
  
8.  **Tamam**'ı tıklatın.  
  
     Şema temsil edilen **XML kaynağı** penceresi. Projenizdeki yazılmış bir <xref:System.Data.DataSet> şemaya göre oluşturulur ve bir <xref:System.Windows.Forms.BindingSource> oluşturulur.  
  
9. Sürükleme öğelerinden **XML kaynağı** çalışma oluşturulacak ilgili denetimlerin istediğiniz yerde penceresine.  
  
     Yinelenmeyen bir şema öğesi sürükleyin, Office projesi oluşturur. bir <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> otomatik olarak bağlı denetim <xref:System.Windows.Forms.BindingSource>.  
  
     Yinelenen bir şema öğesi sürükleyin, Office projesi oluşturur. bir <xref:Microsoft.Office.Tools.Excel.ListObject> otomatik olarak bir veri kaynağına bağlı değil denetim. Daha fazla bilgi için bkz: [XML şemaları ve verileri belge düzeyi özelleştirmelerinde](../vsto/xml-schemas-and-data-in-document-level-customizations.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: şemaları Visual Studio içindeki Word belgeleriyle eşleme](../vsto/how-to-map-schemas-to-word-documents-inside-visual-studio.md)   
 [Belge Düzeyi Özelleştirmelerde XML Şemaları ve Verileri](../vsto/xml-schemas-and-data-in-document-level-customizations.md)  
  
  