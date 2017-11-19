---
title: "Kodlanmış UI testleriyle SharePoint 2010 uygulamalarını test etme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51b53778-469c-4cc9-854c-4e4992d6389b
caps.latest.revision: "30"
ms.author: douge
manager: douge
ms.openlocfilehash: d3ba0b9ce4366efd386d0b5c1b4d9c3f0094511b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="testing-sharepoint-2010-applications-with-coded-ui-tests"></a>Kodlanmış UI Testleriyle SharePoint 2010 Uygulamalarını Test Etme
Kodlanmış UI testleri bir SharePoint uygulama da dahil olmak üzere, kendi kullanıcı Arabirimi denetimlerini dahil olmak üzere tüm uygulama düzgün çalıştığını doğrulamak olanak tanır. Kodlanmış UI testleri, değerler ve kullanıcı arabirimi mantığı da doğrulayabilirsiniz.  
  
 **Gereksinimler**  
  
-   Visual Studio Enterprise  
  
## <a name="what-else-should-i-know-about-coded-ui-tests"></a>Kodlanmış UI testleri hakkında başka ne bilebilirim?  
 Kodlanmış UI testleri kullanmanın avantajları hakkında daha fazla bilgi için bkz: [kullanım UI Otomasyon için Test kodunuzu](../test/use-ui-automation-to-test-your-code.md) ve [sürekli teslimat ile Visual Studio 2012 - bölüm 5 otomatikleştirme sistem testleri için test etme](http://go.microsoft.com/fwlink/?LinkID=255196).  
  
 **Notlar**  
  
-   ![Prerequsite](../test/media/prereq.png "önkoşul") SharePoint uygulamaları için kodlanmış UI testleri, yalnızca SharePoint 2010 ile desteklenir.  
  
-   ![Prerequsite](../test/media/prereq.png "önkoşul") destek Visio ve PowerPoint 2010 denetimleri SharePoint uygulamanız için desteklenmiyor.  
  
## <a name="creating-a-coded-ui-test-for-your-sharepoint-app"></a>SharePoint uygulamanız için kodlanmış UI testi oluşturma  
 [Kodlanmış UI testleri oluşturma](../test/use-ui-automation-to-test-your-code.md#VerifyingCodeUsingCUITCreate) SharePoint 2010 uygulamaları için uygulamalarının diğer türleri için testler oluşturma ile aynıdır. Kaydı ve kayıttan yürütme Web düzenleme arabirimi tüm denetimler için desteklenir. Kategoriler ve web bölümleri seçme arabirimi olan tüm standart web denetimleri.  
  
 ![SharePoint web bölümleri](../test/media/cuit_sharepoint.png "CUIT_SharePoint")  
  
> [!NOTE]
>  Eylem kaydı yapıyorsanız, Eylemler kodu oluşturmadan önce doğrulayın. Bazı davranışları fare vurgulu ile ilişkili olduğundan, varsayılan olarak açıktır. Yedek gezinen kodlanmış UI testleri kaldırmak dikkatli olun. Test için kodu düzenleme veya kullanarak bunu yapabilirsiniz [kodlanmış UI Test Düzenleyicisi](../test/editing-coded-ui-tests-using-the-coded-ui-test-editor.md).  
  
## <a name="including-testing-of-office-2010-controls-within-your-sharepoint-app"></a>Office 2010 denetimlerinin, SharePoint uygulamanızın içinde test de dahil olmak üzere  
 Bazı office 2010 web bölümleri SharePoint uygulamanızda otomasyonunu sağlamak için bazı küçük kod değişiklikler yapmanız gerekir.  
  
> [!WARNING]
>  Visio ve PowerPoint 2010 denetimleri için destek desteklenmiyor.  
  
### <a name="excel-2010-cell-controls"></a>Excel 2010 hücre denetimleri  
 Excel hücre denetimleri eklemek için kodlanmış UI testin kodda bazı değişiklikler yapmanız gerekir.  
  
> [!WARNING]
>  Ok anahtar eylemi tarafından izlenen tüm Excel hücresindeki metin girerek doğru kaydetmez. Hücreleri seçmek için fareyi kullanın.  
  
 Boş bir hücre eylemleri kaydediyorsanız çift tıklayarak hücreyi tıklayarak ve kümesi metin işlemi gerçekleştirme kodu değiştirmeniz gerekir. Tüm klavye eylemi tarafından izlenen hücrenin tıklama etkinleştirir olduğundan bu gereklidir `textarea` hücre içinde. Yalnızca kaydı bir `setvalue` üzerinde boş bir hücre arama `editbox` hücre tıklattınız kadar var olmayan. Örneğin:  
  
```csharp  
Mouse.DoubliClick(uiItemCell,new Point(31,14));  
uiGridKeyboardInputEdit.Text=value;  
```  
  
 Boş olmayan hücre eylemleri kaydı sonra çünkü kaydı biraz daha karmaşık alır bir hücreye metin ekleme şu anda yeni bir \<div > denetimi hücrenin bir alt öğesi olarak eklenir. Yeni \<div > Denetim girdiğiniz metni içerir. Kaydedici eylemleri yeni kaydetmek gereken \<div > kontrol; ancak, çünkü olamaz yeni \<div > Denetim yok kadar test girildikten sonra. Bu sorunu uyum sağlamak için aşağıdaki kod değişiklikleri el ile yapmalısınız.  
  
1.  Hücre başlatma gidin ve olun `RowIndex` ve `ColumnIndex` birincil özellikleri:  
  
    ```csharp  
    this.mUIItemCell.SearchProperties[HtmlCell.PropertyNames. RowIndex] = "3";   
    this.mUIItemCell.SearchProperties[HtmlCell.PropertyNames. ColumnIndex] = "3";  
    ```  
  
2.  Bul `HtmlDiv` hücrenin alt:  
  
    ```csharp  
    private UITestControl getControlToDoubleClick(HtmlCell cell)   
    {   
         if (String.IsNullOrEmpty(cell.InnerText)) return cell;   
         HtmlDiv pane = new HtmlDiv(cell);   
         pane.FilterProperties[HtmlDiv.PropertyNames.InnerText] = cell.InnerText;   
         // Class is an important property in finding pane   
         pane.FilterProperties[HtmlDiv.PropertyNames.Class] = "cv-nwr";   
         UITestControlCollection panes = pane.FindMatchingControls();   
         return panes[0];   
    }  
  
    ```  
  
3.  Fare çift için eylem kodu ekleyin `HtmlDiv`:  
  
    ```csharp  
    Mouse.DoubleClick(uIItemPane, new Point(31, 14)); )  
    ```  
  
4.  Metni ayarlamak için kod ekleme `TextArea`:  
  
    ```csharp  
    uIGridKeyboardInputEdit.Text = value; }  
    ```  
  
## <a name="enabling-coded-ui-testing-of-silverlight-web-parts-in-your-sharepoint-2010-app"></a>SharePoint 2010 uygulamanızda Silverlight web bölümlerinin UI testi kodlanmış etkinleştirme  
 Silverlight sınama Visual Studio 2012 ve sonraki sürümlerde desteklenmez. Ancak, Silverlight web bölümleri SharePoint 2010 uygulamanızı test etmek isterseniz ayrı Silverlight eklentisi Visual Studio Galerisi'nden yükleyebilirsiniz.  
  
#### <a name="setting-up-your-machine"></a>Makinenizin ayarlama  
  
1.  Veya üstü yüklü Visual Studio 2012.1 sahip olduğunuzdan emin olun.  
  
2.  Yükleme [Silverlight için Microsoft Visual Studio kullanıcı Arabirimi testi eklentisi](http://visualstudiogallery.msdn.microsoft.com/28312a61-9451-451a-990c-c9929b751eb4).  
  
3.  Yükleme [Fiddler](http://www.fiddler2.com/fiddler2/). Bu yakalayan ve HTTP trafiği günlüklerini sadece bir araçtır.  
  
4.  Karşıdan [fiddlerXap proje](http://blogs.msdn.com/cfs-file.ashx/__key/communityserver-components-postattachments/00-10-36-48-70/FiddlerXapProxy.zip). Bunu sıkıştırmasını açın, onu oluşturmak ve yardımcı Fiddler Aracı'nı kullandığınızda Silverlight web bölümleri test etmek için gereken dll dosyasını yüklemek için "CopySLHelper.bat" komut dosyasını çalıştırın.  
  
 SharePoint 2010 uygulamanızı Silverlight web bölümleri ile test başlatmak için makinenize ayarladıktan sonra aşağıdaki adımları izleyin:  
  
#### <a name="testing-silverlight-web-parts"></a>Silverlight web bölümleri test etme  
  
1.  Fiddler'ı başlatın.  
  
2.  Tarayıcı önbelleğini temizleyebilirsiniz. Silverlight UI Otomasyon yardımcı DLL içerir, XAP dosyası genellikle önbelleğe gerekli olmasıdır. Biz tarayıcı önbelleğini temizlemek için değiştirilen XAP dosyasını çekilir emin olmak sahip.  
  
3.  Web sayfasını açın.  
  
4.  Kaydedici başlatın ve bir normal web uygulamanızı test etmek gibi kodu oluşturur.  
  
5.  Oluşturulan kod Microsoft.VisualStudio.TestTools.UITest.Extension.Silverlight.dll başvuruyor onaylamalıdır.  
  
     Daha fazla bilgi için bkz: [UI Visual Studio 2012 SharePoint 2010 test etme](http://blogs.msdn.com/b/visualstudioalm/archive/2012/11/01/ui-testing-sharepoint-2010-with-visual-studio-2012.aspx)  
  
## <a name="external-resources"></a>Dış kaynaklar  
  
### <a name="blogs"></a>Bloglar  
 [Visual Studio 2012 ile SharePoint 2010 test kullanıcı Arabirimi](http://blogs.msdn.com/b/visualstudioalm/archive/2012/11/01/ui-testing-sharepoint-2010-with-visual-studio-2012.aspx)  
  
 [Silverlight denetimleri kodlanmış UI testi için arama mantığı anlama](http://blogs.msdn.com/b/tapas_sahoos_blog/archive/2010/11/16/understanding-the-search-logic-for-silverlight-controls-in-coded-ui-test.aspx)  
  
 [Silverlight denetiminin özelliği getirme](http://blogs.msdn.com/b/tapas_sahoos_blog/archive/2010/11/16/fetching-property-of-a-silverlight-control.aspx)  
  
 [Kodlanmış UI testi için içerik dizini](http://blogs.msdn.com/b/mathew_aniyan/archive/2010/02/11/content-index-for-coded-ui-test.aspx)  
  
### <a name="guidance"></a>Kılavuz  
 [Visual Studio 2012 - bölüm 5 ile sürekli teslimat için otomatik otomatikleştirme sistem testleri test etme](http://go.microsoft.com/fwlink/?LinkID=255196)  
  
### <a name="forum"></a>Forum  
 [Visual Studio ALM + Team Foundation Server blogu](http://go.microsoft.com/fwlink/?LinkID=254496)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kodunuzu test etmek için UI otomasyonunu kullanma](../test/use-ui-automation-to-test-your-code.md)   
 [Web performans ve SharePoint 2010 ve 2013 uygulamalarında sınama yük](/devops-test-docs/test/web-performance-and-load-testing-sharepoint-2010-and-2013-applications)   
 [SharePoint çözümleri oluşturma](/office-dev/office-dev/create-sharepoint-solutions)   
 [Doğrulama ve SharePoint kodda hata ayıklama](/office-dev/office-dev/verifying-and-debugging-sharepoint-code)   
 [Derleme ve SharePoint çözümlerini hata ayıklama](/office-dev/office-dev/building-and-debugging-sharepoint-solutions)   
 [SharePoint uygulamalarını performans profili oluşturma](/office-dev/office-dev/profiling-the-performance-of-sharepoint-applications)
