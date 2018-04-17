---
title: 'Nasıl yapılır: çalışma sayfalarına XMLMappedRange denetimleri ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XMLMappedRange control, adding to worksheets
- controls [Office development in Visual Studio], adding to worksheets
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: fa0e6d6249ea9b7da3fb0ab57640b61fb38e7fe5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-xmlmappedrange-controls-to-worksheets"></a>Nasıl yapılır: Çalışma Sayfalarına XMLMappedRange Denetimleri Ekleme
  Microsoft Office Excel hücresine bir XML öğesi eşlediğinizde, Visual Studio otomatik olarak ekler bir <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> çalışma denetimi.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
> [!NOTE]  
>  <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> Denetim üzerinde kullanılabilir değil **araç** veya **veri kaynakları** penceresi. Ayrıca, oluşturulamıyor <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> programlı olarak denetler.  
  
### <a name="to-add-an-xmlmappedrange-control-to-a-worksheet"></a>XMLMappedRange denetimi bir çalışma sayfasına eklemek için  
  
1.  Excel çalışma kitabı Visual Studio tasarımcısında açın.  
  
2.  Denetim eklemek istediğiniz çalışma sayfasını açın.  
  
3.  Üzerinde **Geliştirici** sekmesini tıklatın, **kaynak**.  
  
    > [!NOTE]  
    >  Varsa **Geliştirici** sekmesini Şerit'te görünür değilse, etkinleştirmeniz gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: Şeritte Geliştirici sekmesini gösterme](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
     **XML kaynağı** görev bölmesinde görünür.  
  
4.  İçinde **XML kaynağı** görev bölmesi, tıklatın **XML eşlemeleri**.  
  
5.  İçinde **XML eşlemeleri** iletişim kutusu, tıklatın **Ekle**.  
  
     **XML kaynağı** iletişim kutusu görüntülenir.  
  
6.  Bir XML şemasından seçin **XML kaynağı** iletişim kutusu ve tıklatın **açık**.  
  
     Şema eklenen **XML eşlemeleri** iletişim kutusu.  
  
7.  İçinde **XML eşlemeleri** iletişim kutusu, tıklatın **Tamam**.  
  
8.  Bir öğeyi sürükleyin **XML kaynağı** çalışma sayfası üzerinde hücre görev bölmesi.  
  
     Bir <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> oluşturulur ve projeye eklenir.  
  
    > [!NOTE]  
    >  Bir üst öğeden sürüklediğinizde **XML kaynağı** görev bölmesinde, bir <xref:Microsoft.Office.Tools.Excel.ListObject> denetimi oluşturulur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XmlMappedRange denetimi](../vsto/xmlmappedrange-control.md)   
 [Genişletilmiş nesneleri kullanarak Excel'i otomatikleştirme](../vsto/automating-excel-by-using-extended-objects.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Nasıl Yapılır: Şemaları Visual Studio İçindeki Çalışma Sayfalarıyla Eşleştirme](../vsto/how-to-map-schemas-to-worksheets-inside-visual-studio.md)  
  
  