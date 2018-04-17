---
title: 'Nasıl yapılır: kısayol menülerine komut ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office menus, creating
- Office development in Visual Studio, context menus
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0d1bf0aee988e194b51220588a710a4b5b8d66ec
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-commands-to-shortcut-menus"></a>Nasıl Yapılır: Kısayol Menülerine Komut Ekleme
  Bu konu, komutları bir kısayol menüsü bir Office uygulamasında bir VSTO eklenti kullanarak nasıl ekleneceğini gösterir.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
### <a name="to-add-commands-to-shortcut-menus-in-office"></a>Kısayol menüleri Office komutları eklemek için  
  
1.  Ekle bir **Şerit XML** belge düzeyi veya VSTO eklenti proje öğesi. Daha fazla bilgi için bkz: [nasıl yapılır: Get Şerit özelleştirme başlatılan](../vsto/how-to-get-started-customizing-the-ribbon.md). İçindeki  
  
2.  **Çözüm Gezgini**seçin **ThisAddIn.cs** veya **ThisAddIn.vb**.  
  
3.  Menü çubuğunda seçin **Görünüm**, **kod**.  
  
     **ThisAddIn** sınıf dosyası Kod Düzenleyicisi'nde açar.  
  
4.  Aşağıdaki kodu ekleyin **ThisAddIn** sınıfı. Bu kod yöntemini geçersiz kılar ve Şerit XML sınıfını Office uygulamaya döndürür.  
  
     [!code-csharp[Trin_WordAddIn_Menus#1](../vsto/codesnippet/CSharp/trin_wordaddin_menus.cs/thisaddin.cs#1)]
     [!code-vb[Trin_WordAddIn_Menus#1](../vsto/codesnippet/VisualBasic/trin_wordaddin_menus.vb/thisaddin.vb#1)]  
  
5.  İçinde **Çözüm Gezgini**, Şerit XML dosyası seçin. Varsayılan olarak, Ribbon1.xml Şerit XML dosyasının adı.  
  
6.  Menü çubuğunda seçin **Görünüm**, **kod**.  
  
     Şerit xml dosyası Kod Düzenleyicisi'nde açılır.  
  
7.  Kod Düzenleyicisi'nde kısayol menüsünü ve kısayol menüsünün eklemek istediğiniz denetimi açıklayan XML ekleyin.  
  
     Aşağıdaki örnek, bir düğme, menü ve galeri denetimi bir word belgesi için kısayol menüsünü ekler. Denetim bu kısayol menüsünü ContextMenuText kimliğidir. Office 2010 kısayol denetimi tam bir listesi için kimlikleri bkz [Office 2010 Yardım dosyalarını: Office Fluent kullanıcı arabirimi denetim tanımlayıcıları](http://go.microsoft.com/fwlink/?LinkID=181052).  
  
    ```  
    <?xml version="1.0" encoding="UTF-8"?>  
    <customUI xmlns="http://schemas.microsoft.com/office/2009/07/customui">  
      <contextMenus>  
        <contextMenu idMso="ContextMenuText">  
          <button id="MyButton" label="My Button" insertBeforeMso="HyperlinkInsert" onAction="GetButtonID" />  
          <menu id="MySubMenu" label="My Submenu" >  
            <button id="MyButton2" label="Button on submenu" />  
          </menu>  
          <gallery id="galleryOne" label="My Gallery">  
            <item id="item1" imageMso="HappyFace" />  
            <item id="item2" imageMso="HappyFace" />  
            <item id="item3" imageMso="HappyFace" />  
            <item id="item4" imageMso="HappyFace" />  
          </gallery>  
        </contextMenu>  
      </contextMenus>  
    </customUI>  
    ```  
  
8.  İçinde **Çözüm Gezgini**, seçin **MyRibbon.cs** veya **MyRibbon.vb**.  
  
9. Eklemek için bir geri çağırma yöntemi `Ribbon1` ele almak istediğiniz her denetim için sınıf.  
  
     Aşağıdaki geri çağırma yöntemi işleyiciler **My Button** düğmesi. Bu kod, işaretçi geçerli konumunu etkin belge için bir dize ekler.  
  
     [!code-vb[Trin_WordAddIn_Menus#2](../vsto/codesnippet/VisualBasic/trin_wordaddin_menus.vb/ribbon1.vb#2)]
     [!code-csharp[Trin_WordAddIn_Menus#2](../vsto/codesnippet/CSharp/trin_wordaddin_menus.cs/ribbon1.cs#2)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md)   
 [İzlenecek yol: Yer işaretleri için kısayol menüleri oluşturma](../vsto/walkthrough-creating-shortcut-menus-for-bookmarks.md)   
 [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md)   
 [Office 2010 bağlam menülerini özelleştirme](http://go.microsoft.com/fwlink/?LinkId=182186)  
  
  