---
title: "Nasıl yapılır: derleme ve çalıştırma LinqToXmlDataBinding örnek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3943deaf-80e2-4968-ac04-d3ef56cfad6c
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a90e55a60c9451229fd767dac6a8aaa0e2a2e224
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-build-and-run-the-linqtoxmldatabinding-example"></a>Nasıl yapılır: derleme ve LinqToXmlDataBinding örnek çalıştırma
Bu konu ve LinqToXmlDataBinding Visual Studio projesi oluşturmak nasıl ve sonuçta elde edilen LinqToXmlDataBinding Windows Presentation Foundation (WPF) örnek programının nasıl çalıştırılacağını gösterir.  
  
 Proje oluşturmak için Visual Studio kullanma hakkında daha fazla bilgi için bkz: [Visual Studio'da uygulama geliştirme](http://msdn.microsoft.com/en-us/97490c1b-a247-41fb-8f2c-bc4c201eff68).  
  
## <a name="creating-and-populating-the-project"></a>Oluşturma ve projeyi doldurma  
  
#### <a name="to-create-the-starting-project"></a>Başlangıç projesi oluşturmak için  
  
1.  Visual Studio'yu başlatın ve LinqToXmlDataBinding adlı bir C# WPF uygulaması oluşturun. Projeyi .NET Framework 3.5 (veya üzeri) kullanmanız gerekir.  
  
2.  Aksi halde zaten mevcut proje başvuruları için aşağıdaki .NET derlemelerini ekleyin:  
  
    -   System.Data  
  
    -   System.Data.DataSetExtensions  
  
    -   System.Xml  
  
    -   System.Xml.Linq  
  
3.  Tuşlarına basarak çözümü oluşturun **Ctnrl + Shift + B**, çalıştırın tuşlarına basarak **F5**. Proje hatasız derleyip genel WPF uygulaması çalıştırın.  
  
#### <a name="to-add-custom-code-to-the-project"></a>Özel kod projesine eklemek için  
  
1.  Çözüm Gezgini'nde, L2XDBForm.xaml için Window1.xaml kaynak dosyayı yeniden adlandırın. Bağımlı kaynak dosyası Window1.xaml.cs L2XDBForm.xaml.cs için otomatik olarak adlandırılmamalıdır.  
  
2.  Kaynak kodu bulunan konu kod bölümünden ile L2XDBForm.xaml dosyasında Değiştir [L2DBForm.xaml kaynak kodu](../designers/l2dbform-xaml-source-code.md). (Bu dosya ile çalışmak için XAML kaynağı görünümü kullanın.)  
  
3.  Benzer şekilde, L2XDBForm.xaml.cs kaynağında bulunan kod yerine [L2DBForm.xaml.cs kaynak kodu](../designers/l2dbform-xaml-cs-source-code.md).  
  
4.  Dosya App.xaml tüm oluşumlarını "L2XDBForm.xaml" ile "Window1.xaml" dizesini değiştirin.  
  
5.  Çözüm tuşlarına basarak yapı **Ctrl + Shift + B**.  
  
## <a name="running-the-program"></a>Programın çalıştırılması  
 LinqToXmlDataBinding programın görüntülemek ve katıştırılmış bir XML öğesi depolanan books listesini değiştirmek kullanıcının sağlar.  
  
#### <a name="to-run-the-program-and-view-the-book-list"></a>Programını çalıştırın ve kitap listesini görüntülemek için  
  
1.  Basarak LinqToXmlDataBinding çalıştırmak **F5** (**hata ayıklamayı Başlat**) veya **Ctrl + F5** (**hata ayıklama olmadan Başlat**). Bir program penceresi başlığı ile **LINQ-XML kullanarak WPF veri bağlama** görüntülenmesi gerekir.  
  
2.  Ham görüntüler UI penceresinin üst kısmında fark **XML** kitap listesini temsil eden. Bir WPF kullanılarak görüntülenir <xref:System.Windows.Controls.TextBlock> klavye ve fare etkileşiminin etkinleştirmez denetim.  
  
3.  Etiketli ikinci dikey bölümde **kitap listesi**, görüntüler defterleri düz metin olarak sıralı listesi. Kullandığı bir <xref:System.Windows.Controls.ListBox> seçimi, ancak klavye ve fare sağlar denetim.  
  
#### <a name="to-add-and-delete-books-from-the-list"></a>Eklemek ve books listeden silmek için  
  
1.  Varolan bir kitabı listeden silmek için seçin **kitap listesi** bölümünde ve ardından **seçili kitap kaldırmak** düğmesi. Kitap hem ham XML kaynak listelerini defteri girdisi kaldırıldı dikkat edin.  
  
2.  Yeni bir rehberi listeye eklemek için içine değerleri girin **kimliği** ve **değeri** <xref:System.Windows.Controls.TextBox> son Kısım denetimlerinde **yeni rehberi Ekle**, ardından **Ekle Kitap** düğmesi. Not Defteri kitap ve XML listeleme listesine eklenir. Bu program giriş değerleri doğrulamaz.  
  
#### <a name="to-edit-an-existing-book-entry"></a>Varolan bir kitap girişi düzenlemek için  
  
1.  İkinci Rehberi girişini seçin **kitap listesi** bölümü. Geçerli değerlerini üçüncü bölümünde görüntülenmelidir **seçili kitap Düzenle**.  
  
2.  Klavyeyi kullanarak değerlerini düzenleyin. Kısa sürede ya da <xref:System.Windows.Controls.TextBox> denetim odağı looses, değişiklikleri XML kaynağını ve rehberi listelerini otomatik olarak yayılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LINQ-XML örneği kullanarak WPF veri bağlama](../designers/wpf-data-binding-using-linq-to-xml-example.md)   
 [İzlenecek yol: LinqToXmlDataBinding örneği](../designers/walkthrough-linqtoxmldatabinding-example.md)   
 [Visual Studio'da uygulama geliştirme](http://msdn.microsoft.com/en-us/97490c1b-a247-41fb-8f2c-bc4c201eff68)