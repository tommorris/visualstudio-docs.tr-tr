---
title: "İzlenecek yol: Küme ayraçları eşleşen görüntüleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], new - brace matching
ms.assetid: 5af08ac7-1d08-4ccf-997e-01aa6cb3d3d7
caps.latest.revision: "27"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: c3dde61c10d0a8c9fc5578b02cc713f648409cbf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-displaying-matching-braces"></a>İzlenecek yol: Eşleşen küme parantezleri görüntüleme
Eşleştirmek istediğiniz küme ayraçları tanımlama ve düzeltme işareti küme ayraçları biri olduğunda bir metin işaretçisi etiketi için eşleşen küme parantezleri ekleyerek eşleşen ayraç gibi dil tabanlı özellikler uygulayabilirsiniz. Bir dil bağlamında küme ayraçları tanımlayabilirsiniz, kendi dosya adı uzantısı ve içerik türünü tanımlayın ve etiketler yalnızca o türü için geçerli veya varolan bir içerik türüyle (örneğin, "metin") etiketleri uygulayabilirsiniz. Aşağıdaki örneklerde, "metin" içerik türü etiketleri eşleşen ayraç uygulamak gösterilmiştir.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-managed-extensibility-framework-mef-project"></a>Yönetilen Genişletilebilirlik Çerçevesi (MEF) proje oluşturma  
  
#### <a name="to-create-a-mef-project"></a>Bir MEF projesi oluşturmak için  
  
1.  Bir düzenleyici sınıflandırıcı projesi oluşturun. Çözüm adı `BraceMatchingTest`.  
  
2.  Bir düzenleyici sınıflandırıcı öğe şablonu projeye ekleyin. Daha fazla bilgi için bkz: [bir düzenleyici öğesi şablonuyla bir uzantısı oluşturma](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
3.  Varolan sınıf dosyaları silin.  
  
## <a name="implementing-a-brace-matching-tagger"></a>Etiketleme eşleşen ayraç uygulama  
 Visual Studio'da kullanılan benzer etkisi vurgulama ayraç almak için bir etiketleme türü uygulayabilirsiniz <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag>. Aşağıdaki kod, iç içe geçme herhangi bir düzeyde parantez çiftlerinin etiketleme tanımlamak gösterilmiştir. Bu örnekte, parantez çiftlerinin [']. [] {} etiketleme oluşturucuda tanımlanmış halde dil belirtimi tam dil uygulamasında ilgili parantez çiftlerinin tanımlanması.  
  
#### <a name="to-implement-a-brace-matching-tagger"></a>Etiketleme eşleşen ayraç uygulamak için  
  
1.  Bir sınıf dosyası ekleyin ve BraceMatching adlandırın.  
  
2.  Şu ad alanlarından içe aktarın.  
  
     [!code-csharp[VSSDKBraceMatchingTest#1](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_1.cs)]
     [!code-vb[VSSDKBraceMatchingTest#1](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_1.vb)]  
  
3.  Bir sınıf tanımlama `BraceMatchingTagger` devraldığı <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601> türü <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag>.  
  
     [!code-csharp[VSSDKBraceMatchingTest#2](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_2.cs)]
     [!code-vb[VSSDKBraceMatchingTest#2](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_2.vb)]  
  
4.  Metin görünümü, kaynak arabelleği ve geçerli anlık görüntü noktası ve ayrıca küme parantezi çiftleri kümesini özellikler ekleyin.  
  
     [!code-csharp[VSSDKBraceMatchingTest#3](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_3.cs)]
     [!code-vb[VSSDKBraceMatchingTest#3](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_3.vb)]  
  
5.  Etiketleme oluşturucuda özelliklerini ayarlamak ve değişiklik olaylarını görüntüle abone <xref:Microsoft.VisualStudio.Text.Editor.ITextCaret.PositionChanged> ve <xref:Microsoft.VisualStudio.Text.Editor.ITextView.LayoutChanged>. Bu örnekte, tanımlayıcı amaçlarla eşleşen çiftleri ayrıca oluşturucuda tanımlanır.  
  
     [!code-csharp[VSSDKBraceMatchingTest#4](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_4.cs)]
     [!code-vb[VSSDKBraceMatchingTest#4](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_4.vb)]  
  
6.  Bir parçası olarak <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601> uygulaması, TagsChanged olay bildirin.  
  
     [!code-csharp[VSSDKBraceMatchingTest#5](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_5.cs)]
     [!code-vb[VSSDKBraceMatchingTest#5](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_5.vb)]  
  
7.  Olay işleyicileri geçerli düzeltme işareti konumunu güncelleştirme `CurrentChar` özelliği ve raise TagsChanged olay.  
  
     [!code-csharp[VSSDKBraceMatchingTest#6](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_6.cs)]
     [!code-vb[VSSDKBraceMatchingTest#6](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_6.vb)]  
  
8.  Uygulama <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601.GetTags%2A> eşleşecek şekilde yöntemi küme ayraçları ya da geçerli karakteri bir açma ayracı veya önceki karakteri Visual Studio gibi bir kapatma parantezi olduğunda olduğunda. Eşleşme bulunduğunda, bu yöntem iki etiket, açma parantezi için diğeri için kapatma parantezi başlatır.  
  
     [!code-csharp[VSSDKBraceMatchingTest#7](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_7.cs)]
     [!code-vb[VSSDKBraceMatchingTest#7](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_7.vb)]  
  
9. Aşağıdaki özel yöntemler iç içe geçme herhangi bir düzeyde eşleşen küme parantezi bulun. İlk yöntem açık karakterle eşleşir Kapat karakter bulur:  
  
     [!code-csharp[VSSDKBraceMatchingTest#8](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_8.cs)]
     [!code-vb[VSSDKBraceMatchingTest#8](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_8.vb)]  
  
10. Aşağıdaki yardımcı yöntemi Kapat bir karakterle eşleşir açık karakter bulur:  
  
     [!code-csharp[VSSDKBraceMatchingTest#9](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_9.cs)]
     [!code-vb[VSSDKBraceMatchingTest#9](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_9.vb)]  
  
## <a name="implementing-a-brace-matching-tagger-provider"></a>Etiketleme sağlayıcısı eşleşen ayraç uygulama  
 Bir etiketleme uygulamadan ek olarak, ayrıca uygulamak ve gerekir etiketleme sağlayıcısı verin. Bu durumda, içerik sağlayıcı "metin" türüdür. Başka bir deyişle, eşleşen ayraç tüm metin dosya türlerini görünür, ancak daha eksiksiz bir uygulama yalnızca belirli bir içerik türüne eşleşen ayraç geçerli olur.  
  
#### <a name="to-implement-a-brace-matching-tagger-provider"></a>Ayraç eşleştirme etiketleme sağlayıcısını uygulamak için  
  
1.  Öğesinden devralınan bir etiketleme sağlayıcısı bildirme <xref:Microsoft.VisualStudio.Text.Tagging.IViewTaggerProvider>BraceMatchingTaggerProvider adlandırın ve onunla dışarı aktarma bir <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "metin" ve <xref:Microsoft.VisualStudio.Text.Tagging.TagTypeAttribute> , <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag>.  
  
     [!code-csharp[VSSDKBraceMatchingTest#10](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_10.cs)]
     [!code-vb[VSSDKBraceMatchingTest#10](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_10.vb)]  
  
2.  Uygulama <xref:Microsoft.VisualStudio.Text.Tagging.IViewTaggerProvider.CreateTagger%2A> bir BraceMatchingTagger örneği oluşturmak için yöntem.  
  
     [!code-csharp[VSSDKBraceMatchingTest#11](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_11.cs)]
     [!code-vb[VSSDKBraceMatchingTest#11](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_11.vb)]  
  
## <a name="building-and-testing-the-code"></a>Derleme ve kodu test etme  
 Bu kodu test etmek için BraceMatchingTest çözümü oluşturmak ve deneysel örneğinde çalıştırın.  
  
#### <a name="to-build-and-test-bracematchingtest-solution"></a>Derleme ve BraceMatchingTest çözüm sınamak için  
  
1.  Çözümü oluşturun.  
  
2.  Bu proje Hata Ayıklayıcısı'ndaki çalıştırdığınızda, Visual Studio ikinci bir örneğini örneği.  
  
3.  Bir metin dosyası oluşturun ve eşleşen küme parantezleri içeren herhangi bir metin yazın.  
  
    ```  
    hello {  
    goodbye}  
  
    {}  
  
    {hello}  
    ```  
  
4.  Bir açma ayracı önce şapka getirdiğinizde, bu kuşak hem eşleşen kapatma ayracı vurgulanmış olmalıdır. Yalnızca kapatma parantezi sonra imleci getirdiğinizde, bu kuşak hem eşleşen açma ayracı vurgulanmış olmalıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek Yol: Bir İçerik Türünü Dosya Adı Uzantısına Bağlama](../extensibility/walkthrough-linking-a-content-type-to-a-file-name-extension.md)