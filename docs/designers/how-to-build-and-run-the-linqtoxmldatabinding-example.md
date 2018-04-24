---
title: 'Nasıl yapılır: derleme ve LinqToXmlDataBinding örnek çalıştırma'
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: de5515d96d5aa0dff30082207e7f20fd7981fc89
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-build-and-run-the-linqtoxmldatabinding-example"></a>Nasıl yapılır: derleme ve LinqToXmlDataBinding örnek çalıştırma

Bu konu ve LinqToXmlDataBinding Visual Studio projesi oluşturmak nasıl ve sonuçta elde edilen LinqToXmlDataBinding Windows Presentation Foundation (WPF) örnek programının nasıl çalıştırılacağını gösterir.

Visual Studio hakkında daha fazla bilgi için bkz: [Visual Studio IDE genel bakış](../ide/visual-studio-ide.md).

## <a name="creating-and-populating-the-project"></a>Oluşturma ve projeyi doldurma

### <a name="to-create-the-starting-project"></a>Başlangıç projesi oluşturmak için

1. Visual Studio'yu başlatın ve LinqToXmlDataBinding adlı bir C# WPF uygulaması oluşturun. Projeyi .NET Framework 3.5 (veya üzeri) kullanmanız gerekir.

1. Aksi halde zaten mevcut proje başvuruları için aşağıdaki .NET derlemelerini ekleyin:

    - System.Data

    - System.Data.DataSetExtensions

    - System.Xml

    - System.Xml.Linq

1. Tuşlarına basarak çözümü oluşturun **Ctrl + Shift + B**, çalıştırın tuşlarına basarak **F5**. Proje hatasız derleyip genel WPF uygulaması çalıştırın.

### <a name="to-add-custom-code-to-the-project"></a>Özel kod projesine eklemek için

1. Çözüm Gezgini'nde, L2XDBForm.xaml için Window1.xaml kaynak dosyayı yeniden adlandırın. Bağımlı kaynak dosyası Window1.xaml.cs L2XDBForm.xaml.cs için otomatik olarak adlandırılmamalıdır.

1. Kaynak kodu bulunan konu kod bölümünden ile L2XDBForm.xaml dosyasında Değiştir [L2DBForm.xaml kaynak kodu](../designers/l2dbform-xaml-source-code.md). Bu dosya ile çalışmak için XAML kaynağı görünümünü kullanın.

1. Benzer şekilde, L2XDBForm.xaml.cs kaynağında bulunan kod yerine [L2DBForm.xaml.cs kaynak kodu](../designers/l2dbform-xaml-cs-source-code.md).

1. Dosya App.xaml tüm oluşumlarını "L2XDBForm.xaml" ile "Window1.xaml" dizesini değiştirin.

1. Çözüm tuşlarına basarak yapı **Ctrl + Shift + B**.

## <a name="running-the-program"></a>Programın çalıştırılması

LinqToXmlDataBinding programın görüntülemek ve katıştırılmış bir XML öğesi depolanan books listesini değiştirmek kullanıcının sağlar.

### <a name="to-run-the-program-and-view-the-book-list"></a>Programını çalıştırın ve kitap listesini görüntülemek için

- Basarak LinqToXmlDataBinding çalıştırmak **F5** (**hata ayıklamayı Başlat**) veya **Ctrl + F5** (**hata ayıklama olmadan Başlat**).

   Bir program penceresi başlığı ile **LINQ-XML kullanarak WPF veri bağlama** görüntülenir.

- Ham görüntüler UI penceresinin üst kısmında fark **XML** kitap listesini temsil eden. Bir WPF kullanılarak görüntülenir <xref:System.Windows.Controls.TextBlock> klavye ve fare etkileşiminin etkinleştirmez denetim.

- Etiketli ikinci dikey bölümde **kitap listesi**, görüntüler defterleri düz metin olarak sıralı listesi. Kullandığı bir <xref:System.Windows.Controls.ListBox> seçimi, ancak klavye ve fare sağlar denetim.

### <a name="to-add-and-delete-books-from-the-list"></a>Eklemek ve books listeden silmek için

- Varolan bir kitabı listeden silmek için seçin **kitap listesi** bölümünde ve ardından **seçili kitap kaldırmak** düğmesi. Kitap hem ham XML kaynak listelerini defteri girdisi kaldırıldı dikkat edin.

- Yeni bir rehberi listeye eklemek için içine değerleri girin **kimliği** ve **değeri** <xref:System.Windows.Controls.TextBox> son Kısım denetimlerinde **yeni rehberi Ekle**, ardından **Ekle Kitap** düğmesi. Not Defteri kitap ve XML listeleme listesine eklenir. Bu program giriş değerleri doğrulamaz.

### <a name="to-edit-an-existing-book-entry"></a>Varolan bir kitap girişi düzenlemek için

1. İkinci Rehberi girişini seçin **kitap listesi** bölümü. Geçerli değerlerini üçüncü bölümünde görüntülenmelidir **seçili kitap Düzenle**.

1. Klavyeyi kullanarak değerlerini düzenleyin. Kısa sürede ya da <xref:System.Windows.Controls.TextBox> denetim odağı looses, değişiklikleri XML kaynağını ve rehberi listelerini otomatik olarak yayılır.

## <a name="see-also"></a>Ayrıca bkz.

- [LINQ to XML Kullanarak WPF Verilerini Bağlama Örneği](../designers/wpf-data-binding-using-linq-to-xml-example.md)
- [İzlenecek Yol: LinqToXmlDataBinding Örneği](../designers/walkthrough-linqtoxmldatabinding-example.md)
- [Visual Studio IDE’ye Genel Bakış](../ide/visual-studio-ide.md)