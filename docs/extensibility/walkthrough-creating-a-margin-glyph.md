---
title: "İzlenecek yol: bir kenar karakter oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], new - margin glyph
ms.assetid: 814185db-24f9-417f-b3b1-7c5aabb42b45
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: fc813ed3c29c2fe0a4cac1c348ffed18ae8fd2d2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-a-margin-glyph"></a>İzlenecek yol: bir kenar karakter oluşturma
Özel düzenleyici uzantıları kullanarak Düzenleyicisi kenar boşluklarını görünümünü özelleştirebilirsiniz. Her bir kod açıklaması "todo" word görüntülendiğinde bu kılavuzda bir özel karakter göstergesi kenar boşluğu koyar.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-mef-project"></a>Bir MEF projesi oluşturma  
  
1.  Bir C# VSIX projesi oluşturun. (İçinde **yeni proje** iletişim kutusunda **Visual C# / genişletilebilirlik**, ardından **VSIX proje**.) Çözüm adı `TodoGlyphTest`.  
  
2.  Bir düzenleyici sınıflandırıcı proje öğesi ekleyin. Daha fazla bilgi için bkz: [bir düzenleyici öğesi şablonuyla bir uzantısı oluşturma](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
3.  Varolan sınıf dosyaları silin.  
  
## <a name="defining-the-glyph"></a>Simge tanımlama  
 Bir karakter uygulayarak tanımlama <xref:Microsoft.VisualStudio.Text.Editor.IGlyphFactory> arabirimi.  
  
#### <a name="to-define-the-glyph"></a>Karakter tanımlamak için  
  
1.  Bir sınıf dosyası ekleyin ve adını `TodoGlyphFactory`.  
  
2.  Aşağıdakileri ekleyin bildirimlerini kullanarak.  
  
     [!code-csharp[VSSDKTodoGlyphTest#1](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_1.cs)]
     [!code-vb[VSSDKTodoGlyphTest#1](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_1.vb)]  
  
3.  Adlı bir sınıf ekleyin `TodoGlyphFactory` uygulayan <xref:Microsoft.VisualStudio.Text.Editor.IGlyphFactory>.  
  
     [!code-csharp[VSSDKTodoGlyphTest#2](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_2.cs)]
     [!code-vb[VSSDKTodoGlyphTest#2](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_2.vb)]  
  
4.  Karakter boyutları tanımlayan özel bir alan ekleyin.  
  
     [!code-csharp[VSSDKTodoGlyphTest#3](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_3.cs)]
     [!code-vb[VSSDKTodoGlyphTest#3](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_3.vb)]  
  
5.  Uygulama `GenerateGlyph` karakter kullanıcı arabirimi (UI) öğesi tanımlayarak. `TodoTag`Bu kılavuzda daha sonra tanımlanır.  
  
     [!code-csharp[VSSDKTodoGlyphTest#4](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_4.cs)]
     [!code-vb[VSSDKTodoGlyphTest#4](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_4.vb)]  
  
6.  Adlı bir sınıf ekleyin `TodoGlyphFactoryProvider` uygulayan <xref:Microsoft.VisualStudio.Text.Editor.IGlyphFactoryProvider>. Bu sınıfla verme bir <xref:Microsoft.VisualStudio.Utilities.NameAttribute> "TodoGlyph", bir <xref:Microsoft.VisualStudio.Utilities.OrderAttribute> sonra VsTextMarker, bir <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "kod" ve <xref:Microsoft.VisualStudio.Text.Tagging.TagTypeAttribute> TodoTag.  
  
     [!code-csharp[VSSDKTodoGlyphTest#5](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_5.cs)]
     [!code-vb[VSSDKTodoGlyphTest#5](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_5.vb)]  
  
7.  Uygulama <xref:Microsoft.VisualStudio.Text.Editor.IGlyphFactoryProvider.GetGlyphFactory%2A> örneği tarafından yöntemi `TodoGlyphFactory`.  
  
     [!code-csharp[VSSDKTodoGlyphTest#6](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_6.cs)]
     [!code-vb[VSSDKTodoGlyphTest#6](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_6.vb)]  
  
## <a name="defining-a-todo-tag-and-tagger"></a>Yapılacaklar etiketi ve etiketleme tanımlama  
 Bir etiket türü ve etiketleme oluşturarak ve etiketleme sağlayıcısını kullanarak dışa aktarma önceki adımlarda tanımlanan kullanıcı Arabirimi öğesi ve gösterge boşluğu arasındaki ilişkiyi tanımlayabilirsiniz.  
  
#### <a name="to-define-a-todo-tag-and-tagger"></a>Yapılacaklar etiketi ve etiketleme tanımlamak için  
  
1.  Yeni bir sınıf dosyası projeye ekleyin ve adını `TodoTagger`.  
  
2.  Aşağıdaki içeri aktarmaları ekleyin.  
  
     [!code-csharp[VSSDKTodoGlyphTest#7](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_7.cs)]
     [!code-vb[VSSDKTodoGlyphTest#7](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_7.vb)]  
  
3.  Adlı bir sınıf ekleyin `TodoTag`.  
  
     [!code-csharp[VSSDKTodoGlyphTest#8](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_8.cs)]
     [!code-vb[VSSDKTodoGlyphTest#8](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_8.vb)]  
  
4.  Adlı sınıf değiştirme `TodoTagger` uygulayan <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601> türü `TodoTag`.  
  
     [!code-csharp[VSSDKTodoGlyphTest#9](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_9.cs)]
     [!code-vb[VSSDKTodoGlyphTest#9](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_9.vb)]  
  
5.  İçin `TodoTagger` sınıfı için özel alanlar ekleyin bir <xref:Microsoft.VisualStudio.Text.Classification.IClassifier> ve sınıflandırmasında bulmak metni yayılır.  
  
     [!code-csharp[VSSDKTodoGlyphTest#10](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_10.cs)]
     [!code-vb[VSSDKTodoGlyphTest#10](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_10.vb)]  
  
6.  Sınıflandırıcı ayarlar bir oluşturucu ekleyin.  
  
     [!code-csharp[VSSDKTodoGlyphTest#11](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_11.cs)]
     [!code-vb[VSSDKTodoGlyphTest#11](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_11.vb)]  
  
7.  Uygulama <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601.GetTags%2A> tüm sınıflandırma bulma tarafından yöntemi yayılan, adları "Açıklama" sözcüğü içerir ve arama metni metni içerir. Arama metni bulunduğunda, geri yeni bir verim <xref:Microsoft.VisualStudio.Text.Tagging.TagSpan%601> türü `TodoTag`.  
  
     [!code-csharp[VSSDKTodoGlyphTest#12](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_12.cs)]
     [!code-vb[VSSDKTodoGlyphTest#12](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_12.vb)]  
  
8.  Bildirme bir `TagsChanged` olay.  
  
     [!code-csharp[VSSDKTodoGlyphTest#13](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_13.cs)]
     [!code-vb[VSSDKTodoGlyphTest#13](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_13.vb)]  
  
9. Adlı bir sınıf ekleyin `TodoTaggerProvider` uygulayan <xref:Microsoft.VisualStudio.Text.Tagging.ITaggerProvider>ve onunla verme bir <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "kod" ve <xref:Microsoft.VisualStudio.Text.Tagging.TagTypeAttribute> TodoTag biri.  
  
     [!code-csharp[VSSDKTodoGlyphTest#14](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_14.cs)]
     [!code-vb[VSSDKTodoGlyphTest#14](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_14.vb)]  
  
10. İçeri aktarma <xref:Microsoft.VisualStudio.Text.Classification.IClassifierAggregatorService>.  
  
     [!code-csharp[VSSDKTodoGlyphTest#15](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_15.cs)]
     [!code-vb[VSSDKTodoGlyphTest#15](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_15.vb)]  
  
11. Uygulama <xref:Microsoft.VisualStudio.Text.Tagging.ITaggerProvider.CreateTagger%2A> örneği tarafından yöntemi `TodoTagger`.  
  
     [!code-csharp[VSSDKTodoGlyphTest#16](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_16.cs)]
     [!code-vb[VSSDKTodoGlyphTest#16](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_16.vb)]  
  
## <a name="building-and-testing-the-code"></a>Derleme ve kodu test etme  
 Bu kodu test etmek için TodoGlyphTest çözümü oluşturmak ve deneysel örneğinde çalıştırın.  
  
#### <a name="to-build-and-test-the-todoglyphtest-solution"></a>Derleme ve TodoGlyphTest çözüm sınamak için  
  
1.  Çözümü oluşturun.  
  
2.  F5 tuşuna basarak projeyi çalıştırın. Visual Studio ikinci bir kopyası oluşturulur.  
  
3.  Gösterge Boşluğu gösteren emin olun. (Üzerinde **Araçları** menüsünde tıklatın **seçenekleri**. Üzerinde **metin düzenleyici** sayfasında, olduğundan emin olun **gösterge boşluğu** seçilir.)  
  
4.  Açıklamaları olan bir kod dosyasını açın. "Todo" sözcüğünü yorum bölümleri birine ekleyin.  
  
5.  Koyu mavi anahat sahip açık mavi bir daire kod penceresinin sol gösterge boşluğu görüntülenmelidir.