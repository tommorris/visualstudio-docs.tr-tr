---
title: XAML Tasarımcısı'nda verilere bağlayın
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
f1_keywords:
- VS.XamlDesigner.DataBinding
dev_langs:
- CSharp
- VB
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 2c12d1ca9605a7591146f3d6141eb12b5f8975f6
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34745717"
---
# <a name="walkthrough-bind-to-data-in-xaml-designer"></a>İzlenecek yol: XAML Tasarımcısı’nda verilere bağlama

XAML Tasarımcısı'nda çalışma yüzeyi ve Özellikler penceresini kullanarak veri bağlama özellikleri ayarlayabilirsiniz. Bu kılavuzda örnek verinin bir denetime nasıl bağlanacağını gösterir. Özellikle, izlenecek olan basit bir alışveriş sepeti sınıfı oluşturma gösterilmektedir bir [DependencyProperty](/uwp/api/Windows.UI.Xaml.DependencyProperty) adlı `ItemCount`ve ardından bağlamak `ItemCount` özelliğine **metin** özelliği bir [TextBlock](/uwp/api/Windows.UI.Xaml.Controls.TextBlock) denetim.

## <a name="to-create-a-class-to-use-as-a-data-source"></a>Veri kaynağı olarak kullanmak için bir sınıf oluşturmak için

1. Üzerinde **dosya** menüsünde seçin **yeni**> **proje**.

1. İçinde **yeni proje** iletişim kutusunda, seçin **Visual C#** veya **Visual Basic** düğümünü genişletin **Windows Masaüstü** düğümü ve ardından seçin **WPF uygulaması** şablonu.

1. Proje adı **BindingTest**ve ardından **Tamam** düğmesi.

1. MainWindow.xaml.cs (veya MainWindow.xaml.vb) dosyasını açın ve aşağıdaki kodu ekleyin. C# ' ta kodda eklemek `BindingTest` ad alanı (önce dosyayı son kapatma parantezi). Visual Basic'te, yalnızca yeni sınıf ekleyin.

   ```csharp
   public class ShoppingCart : DependencyObject
   {
       public int ItemCount
       {
           get { return (int)GetValue(ItemCountProperty); }
           set { SetValue(ItemCountProperty, value); }
       }

       public static readonly DependencyProperty ItemCountProperty =
            DependencyProperty.Register("ItemCount", typeof(int),
            typeof(ShoppingCart), new PropertyMetadata(0));
   }
   ```

   ```vb
   Public Class ShoppingCart
       Inherits DependencyObject

       Public Shared ReadOnly ItemCountProperty As DependencyProperty = DependencyProperty.Register(
            "ItemCount", GetType(Integer), GetType(ShoppingCart), New PropertyMetadata(0))
       Public Property ItemCount As Integer
           Get
               ItemCount = CType(GetValue(ItemCountProperty), Integer)
           End Get
           Set(value As Integer)
               SetValue(ItemCountProperty, value)
           End Set
       End Property
   End Class
   ```

   Bu kodu kullanarak değerinin 0 varsayılan öğesi sayısı ayarlar [PropertyMetadata](/uwp/api/Windows.UI.Xaml.PropertyMetadata) nesnesi.

1. Üzerinde **dosya** menüsünde seçin **yapı** > **yapı çözümü**.

## <a name="to-bind-the-itemcount-property-to-a-textblock-control"></a>TextBlock denetimi ItemCount özelliği bağlamak için

1. Çözüm Gezgini'nde, MainWindow.xaml için kısayol menüsünü açın ve seçin **Görünüm Tasarımcısı**.

1. Araç kutusunda seçin bir [kılavuz](/uwp/api/Windows.UI.Xaml.Controls.Grid) denetlemek ve forma ekleyin.

1. İle `Grid` Özellikler penceresinde seçili seçin **yeni** düğmesine **DataContext** özelliği.

1. İçinde **nesnesi Seç** iletişim kutusunda, olduğundan emin olun **tüm derlemelerde Göster** onay kutusu işaretli değilse, seçin **ShoppingCart** altında **BindingTest** ad alanı ve ardından **Tamam** düğmesi.

     Aşağıdaki çizimde gösterildiği **nesnesi Seç** iletişim kutusuyla **ShoppingCart** seçili.

     ![Nesne iletişim kutusu seç](../designers/media/blendselectobject.png)

1. İçinde **araç**, seçin bir `TextBlock` denetim forma ekleyin.

1. İle `TextBlock` denetimi, Özellikler penceresinde seçili seçin sağındaki özelliği işaret **metin** özelliği ve ardından **oluşturma verileri bağlama**. (Özellik işaretçisi küçük bir kutu gibi görünür.)

1. İletişim kutusu, bağlama oluşturma verilerdeki **yolu** kutusunda, seçin **ItemCount: (int32)** özelliği ve ardından **Tamam** düğmesi.

     Aşağıdaki çizimde gösterildiği **oluşturma verileri bağlama** iletişim kutusuyla **ItemCount** seçili özelliği.

     ![Oluştur iletişim kutusu veri bağlama](../designers/media/xaml_create_data_binding.png)

1. Tuşuna **F5** uygulamayı çalıştırmak için.

     `TextBlock` Denetimi 0 varsayılan değerini metin olarak göster.

## <a name="see-also"></a>Ayrıca bkz.

- [XAML Tasarımcısı’nı kullanarak bir kullanıcı arabirimi oluşturma](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md)
- [Değer dönüştürücüsü iletişim kutusu ekleme](https://msdn.microsoft.com/c5f3d110-a541-4b55-8bca-928f77778af8)