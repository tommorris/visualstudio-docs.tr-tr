---
title: "İzlenecek yol: XAML Tasarımcısı'nda verileri bağlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.XamlDesigner.DataBinding
ms.assetid: 1a99aeae-c3ef-407d-ba79-b8055489a43d
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 65345f4c606ef9882d6c737e0dc1f3f0cbe99026
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-binding-to-data-in-xaml-designer"></a>İzlenecek yol: XAML Tasarımcısı'nda veri bağlama
XAML Tasarımcısı'nda çalışma yüzeyi ve Özellikler penceresini kullanarak veri bağlama özellikleri ayarlayabilirsiniz. Bu kılavuzda örnek verinin bir denetime nasıl bağlanacağını gösterir. Özellikle, izlenecek olan basit bir alışveriş sepeti sınıfı oluşturma gösterilmektedir bir [DependencyProperty](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.dependencyproperty.aspx) adlı `ItemCount`ve ardından bağlamak `ItemCount` özelliğine **metin** özelliği bir [TextBlock](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.textblock.aspx) denetim.  
  
### <a name="to-create-a-class-to-use-as-a-data-source"></a>Veri kaynağı olarak kullanmak için bir sınıf oluşturmak için  
  
1.  Üzerinde **dosya** menüsünde seçin **yeni**, **proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda, seçin **Visual C#** veya **Visual Basic** düğümünü genişletin **Windows Masaüstü** düğümü ve ardından seçin **WPF uygulaması** şablonu.  
  
3.  Proje adı **BindingTest**ve ardından **Tamam** düğmesi.  
  
4.  MainWindow.xaml.cs (veya MainWindow.xaml.vb) dosyasını açın ve aşağıdaki kodu ekleyin. C# ' ta kodda eklemek `BindingTest` ad alanı (önce dosyayı son kapatma parantezi). Visual Basic'te, yalnızca yeni sınıf ekleyin.  
  
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
  
     Bu kodu kullanarak değerinin 0 varsayılan öğesi sayısı ayarlar [PropertyMetadata](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.propertymetadata.aspx) nesnesi.  
  
5.  Üzerinde **dosya** menüsünde seçin **yapı**, **yapı çözümü**.  
  
### <a name="to-bind-the-itemcount-property-to-a-textblock-control"></a>TextBlock denetimi ItemCount özelliği bağlamak için  
  
1.  Çözüm Gezgini'nde, MainWindow.xaml için kısayol menüsünü açın ve seçin **Görünüm Tasarımcısı**.  
  
2.  Araç kutusunda seçin bir [kılavuz](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.grid.aspx) denetlemek ve forma ekleyin.  
  
3.  İle `Grid` Özellikler penceresinde seçili seçin **yeni** düğmesine **DataContext** özelliği.  
  
4.  İçinde **nesnesi Seç** iletişim kutusunda, olduğundan emin olun **tüm derlemelerde Göster** onay kutusu işaretli değilse, seçin **ShoppingCart** altında **BindingTest** ad alanı ve ardından **Tamam** düğmesi.  
  
     Aşağıdaki çizimde gösterildiği **nesnesi Seç** iletişim kutusuyla **ShoppingCart** seçili.  
  
     ![Nesne Seç iletişim kutusu](../designers/media/blendselectobject.PNG "BlendSelectObject")  
  
5.  İçinde **araç**, seçin bir `TextBlock` denetim forma ekleyin.  
  
6.  İle `TextBlock` denetimi, Özellikler penceresinde seçili seçin sağındaki özelliği işaret **metin** özelliği ve ardından **oluşturma verileri bağlama**. (Özellik işaretçisi küçük bir kutu gibi görünür.)  
  
7.  İletişim kutusu, bağlama oluşturma verilerdeki **yolu** kutusunda, seçin **ItemCount: (int32)** özelliği ve ardından **Tamam** düğmesi.  
  
     Aşağıdaki çizimde gösterildiği **oluşturma verileri bağlama** iletişim kutusuyla **ItemCount** seçili özelliği.  
  
     ![Oluştur iletişim kutusu veri bağlama](../designers/media/xaml_create_data_binding.png "xaml_create_data_binding")  
  
8.  Uygulamayı çalıştırmak için F5 tuşuna basın.  
  
     `TextBlock` Denetimi 0 varsayılan değerini metin olarak göster.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XAML Tasarımcısı kullanarak bir kullanıcı Arabirimi oluşturma](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md)   
 [Değer dönüştürücüsü iletişim kutusu ekleme](https://msdn.microsoft.com/en-us/c5f3d110-a541-4b55-8bca-928f77778af8)