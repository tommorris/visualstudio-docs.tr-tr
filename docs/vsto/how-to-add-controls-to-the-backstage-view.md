---
title: 'Nasıl yapılır: Backstage görünümüne denetimler ekleme '
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- customizing the Ribbon, menus
- controls, Ribbon
- menus, customizing
- Microsoft Office Button
- custom Ribbon, menus
- Ribbon, customizing
- Office button
- Ribbon, menus
- Microsoft Office Menu
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d72cd3371a1465faa1dd505f71c5fe8c9e2e181d
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="how-to-add-controls-to-the-backstage-view"></a>Nasıl yapılır: Backstage görünümüne denetimler ekleme
  ' I tıklattığınızda, açılan menüye denetim eklemek için Şerit Tasarımcısını kullanabilirsiniz **dosya** eklediğiniz denetimleri uygulama çalıştırdığınızda sekmesini **dosya** sekmesi görünür adlı bir grup  **Eklentiler**.  
  
 Denetimleri önce veya sonra yerleşik denetimleri Visual Studio'da Şerit Tasarımcısını kullanarak konumlandırmak olamaz. Yerleşik denetim Backstage görünümünde görüntülenen bir denetimdir. Önce veya sonra yerleşik denetimleri denetimleri konumlandırmak istiyorsanız, bir Şerit XML kullanmanız gerekir. Hakkında daha fazla bilgi için **Şerit (XML)**, bkz: [Şerit XML](../vsto/ribbon-xml.md). Backstage görünümünü özelleştirme hakkında daha fazla bilgi için bkz: [giriş geliştiricilerin Office 2010 Backstage görünümüne](http://go.microsoft.com/fwlink/?LinkId=182189) ve [geliştiriciler için Office 2010 Backstage görünümünü özelleştirme](http://go.microsoft.com/fwlink/?LinkId=182188).  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
### <a name="to-add-controls-to-backstage-view"></a>Backstage görünümüne denetimler eklemek için  
  
1.  Şerit öğesi Tasarım görünümünde açın.  
  
     Nasıl ekleneceği hakkında bilgi için bir **Şerit (Görsel Tasarımcı)** öğesi projeniz için bkz: [nasıl yapılır: Şerit özelleştirmeye başlama](../vsto/how-to-get-started-customizing-the-ribbon.md).  
  
2.  Şerit Tasarımcısı'nda tıklatın **dosya** sekmesi.  
  
     Menü Tasarımcısı görünür. Bu tasarım yüzeyi herhangi bir denetim içermiyor.  
  
3.  Gelen **Office Şerit denetimleri** sekmesinde **araç**, aşağıdaki denetimleri menü tasarımcısına sürükleyin:  
  
    -   Düğme  
  
    -   CheckBox  
  
    -   Galerisi  
  
    -   Menü  
  
    -   Ayırıcı  
  
    -   Bölünmüş düğme  
  
    -   ToggleButton  
  
4.  Bunları yeni konumlara menüsünde taşımak için denetimleri sürükleyin.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Şerite Genel Bakış](../vsto/ribbon-overview.md)   
 [Şerit Tasarımcısı](../vsto/ribbon-designer.md)   
 [Şerit XML](../vsto/ribbon-xml.md)   
 [Nasıl yapılır: Şerit özelleştirmeye başlama](../vsto/how-to-get-started-customizing-the-ribbon.md)   
 [İzlenecek yol: Şerit Tasarımcısını kullanarak özel sekme oluşturma](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)  
  
  