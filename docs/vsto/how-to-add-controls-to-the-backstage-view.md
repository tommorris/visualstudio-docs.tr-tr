---
title: 'Nasıl yapılır: Backstage görünümüne denetimler ekleme | Microsoft Docs'
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
ms.openlocfilehash: 1cdda3960363ba87e9434cd14077c7182a9f56c4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-controls-to-the-backstage-view"></a>Nasıl Yapılır: Backstage Görünümüne Denetimler Ekleme
  ' I tıklattığınızda, açılan menüye denetim eklemek için Şerit Tasarımcısını kullanabilirsiniz **dosya** eklediğiniz denetimleri uygulama çalıştırdığınızda sekmesini **dosya** sekmesi görünür adlı bir grup  **Eklentiler**.  
  
 Denetimleri önce veya sonra yerleşik denetimleri Visual Studio'da Şerit Tasarımcısını kullanarak konumlandırmak olamaz. Yerleşik denetim Backstage görünümünde görüntülenen bir denetimdir. Önce veya sonra yerleşik denetimleri denetimleri konumlandırmak istiyorsanız, bir Şerit XML kullanmanız gerekir. Hakkında daha fazla bilgi için **Şerit (XML)**, bkz: [Şerit XML](../vsto/ribbon-xml.md). Backstage görünümünü özelleştirme hakkında daha fazla bilgi için bkz: [giriş geliştiricilerin Office 2010 Backstage görünümüne](http://go.microsoft.com/fwlink/?LinkId=182189) ve [geliştiricilerin Office 2010 Backstage görünümünü özelleştirme](http://go.microsoft.com/fwlink/?LinkId=182188).  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
### <a name="to-add-controls-to-backstage-view"></a>Backstage görünümüne denetimler eklemek için  
  
1.  Şerit öğesi Tasarım görünümünde açın.  
  
     Nasıl ekleneceği hakkında bilgi için bir **Şerit (Görsel Tasarımcı)** öğesi projeniz için bkz: [nasıl yapılır: alma Şerit özelleştirme başlatılan](../vsto/how-to-get-started-customizing-the-ribbon.md).  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Şerite Genel Bakış](../vsto/ribbon-overview.md)   
 [Şerit Tasarımcısı](../vsto/ribbon-designer.md)   
 [Şerit XML](../vsto/ribbon-xml.md)   
 [Nasıl yapılır: Şerit özelleştirmeye başlama](../vsto/how-to-get-started-customizing-the-ribbon.md)   
 [İzlenecek Yol: Şerit Tasarımcısını Kullanarak Özel Sekme Oluşturma](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)  
  
  