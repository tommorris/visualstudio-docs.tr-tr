---
title: 'Nasıl yapılır: ASPX biçimlendirmesini yerelleştirme | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- localizing XML [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, localizing
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9dd127fea21a53b9a29082f536ac8c0404299c63
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-localize-aspx-markup"></a>Nasıl yapılır: ASPX İşaretlemesini Yerelleştirme
  [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] (.aspx) sayfaları genellikle sabit kodlanmış dize değerlerini kullanın. Bu dizeleri yerelleştirme için bunları yerelleştirilen kaynaklar başvuru ifadelerle değiştirin.  
  
## <a name="localizing-aspx-markup"></a>ASPX biçimlendirmesini yerelleştirme  
  
#### <a name="to-localize-aspx-markup"></a>ASPX biçimlendirmesini yerelleştirme için  
  
1.  Ayrı kaynak dosyaları ekleyin: varsayılan dil için bir tane ve her bir yerelleştirilmiş dili.  
  
     Yalnızca biçimlendirme ve kod değil yerelleştirme, bir genel kaynak dosyası proje öğesi ekleyin. Kod ve biçimlendirme yerelleştirme, bir kaynak dosyası proje öğesi ekleyin.  
  
    1.  Genel kaynaklar dosyası eklemek için **Çözüm Gezgini**, bir SharePoint proje öğesi için kısayol menüsünü açın ve ardından **Ekle**, **yeni öğe**. SharePoint altında **2010** düğümü seçin **Genel kaynaklar dosyası** şablonu.  
  
    2.  Bir kaynak dosya eklemek için **Çözüm Gezgini**, bir SharePoint proje öğesi için kısayol menüsünü açın ve ardından **Ekle**, **yeni öğe**. Ya da altında **Visual Basic** veya **Visual C#** düğümü seçin **kaynakları dosya** şablonu.  
  
    > [!NOTE]  
    >  Dağıtım türü özelliğini etkinleştirmek için bir SharePoint proje öğesi için kaynak dosyaları eklediğinizden emin olun. Bu yordamda daha sonra bu özellik gereklidir. Çözümünüzü bir SharePoint proje öğesi yoksa boş bir SharePoint proje ekleyin ve kendi varsayılan Elements.xml dosyasını kaldırın.  
  
2.  Varsayılan dil kaynak dosyasına .resx uzantılı, MyAppResources.resx gibi eklenmemiş tercih ettiğiniz bir ad verin. Her bir yerelleştirilmiş kaynak dosya için aynı temel adı kullanın, ancak kültürü eklemek [!INCLUDE[TLA2#tla_id](../sharepoint/includes/tla2sharptla-id-md.md)]. Örneğin, Almanca yerelleştirilmiş kaynak MyAppResources.de DE.resx adlandırın.  
  
3.  Değerini değiştirme **dağıtım türü** için her kaynak dosyasının özelliği **AppGlobalResource** sunucunun App_GlobalResources klasörüne dağıtmak bunları neden olacak.  
  
4.  Kod yanı sıra ASPX biçimlendirmesini yerelleştirme için kaynakların kullanıyorsanız değerini bırakın **yapı eylemi** özelliği her bir dosyanın **katıştırılmış kaynak**. Yalnızca biçimlendirmesini yerelleştirme için kaynak dosyaları kullanıyorsanız, isteğe bağlı olarak dosyalara özellik değerini değiştirebilir **içerik**. Daha fazla bilgi için bkz: [SharePoint Çözümlerini Yerelleştirme](../sharepoint/localizing-sharepoint-solutions.md).  
  
5.  Her kaynak dosyasını açın ve her dosya içine aynı dize kimlikleri kullanarak yerelleştirilmiş dizeleri ekleyin.  
  
6.  İçinde [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] ASPX sayfasının veya denetiminin, için biçimlendirme sabit kodlanmış dizeleri aşağıdaki biçimi kullanın değerleriyle değiştirin:  
  
    ```  
    <%$Resources:Resource File Name, String ID%>  
    ```  
  
     Örneğin, bir uygulama sayfasında bir etiket denetimi için metin yerelleştirme için değiştirmeniz:  
  
    ```  
    <asp:Content ID="Main" ContentPlaceHolderID="PlaceHolderMain" runat="server">  
    <asp:Label ID="lbl" runat="server" Text="Label text"></asp:Label>  
    </asp:Content>  
    ```  
  
     to  
  
    ```  
    <asp:Content ID="Main" ContentPlaceHolderID="PlaceHolderMain" runat="server">  
    <asp:Label ID="lbl" runat="server" Text="<%$Resources:MyAppResources,String1%>"></asp:Label>  
    </asp:Content>  
    ```  
  
7.  Derleme ve uygulamayı çalıştırmak için F5 tuşuna seçin.  
  
8.  SharePoint'te varsayılandan görüntüleme dilini değiştirin.  
  
     Yerelleştirilmiş dizeleri uygulamada görüntülenir. Yerelleştirilmiş kaynakları görüntülemek için SharePoint sunucusu kaynak dosyanın kültür eşleşen bir dil paketi olması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint Çözümlerini Yerelleştirme](../sharepoint/localizing-sharepoint-solutions.md)   
 [Nasıl yapılır: bir özelliği yerelleştirme](../sharepoint/how-to-localize-a-feature.md)   
 [Nasıl yapılır: kaynak dosyası ekleme](../sharepoint/how-to-add-a-resource-file.md)   
 [Nasıl yapılır: Kod Yerelleştirme](../sharepoint/how-to-localize-code.md)  
  
  