---
title: "İzlenecek yol: metin görünümü özelleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], new - customizing the view
ms.assetid: 32d32ac8-22ff-4de7-af69-bd46ec4ad9bf
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: ecbf5e3bed5ba506278f00b2b5b0b76f8f02850a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-customizing-the-text-view"></a>İzlenecek yol: metin görünümü özelleştirme
Metin görünümü, düzenleyici biçimi eşlemesindeki aşağıdaki özelliklerden herhangi birini değiştirerek özelleştirebilirsiniz:  
  
-   Gösterge Boşluğu  
  
-   Ekleme düzeltme işareti  
  
-   Düzeltme işareti üzerine yaz  
  
-   Seçili metni  
  
-   Etkin olmayan seçili metinle (odağını kaybetmiş diğer bir deyişle, seçili)  
  
-   Görünür boşluk  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-mef-project"></a>Bir MEF projesi oluşturma  
  
1.  Bir C# VSIX projesi oluşturun. (İçinde **yeni proje** iletişim kutusunda **Visual C# / genişletilebilirlik**, ardından **VSIX proje**.) Çözüm adı `ViewPropertyTest`.  
  
2.  Bir düzenleyici sınıflandırıcı öğe şablonu projeye ekleyin. Daha fazla bilgi için bkz: [bir düzenleyici öğesi şablonuyla bir uzantısı oluşturma](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
3.  Varolan sınıf dosyaları silin.  
  
## <a name="defining-the-content-type"></a>İçerik türü tanımlama  
  
1.  Bir sınıf dosyası ekleyin ve adını `ViewPropertyModifier`.  
  
2.  Aşağıdakileri ekleyin `using` yönergeleri:  
  
     [!code-csharp[VSSDKViewPropertyTest#1](../extensibility/codesnippet/CSharp/walkthrough-customizing-the-text-view_1.cs)]
     [!code-vb[VSSDKViewPropertyTest#1](../extensibility/codesnippet/VisualBasic/walkthrough-customizing-the-text-view_1.vb)]  
  
3.  Adlı bir sınıf bildirme `TestViewCreationListener` devraldığı <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener>. Bu sınıf aşağıdaki özniteliklerle dışarı aktarın:  
  
    -   <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>Bu dinleyici uygulandığı içerik türünü belirtmek için.  
  
    -   <xref:Microsoft.VisualStudio.Text.Editor.TextViewRoleAttribute>Bu dinleyici rolü belirtmek için.  
  
     [!code-csharp[VSSDKViewPropertyTest#2](../extensibility/codesnippet/CSharp/walkthrough-customizing-the-text-view_2.cs)]
     [!code-vb[VSSDKViewPropertyTest#2](../extensibility/codesnippet/VisualBasic/walkthrough-customizing-the-text-view_2.vb)]  
  
4.  Bu sınıf, içeri aktarma <xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMapService>.  
  
     [!code-csharp[VSSDKViewPropertyTest#3](../extensibility/codesnippet/CSharp/walkthrough-customizing-the-text-view_3.cs)]
     [!code-vb[VSSDKViewPropertyTest#3](../extensibility/codesnippet/VisualBasic/walkthrough-customizing-the-text-view_3.vb)]  
  
## <a name="changing-the-view-properties"></a>Görünüm özelliklerini değiştirme  
  
1.  Uygulama <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener.TextViewCreated%2A> yöntemi böylece görünüm açıldığında özelliklerini görüntüleme değiştirilir. Değişiklik yapmak için ilk bulma <xref:System.Windows.ResourceDictionary> bulmak istediğiniz görünümü en/boy karşılık gelir. Ardından uygun kaynak sözlüğü özelliğini değiştirin ve özelliklerini ayarlayın. Çağrıları toplu <xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMap.SetProperties%2A> yöntemini çağırarak <xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMap.BeginBatchUpdate%2A> özelliklerini ayarlamadan önce yöntemi ve ardından <xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMap.EndBatchUpdate%2A> özellikler ayarlandıktan sonra.  
  
     [!code-csharp[VSSDKViewPropertyTest#4](../extensibility/codesnippet/CSharp/walkthrough-customizing-the-text-view_4.cs)]
     [!code-vb[VSSDKViewPropertyTest#4](../extensibility/codesnippet/VisualBasic/walkthrough-customizing-the-text-view_4.vb)]  
  
## <a name="building-and-testing-the-code"></a>Derleme ve kodu test etme  
  
1.  Çözümü oluşturun.  
  
     Bu proje Hata Ayıklayıcısı'ndaki çalıştırdığınızda, Visual Studio ikinci bir örneğini örneği.  
  
2.  Bir metin dosyası oluşturun ve bazı metin yazın.  
  
    -   Ekleme düzeltme işareti macenta olmalıdır ve üzerine yazma şapka Turkuaz olması gerekir.  
  
    -   Gösterge boşluğu ('metin görünümü sol) açık olmalıdır yeşil.  
  
3.  Yazdığınız metni seçin. Seçili metnin rengini açık olmalıdır pembe.  
  
4.  Metin seçiliyken metin penceresi dışında herhangi bir yere tıklayın. Seçili metnin rengini koyu pembe olmalıdır.  
  
5.  Üzerinde görünür boşluk açın. (Üzerinde **Düzenle** menüsündeki **Gelişmiş** ve ardından **görünüm boşluk**). Bazı sekmeler metni yazın. Sekmeleri temsil eden kırmızı oklar görüntülenmesi gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dil Hizmeti ve Düzenleyici Uzantı Noktaları](../extensibility/language-service-and-editor-extension-points.md)