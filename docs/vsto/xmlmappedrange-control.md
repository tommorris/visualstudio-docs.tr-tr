---
title: XmlMappedRange denetimi
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XMLMappedRange control, data binding
- XMLMappedRange control
- XMLMappedRange control, events
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e176b5cf9df3b5aaf990c7b2b5fed8a3620d7e65
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35258690"
---
# <a name="xmlmappedrange-control"></a>XmlMappedRange denetimi
  <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> Denetimidir yalnızca bir yinelenmeyen şema öğesi Microsoft Office Excel hücresine eşlendiğinde oluşturan bir aralık. Örneğin, `maxOccurs` şema öğesinin özniteliği 1 değerine eşittir. Visual Studio XML eşlenmiş aralığı oluşturduktan sonra Excel nesne modeline çapraz geçiş yapmak zorunda kalmadan doğrudan karşı programlama yapabilirsiniz. Yalnızca silebilirsiniz bir <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> öğe eşlemesi kaldırıldığında Excel'den denetim.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz: [nasıl I: kullanım XML eşleme Excel'de musunuz?](http://go.microsoft.com/fwlink/?LinkID=130288).  
  
## <a name="bind-data-to-the-control"></a>Denetimlere veri bağlama  
 Bir <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> denetim tek bir veri alanının (Basit veri bağlama) bağlamayı destekler. <xref:Microsoft.Office.Tools.Excel.ListObject> Denetimi karmaşık veri bağlamayı destekleyen ve yinelenen bir şema öğesi bir hücreye eşlendiğinde otomatik olarak oluşturulur. Daha fazla bilgi için bkz: [ListObject denetimi](../vsto/listobject-control.md).  
  
 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> Denetimi kullanarak bir veri kaynağı bağlı <xref:System.Windows.Forms.Control.DataBindings%2A> özelliği. Zaman bir <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> eklenir çalışma sayfası hücresi için Visual Studio otomatik olarak eşlenmiş hücrelerdeki verilerinden bir veri kümesi oluşturur ve bu veri kümesine denetimi bağlar. Varsayılan veri bağlama özelliğini <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> olan <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Value2%2A>.  
  
 İlişkili veri kümesindeki veriler herhangi bir mekanizma aracılığıyla güncelleştirdiyseniz <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> denetimi değişiklikleri yansıtır.  
  
## <a name="formatting"></a>Biçimlendirme  
 Aynı biçimlendirmeyi uygulayabilirsiniz bir <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> uygulayabileceğiniz denetim bir <xref:Microsoft.Office.Interop.Excel.Range>. Bu kenarlıklar, yazı tipi, numara biçimi ve stilleri içerir.  
  
## <a name="events"></a>Olaylar  
 İçin kullanılabilir olan olaylar <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> denetimi:  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.BeforeDoubleClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.BeforeRightClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.BindingContextChanged>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Change>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Selected>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Deselected>  
  
-   <xref:System.ComponentModel.Component.Disposed>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.SelectionChange>  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Genişletilmiş nesneleri kullanarak Excel'i otomatikleştirmek](../vsto/automating-excel-by-using-extended-objects.md)   
 [Nasıl yapılır: çalışma sayfalarına XMLMappedRange denetimleri ekleme](../vsto/how-to-add-xmlmappedrange-controls-to-worksheets.md)   
 [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Nasıl yapılır: şemaları Visual Studio içindeki çalışma sayfalarıyla](../vsto/how-to-map-schemas-to-worksheets-inside-visual-studio.md)   
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  