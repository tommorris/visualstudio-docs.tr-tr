---
title: L2DBForm.xaml.cs kaynak kodu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-designers
ms.topic: conceptual
ms.assetid: 5a40dad3-6763-4576-b3ad-874df3f2c8d9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7493ce758628ee8f5d20fccc9653505c74ac3875
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="l2dbformxamlcs-source-code"></a>L2DBForm.xaml.cs kaynak kodu
Bu konu, içeriği ve C# kaynak kodu dosyasına L2DBForm.xaml.cs açıklamasını içerir. Bu dosyada bulunan L2XDBForm parçalı sınıf üç mantıksal bölümlere ayrılabilir: veri üyeleri ve `OnRemove` ve `OnAddBook` olay işleyicileri düğmesini tıklatın.  
  
## <a name="data-members"></a>Veri üyeleri  
 İki özel veri üyeleri bu sınıf L2DBForm.xaml içinde kullanılan pencere kaynaklarına ilişkilendirmek için kullanılır.  
  
-   Ad alanı değişkeni `myBooks` için başlatılan `"http://www.mybooks.com"`.  
  
-   Üye `bookList` L2DBForm.xaml CDATA dizesinde aşağıdaki satırı ile oluşturucuya başlatılır:  
  
    ```  
    bookList = (XElement)((ObjectDataProvider)Resources["LoadedBooks"]).Data;  
    ```  
  
## <a name="onaddbook-event-handler"></a>OnAddBook olay işleyicisi  
 Bu yöntem aşağıdaki üç ifadeleri içerir:  
  
-   İlk koşul deyimi, giriş doğrulaması için kullanılır.  
  
-   İkinci ifade yeni bir oluşturur <xref:System.Xml.Linq.XElement> girilen kullanıcı dizeden değerleri **yeni rehberi Ekle** kullanıcı arabirimi (UI) bölümü.  
  
-   Son deyim L2DBForm.xaml veri sağlayıcısının bu yeni bir kitap öğesi ekler. Sonuç olarak, dinamik veri bağlama otomatik olarak UI bu yeni öğe ile güncelleştirmek; Ek kullanıcı tarafından sağlanan kod gereklidir.  
  
## <a name="onremove-event-handler"></a>OnRemove olay işleyicisi  
 `OnRemove` İşleyicisidir daha karmaşıktır `OnAddBook` için iki nedenden dolayı işleyici. Ham XML korunan boşluk içerdiği için ilk olarak, satır başı eşleşen ayrıca defteri girişiyle kaldırılması gerekir. İkinci olarak, kolaylık, silinmiş öğe üzerinde olduğu, seçim listesinde önceki bir sıfırlanır.  
  
 Ancak seçilen defteri öğesi kaldırmanın çekirdek iş yalnızca iki deyimleri tarafından gerçekleştirilir:  
  
-   İlk olarak, liste kutusunda seçili öğenin ilişkili kitap öğesini alınır:  
  
    ```  
    XElement selBook = (XElement)lbBooks.SelectedItem;   
    ```  
  
-   Ardından, bu öğenin veri sağlayıcısı'ndan silinir:  
  
    ```  
    selBook.Remove();  
    ```  
  
 Yeniden, dinamik veri bağlama programın UI otomatik olarak güncelleştirilir sağlar.  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
  
### <a name="code"></a>Kod  
  
```csharp  
using System;  
using System.Linq;  
using System.Collections;  
using System.Collections.Generic;  
using System.Diagnostics;  
using System.Text;  
using System.Windows;  
using System.Windows.Controls;  
using System.Windows.Data;  
using System.Windows.Input;  
using System.Xml;  
using System.Xml.Linq;  
  
namespace LinqToXmlDataBinding {  
    /// <summary>  
    /// Interaction logic for L2XDBForm.xaml  
    /// </summary>  
  
    public partial class L2XDBForm : System.Windows.Window   
    {  
        XNamespace mybooks = "http://www.mybooks.com";  
        XElement bookList;  
  
        public L2XDBForm()   
        {  
            InitializeComponent();  
            bookList = (XElement)((ObjectDataProvider)Resources["LoadedBooks"]).Data;  
        }  
  
        void OnRemoveBook(object sender, EventArgs e)   
        {  
            int index = lbBooks.SelectedIndex;  
            if (index < 0) return;  
  
            XElement selBook = (XElement)lbBooks.SelectedItem;  
            //Get next node before removing element.  
            XNode nextNode = selBook.NextNode;  
            selBook.Remove();  
  
            //Remove any matching newline node.  
            if (nextNode != null && nextNode.ToString().Trim().Equals(""))  
            { nextNode.Remove(); }  
  
            //Set selected item.   
            if (lbBooks.Items.Count > 0)  
            {  lbBooks.SelectedItem = lbBooks.Items[index > 0 ? index - 1 : 0]; }  
        }  
  
        void OnAddBook(object sender, EventArgs e)   
        {  
            if (String.IsNullOrEmpty(tbAddID.Text) ||  
                String.IsNullOrEmpty(tbAddValue.Text))  
            {  
                MessageBox.Show("Please supply both a Book ID and a Value!", "Entry Error!");  
                return;   
            }  
            XElement newBook = new XElement(  
                                mybooks + "book",  
                                new XAttribute("id", tbAddID.Text),  
                                tbAddValue.Text);  
            bookList.Add("  ", newBook, "\r\n");  
        }  
    }  
}  
  
```  
  
### <a name="comments"></a>Açıklamalar  
 Bu işleyiciler için ilişkili XAML kaynağı için [L2DBForm.xaml kaynak kodu](../designers/l2dbform-xaml-source-code.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: LinqToXmlDataBinding örneği](../designers/walkthrough-linqtoxmldatabinding-example.md)   
 [L2DBForm.xaml Kaynak Kodu](../designers/l2dbform-xaml-source-code.md)