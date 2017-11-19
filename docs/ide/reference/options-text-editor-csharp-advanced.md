---
title: "Gelişmiş Seçenekler, metin düzenleyici, C# | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Outlining
- VS.ToolsOptionsPages.Text_Editor.Visual_JSharp.Advanced
- VS.ToolsOptionsPages.Text_Editor.Visual_JSharp.Outlining
- VS.ToolsOptionsPages.Text_Editor.CSharp.Advanced
helpviewer_keywords:
- XML comments
- XML documentation, generating
- outlining options [C#]
- outlining options [J#]
- XML documentation, creating
ms.assetid: 947f9d9a-b0f3-408d-9866-d82895bcee31
caps.latest.revision: "22"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7537b4fc3fec90808c6bdc4a982fe3b7ff37a1d5
ms.sourcegitcommit: c0422a3d594ea5ae8fc03f1aee684b04f417522e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2017
---
# <a name="options-text-editor-c-advanced"></a>Seçenekler, Metin Düzenleyici, C#, Gelişmiş
Biçimlendirme Düzenleyicisi'nde, yeniden düzenleme kod ve XML belgeleri yorumları ayarları Visual C# için değiştirmek için bu iletişim kutusunu kullanın. Bu iletişim kutusunu erişmek için tıklatın **seçenekleri** üzerinde **Araçları** menüsünde genişletin **metin düzenleyici** klasörünü genişletin **C#**ve 'ıtıklatın **Gelişmiş**.  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="outlining"></a>Anahat Oluşturma  
 Anahat modu dosyalarını açtığınızda girin  
 Seçili olduğunda, otomatik olarak kod daraltılabilir bloklarını oluşturur kod dosyası özetlenmektedir. İlk kez bir dosya açıldığında, #regions blokları ve etkin olmayan kod blokları daraltın.  
  
## <a name="editor-help"></a>Düzenleyici Yardım  
 Hataları Düzenleyicisi'nde altı çizili  
 Kod derleme hataları tanımlar. Bu seçenek belirlendiğinde, dalgalı alt çizgiler özel anlamları renkte görüntülenir:  
  
-   Ayrıştırma hatalar kırmızı olur.  
  
-   Derleme hataları mavi.  
  
-   Derleme Uyarıları yeşil.  
  
-   Geçersiz [Düzenle ve devam et](../../debugger/edit-and-continue.md) düzenlemeleri mor.  
  
Hata hakkında bilgi içeren bir araç ipucunu görmek için altı çizili kod kesimi üzerine getirin.  
  
Canlı anlamsal hataları göster  
Bildirme ve bilinmeyen bir türe kullanarak veya bilinmeyen bir özelliğe başvurma belirli derleme hatasız açık derlemesini tanımlar.  
  
İmleç sembol yapılan başvurular vurgulayın  
İmleç içinde bir simge konumlandırıldığında ya da bir simge tıklattığınızda, bu simgeyi kod dosyasındaki tüm örneklerini vurgulanır.  
  
## <a name="refactoring"></a>Yeniden Düzenle  
 Yeniden düzenleme sonuçlarını doğrulayın  
 Görüntüler **doğrulama sonuçlarını** iletişim kutusu, derleme hataları içeren düzenleme kodu çalıştığınızda ya da yeniden düzenleme neden özgün bağlamasına farklı bir şey bağlamak bir kod başvurusu.  
  
 Oluşturulan derleyici başvurularıyla üyelerinde uyar  
 Oluşturulan derleyici başvurusu aynı ada sahip bir üye yeniden denediğinizde bir uyarı iletişim kutusu görüntüler.  
  
## <a name="xml-documentation-comments"></a>XML Belgeleri Yorumları  
 XML belge açıklamaları için / / / Oluştur  
 Seçili olduğunda, ekler \<Özet > başlangıç ve bitiş etiketleri XML belge açıklamaları için otomatik olarak / / / açıklama giriş yazdıktan sonra. XML belgeleri hakkında daha fazla bilgi için bkz: [XML belgeleri yorumları](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments).  
  
## <a name="implement-interface"></a>Arabirimi Uygulama  
 #Region ile oluşturulan kod surround  
 Bir #region ekler \< *arabirim adı*> arabirimi uygulama veya uygulama arabirimi açıkça kullanıldığında yöntemleri geçici üye.  
  
## <a name="organize-usings"></a>Using'leri düzenleme  
 'System' yönergeleri kullanımları sıralarken önce yerleştirin  
 Seçili olduğunda, `System` kullanma yönergeleri görünen diğer önce yönergeleri kullanarak. Daha fazla bilgi için bkz: Düzenle kullanımları [Visual C# IntelliSense](../../ide/visual-csharp-intellisense.md#automatic-code-generation).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML belgeleri yorumları](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)   
 [Dile özgü Düzenleyici seçeneklerini ayarlama](../../ide/reference/setting-language-specific-editor-options.md)   
 [Visual C# IntelliSense](../../ide/visual-csharp-intellisense.md)