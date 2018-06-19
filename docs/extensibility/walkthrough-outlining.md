---
title: 'İzlenecek yol: Anahat oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - outlining
ms.assetid: d75a44aa-265a-44d4-9c28-457f59c4ff9f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8360daf5ff1e7d94d995bdbefee6228a47e47db8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31143904"
---
# <a name="walkthrough-outlining"></a>İzlenecek yol: anahat oluşturma
Dil tabanlı özellikleri genişletmek veya daraltmak için istediğiniz metin bölgeler türlerini tanımlayarak anahat oluşturma gibi uygulayabilirsiniz. Bir dil hizmeti bağlamında bölgeler tanımlayabilirsiniz kendi dosya adı uzantısı ve içerik türünü tanımlayın ve bölge tanımı yalnızca o türü için geçerli veya varolan bir içerik türüyle (örneğin, "metin") bölge tanımları uygulayabilirsiniz. Bu kılavuzda, tanımlayın ve anahat bölgelerini görüntülemek gösterilmektedir.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-managed-extensibility-framework-mef-project"></a>Yönetilen Genişletilebilirlik Çerçevesi (MEF) proje oluşturma  
  
#### <a name="to-create-a-mef-project"></a>Bir MEF projesi oluşturmak için  
  
1.  Bir VSIX projesi oluşturun. Çözüm adı `OutlineRegionTest`.  
  
2.  Bir düzenleyici sınıflandırıcı öğe şablonu projeye ekleyin. Daha fazla bilgi için bkz: [bir düzenleyici öğesi şablonuyla bir uzantısı oluşturma](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
3.  Varolan sınıf dosyaları silin.  
  
## <a name="implementing-an-outlining-tagger"></a>Anahat etiketleme uygulama  
 Anahat bölgeler etiketi bir tür işaretlenmiş (<xref:Microsoft.VisualStudio.Text.Tagging.OutliningRegionTag>). Bu etiket davranışı anahat oluşturma standart sağlar. Anahatları belirlenmiş bölge genişletilmiş veya daraltılmış. Anahatları belirlenmiş bölge genişletilmiş olarak ve genişletilmiş bölge dikey bir çizgiyle güncelleştireceğinizi bir daraltılmışsa artı veya eksi işareti işaretlenir.  
  
 Aşağıdaki adımları virgülle ayrılan tüm bölgeler için anahat bölgeler oluşturur etiketleme tanımlamak nasıl Göster "[" ve "]".  
  
#### <a name="to-implement-an-outlining-tagger"></a>Anahat etiketleme uygulamak için  
  
1.  Bir sınıf dosyası ekleyin ve adını `OutliningTagger`.  
  
2.  Şu ad alanlarından içe aktarın.  
  
     [!code-csharp[VSSDKOutlineRegionTest#1](../extensibility/codesnippet/CSharp/walkthrough-outlining_1.cs)]
     [!code-vb[VSSDKOutlineRegionTest#1](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_1.vb)]  
  
3.  Adlı bir sınıf oluşturun `OutliningTagger`, ve uygulama <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601>:  
  
     [!code-csharp[VSSDKOutlineRegionTest#2](../extensibility/codesnippet/CSharp/walkthrough-outlining_2.cs)]
     [!code-vb[VSSDKOutlineRegionTest#2](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_2.vb)]  
  
4.  Anlık görüntü ve metin arabelleğini izlemek ve bölgeler anahat oluşturma olarak etiketlenmiş satır kümesi accumulate için bazı alanlar ekleyin. Bu kodu anahat bölgeleri temsil eden (daha sonra tanımlanacak) bölge nesneleri listesini içerir.  
  
     [!code-csharp[VSSDKOutlineRegionTest#3](../extensibility/codesnippet/CSharp/walkthrough-outlining_3.cs)]
     [!code-vb[VSSDKOutlineRegionTest#3](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_3.vb)]  
  
5.  Alanları başlatır etiketleme bir oluşturucu ekleyin arabellek ayrıştırır ve bir olay işleyicisi ekler <xref:Microsoft.VisualStudio.Text.ITextBuffer.Changed> olay.  
  
     [!code-csharp[VSSDKOutlineRegionTest#4](../extensibility/codesnippet/CSharp/walkthrough-outlining_4.cs)]
     [!code-vb[VSSDKOutlineRegionTest#4](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_4.vb)]  
  
6.  Uygulama <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601.GetTags%2A> etiket başlatır yöntemi yayılır. Bu örnek varsayar yayılma <xref:Microsoft.VisualStudio.Text.NormalizedSpanCollection> yönteme geçirilen bitişik, ancak bu her zaman durumda olmayabilir. Bu yöntem her anahat bölgeler için yeni bir etiket aralık başlatır.  
  
     [!code-csharp[VSSDKOutlineRegionTest#5](../extensibility/codesnippet/CSharp/walkthrough-outlining_5.cs)]
     [!code-vb[VSSDKOutlineRegionTest#5](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_5.vb)]  
  
7.  Bildirme bir `TagsChanged` olay işleyicisi.  
  
     [!code-csharp[VSSDKOutlineRegionTest#6](../extensibility/codesnippet/CSharp/walkthrough-outlining_6.cs)]
     [!code-vb[VSSDKOutlineRegionTest#6](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_6.vb)]  
  
8.  Ekleme bir `BufferChanged` yanıtlar olay işleyicisi <xref:Microsoft.VisualStudio.Text.ITextBuffer.Changed> metin arabelleği ayrıştırma tarafından olaylar.  
  
     [!code-csharp[VSSDKOutlineRegionTest#7](../extensibility/codesnippet/CSharp/walkthrough-outlining_7.cs)]
     [!code-vb[VSSDKOutlineRegionTest#7](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_7.vb)]  
  
9. Arabellek ayrıştıran bir yöntem ekleyin. Burada verilen yalnızca bir örnektir. İç içe geçmiş anahat bölgelere arabellek zaman uyumlu olarak ayrıştırır.  
  
     [!code-csharp[VSSDKOutlineRegionTest#8](../extensibility/codesnippet/CSharp/walkthrough-outlining_8.cs)]
     [!code-vb[VSSDKOutlineRegionTest#8](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_8.vb)]  
  
10. Aşağıdaki yardımcı yöntemi, sol parantez çifti 1 olacak şekilde, anahat düzeyini temsil eden bir tamsayı alır.  
  
     [!code-csharp[VSSDKOutlineRegionTest#9](../extensibility/codesnippet/CSharp/walkthrough-outlining_9.cs)]
     [!code-vb[VSSDKOutlineRegionTest#9](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_9.vb)]  
  
11. Aşağıdaki yardımcı yöntemi (Bu konuda daha sonra tanımlanan) bir bölge içinde SnapshotSpan çevirir.  
  
     [!code-csharp[VSSDKOutlineRegionTest#10](../extensibility/codesnippet/CSharp/walkthrough-outlining_10.cs)]
     [!code-vb[VSSDKOutlineRegionTest#10](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_10.vb)]  
  
12. Yalnızca gösterim amacıyla kodudur. Anahat bölge ve (varsa) üst bölge için bir başvuru başlangıç uzaklığı ve satır numarası içeren bir PartialRegion sınıf tanımlar. Bu bölgeler anahat oluşturma iç içe geçmiş ayarlamak ayrıştırıcı sağlar. Türetilmiş bir bölge sınıf anahat bölge sonuna satır sayısı için bir başvuru içeriyor.  
  
     [!code-csharp[VSSDKOutlineRegionTest#11](../extensibility/codesnippet/CSharp/walkthrough-outlining_11.cs)]
     [!code-vb[VSSDKOutlineRegionTest#11](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_11.vb)]  
  
## <a name="implementing-a-tagger-provider"></a>Etiketleme sağlayıcıyı uygulama  
 Etiketleme sağlayıcısı, etiketleme için dışarı aktarmanız gerekir. Etiketleme sağlayıcısı oluşturur bir `OutliningTagger` "metin" içerik türü ya da başka döndürür bir arabellek için bir `OutliningTagger` arabellek zaten varsa.  
  
#### <a name="to-implement-a-tagger-provider"></a>Etiketleme sağlayıcısını uygulamak için  
  
1.  Adlı bir sınıf oluşturun `OutliningTaggerProvider` uygulayan <xref:Microsoft.VisualStudio.Text.Tagging.ITaggerProvider>ve ContentType ve TagType özniteliklerle verin.  
  
     [!code-csharp[VSSDKOutlineRegionTest#12](../extensibility/codesnippet/CSharp/walkthrough-outlining_12.cs)]
     [!code-vb[VSSDKOutlineRegionTest#12](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_12.vb)]  
  
2.  Uygulama <xref:Microsoft.VisualStudio.Text.Tagging.ITaggerProvider.CreateTagger%2A> ekleyerek yöntemi bir `OutliningTagger` arabellek özelliklerine.  
  
     [!code-csharp[VSSDKOutlineRegionTest#13](../extensibility/codesnippet/CSharp/walkthrough-outlining_13.cs)]
     [!code-vb[VSSDKOutlineRegionTest#13](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_13.vb)]  
  
## <a name="building-and-testing-the-code"></a>Derleme ve kodu test etme  
 Bu kodu test etmek için OutlineRegionTest çözümü oluşturmak ve deneysel örneğinde çalıştırın.  
  
#### <a name="to-build-and-test-the-outlineregiontest-solution"></a>Derleme ve OutlineRegionTest çözüm sınamak için  
  
1.  Çözümü oluşturun.  
  
2.  Bu proje Hata Ayıklayıcısı'ndaki çalıştırdığınızda, Visual Studio ikinci bir örneğini örneği.  
  
3.  Bir metin dosyası oluşturun. Açılış ayracı ve kapanış ayracı içeren herhangi bir metin yazın.  
  
    ```  
    [  
       Hello  
    ]  
    ```  
  
4.  Her iki küme ayraçları içeren bir anahat bölge olması gerekir. Anahat bölge daraltmak için eksi işareti açma ayracı solundaki tıklatın olması gerekir. Ne zaman bölge daraltıldığında, üç nokta (...) simgenin daraltılmış bölge ve metin içeren bir açılır solunda görünmelidir **Vurgulu metin** üç nokta üzerinde işaretçinin taşıdığınızda görünmelidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek Yol: Bir İçerik Türünü Dosya Adı Uzantısına Bağlama](../extensibility/walkthrough-linking-a-content-type-to-a-file-name-extension.md)