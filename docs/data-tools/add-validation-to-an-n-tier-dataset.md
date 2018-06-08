---
title: N Katmanlı bir veri kümesine doğrulama ekleme
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- n-tier applications, validating
- validation [Visual Basic], n-tier data applications
- validating n-tier data applications
ms.assetid: 34ce4db6-09bb-4b46-b435-b2514aac52d3
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 81d929aaffb6f08e5e1cda1cf3329de81fe13bc8
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845411"
---
# <a name="add-validation-to-an-n-tier-dataset"></a>N Katmanlı bir veri kümesine doğrulama ekleme
N katmanlı çözümünü ayrılmış bir veri kümesine doğrulama ekleme temelde tek dosya dataset (veri kümesinde tek bir proje) için doğrulama ekleme ile aynıdır. Verileri doğrulama gerçekleştirmek için önerilen sırasında konumdur <xref:System.Data.DataTable.ColumnChanging> ve/veya <xref:System.Data.DataTable.RowChanging> veri tablosu olayları.

 Veri kümesi için kullanıcı kodu sütun ve satır değiştirme olayları kümesindeki veri tabloları ekleyebileceğiniz kısmi sınıflar oluşturmak için işlevsellik sağlar. N katmanlı çözümünü kümesinde için kod ekleme hakkında daha fazla bilgi için bkz: [n katmanlı uygulamalarda veri kümelerine kod ekleme](../data-tools/add-code-to-datasets-in-n-tier-applications.md), ve [n katmanlı uygulamalarda TableAdapters için kodu ekleyin](../data-tools/add-code-to-tableadapters-in-n-tier-applications.md). Kısmi sınıflar hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir sınıfı kısmi sınıflara (Sınıf Tasarımcısı) bölme](../ide/how-to-split-a-class-into-partial-classes-class-designer.md) veya [kısmi sınıflar ve yöntemler](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods).

> [!NOTE]
>  Ne zaman, ayrı veri kümeleri TableAdapters (ayarlayarak **DataSet projesi** özelliği), projedeki mevcut kısmi veri kümesi sınıflarını olmaz taşınabilir otomatik olarak. Var olan kısmi dataset sınıfları el ile dataset projesi taşınması gerekir.

> [!NOTE]
>  Veri kümesi Tasarımcısı otomatik olarak oluşturmaz olay işleyicileri için C# <xref:System.Data.DataTable.ColumnChanging> ve <xref:System.Data.DataTable.RowChanging> olaylar. El ile bir olay işleyicisi oluşturun ve temeldeki olayının olay işleyicisine bağlanacağını gerekmez. Aşağıdaki yordamlar gerekli olay işleyicileri hem Visual Basic ve C# içinde nasıl oluşturulacağını açıklar.

## <a name="validate-changes-to-individual-columns"></a>Tek tek sütuna değişiklikleri doğrulama
 Tek tek sütunlardaki değerleri işleyerek doğrulamak <xref:System.Data.DataTable.ColumnChanging> olay. <xref:System.Data.DataTable.ColumnChanging> Olayı, bir sütundaki değeri değiştirildiğinde oluşturulur. İçin bir olay işleyicisi oluşturun <xref:System.Data.DataTable.ColumnChanging> üzerinde istenen sütun çift tıklatarak olay **veri kümesi Tasarımcısı**.

 Bir sütundaki çift ilk kez Tasarımcısı için bir olay işleyicisi oluşturur <xref:System.Data.DataTable.ColumnChanging> olay. Bir `If...Then` deyimi de oluşturulur belirli bir sütun için test. Çift Örneğin, aşağıdaki kod oluşturulur **GereklilikTarihi** Northwind Siparişler tablosundaki sütun:

```vb
Private Sub OrdersDataTable_ColumnChanging(ByVal sender As System.Object, ByVal e As System.Data.DataColumnChangeEventArgs) Handles Me.ColumnChanging
    If (e.Column.ColumnName = Me.RequiredDateColumn.ColumnName) Then
        ' Add validation code here.
    End If
End Sub
```

> [!NOTE]
>  C# projelerinde, veri kümesi Tasarımcısı yalnızca veri kümesi ve kümesindeki tek tek tablolar için kısmi sınıflar oluşturur. Veri kümesi Tasarımcısı olay işleyicileri için otomatik olarak oluşturmaz <xref:System.Data.DataTable.ColumnChanging> ve <xref:System.Data.DataTable.RowChanging> C# ' de Visual Basic'te yaptığı gibi olaylar. C# projelerinde, el ile olay işleme ve arka plandaki olay yöntemi bağlanacağını için bir yöntem oluşturmak gerekir. Aşağıdaki yordam, hem Visual Basic ve C# ' gerekli olay işleyicileri oluşturma adımları sağlar.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

#### <a name="to-add-validation-during-changes-to-individual-column-values"></a>Değişiklikleri sırasında doğrulama için tek tek sütun değerlerini eklemek için

1.  Veri kümesi çift tıklatarak açın *.xsd* dosyasını **Çözüm Gezgini**. Daha fazla bilgi için bkz: [izlenecek yol: veri kümesi tasarımcısında bir veri kümesi oluşturma](walkthrough-creating-a-dataset-with-the-dataset-designer.md).

2.  Doğrulamak istediğiniz sütun çift tıklayın. Bu eylem oluşturur <xref:System.Data.DataTable.ColumnChanging> olay işleyicisi.

    > [!NOTE]
    >  Veri kümesi Tasarımcısı C# olayı için bir olay işleyicisi otomatik olarak oluşturmaz. C# olayını işlemek gerekli olan kod bir sonraki bölümde eklenmiştir. `SampleColumnChangingEvent` oluşturulur ve en çok sayfaya <xref:System.Data.DataTable.ColumnChanging> olayında <xref:System.Data.DataTable.EndInit%2A> yöntemi.

3.  Doğrulamak için kodu ekleyin `e.ProposedValue` uygulamanızı gereksinimlerini karşılayan verileri içerir. Önerilen değer kabul edilebilir değilse, bir hata var. göstermek için sütun ayarlayın.

     Aşağıdaki kod örneğinde doğrular **miktar** sütun 0'dan büyük bir değer içeriyor. Varsa **miktar** küçük veya ona eşit bir hata sütun 0 olarak ayarlanır. `Else` Yan tümcesi varsa hata temizler **miktar** 0'dan büyük. Sütun değiştirme olay işleyicisi kodunda aşağıdakine benzemelidir:

    ```vb
    If (e.Column.ColumnName = Me.QuantityColumn.ColumnName) Then
        If CType(e.ProposedValue, Short) <= 0 Then
            e.Row.SetColumnError(e.Column, "Quantity must be greater than 0")
        Else
            e.Row.SetColumnError(e.Column, "")
        End If
    End If
    ```
    ```csharp
    // Add this code to the DataTable partial class.

    public override void EndInit()
    {
        base.EndInit();
        // Hook up the ColumnChanging event
        // to call the SampleColumnChangingEvent method.
        ColumnChanging += SampleColumnChangingEvent;
    }

    public void SampleColumnChangingEvent(object sender, System.Data.DataColumnChangeEventArgs e)
    {
        if (e.Column.ColumnName == QuantityColumn.ColumnName)
        {
            if ((short)e.ProposedValue <= 0)
            {
                e.Row.SetColumnError("Quantity", "Quantity must be greater than 0");
            }
            else
            {
                e.Row.SetColumnError("Quantity", "");
            }
        }
    }
    ```

## <a name="validate-changes-to-whole-rows"></a>Tüm satırlara değişiklikleri doğrulama
 Tüm satırların değerlerini işleyerek doğrulamak <xref:System.Data.DataTable.RowChanging> olay. <xref:System.Data.DataTable.RowChanging> Tüm sütunlardaki değerlerin taahhüt olduğunuzda olayı oluşturulur. İçinde doğrulamak gerekli olan <xref:System.Data.DataTable.RowChanging> olay bir sütun değeri başka bir sütun değeri kullanır. Örneğin, Northwind Siparişler tablosundaki OrderDate ve GereklilikTarihi düşünün.

 Siparişleri girilen olduğunda doğrulama sipariş üzerinde veya OrderDate önce GereklilikTarihi ile girilen değil emin hale getirir. Bir tek sütun değişikliği doğrulama anlamsız için bu örnekte, GerekliTarih ve OrderDate sütunlar için değerleri karşılaştırmak olması gerekir.

 İçin bir olay işleyicisi oluşturun <xref:System.Data.DataTable.RowChanging> üzerinde başlık çubuğunda tablosunun tablo adı çift tıklatarak olay **veri kümesi Tasarımcısı**.

#### <a name="to-add-validation-during-changes-to-whole-rows"></a>Tüm satır değişiklikleri sırasında doğrulama eklemek için

1.  Veri kümesi çift tıklatarak açın *.xsd* dosyasını **Çözüm Gezgini**. Daha fazla bilgi için bkz: [izlenecek yol: veri kümesi tasarımcısında bir veri kümesi oluşturma](walkthrough-creating-a-dataset-with-the-dataset-designer.md).

2.  Başlık çubuğu Tasarımcı veri tabloya çift tıklayın.

     Bir parçalı sınıf ile oluşturulan bir `RowChanging` olay işleyicisi ve Kod Düzenleyicisi'nde açar.

    > [!NOTE]
    >  Veri kümesi Tasarımcısı için bir olay işleyicisi otomatik olarak oluşturmaz <xref:System.Data.DataTable.RowChanging> C# projelerinde olay. İşlemek için bir yöntem oluşturmak zorunda <xref:System.Data.DataTable.RowChanging> olay ve ardından tablonun başlatma yöntemini olayda bağlanacağını kodu çalıştırın.

3.  Parçalı sınıf bildirimi içinde kullanıcı kodu ekleyin.

4.  Aşağıdaki kod nereye sırasında doğrulamak için kullanıcı kodu ekleneceğini gösterir <xref:System.Data.DataTable.RowChanging> olay. C# örnek olay işleyicisi yöntemi kadar bağlanmanıza kodunu da içeren `OrdersRowChanging` olay.

    ```vb
    Partial Class OrdersDataTable
        Private Sub OrdersDataTable_OrdersRowChanging(ByVal sender As System.Object, ByVal e As OrdersRowChangeEvent) Handles Me.OrdersRowChanging
            ' Add logic to validate columns here.
            If e.Row.RequiredDate <= e.Row.OrderDate Then
                ' Set the RowError if validation fails.
                e.Row.RowError = "Required Date cannot be on or before the OrderDate"
            Else
                ' Clear the RowError when validation passes.
                e.Row.RowError = ""
            End If
        End Sub
    End Class
    ```
    ```csharp
    partial class OrdersDataTable
    {
        public override void EndInit()
        {
            base.EndInit();
            // Hook up the event to the
            // RowChangingEvent method.
            OrdersRowChanging += RowChangingEvent;
        }

        public void RowChangingEvent(object sender, OrdersRowChangeEvent e)
        {
            // Perform the validation logic.
            if (e.Row.RequiredDate <= e.Row.OrderDate)
            {
                // Set the row to an error when validation fails.
                e.Row.RowError = "Required Date cannot be on or before the OrderDate";
            }
            else
            {
                // Clear the RowError if validation passes.
                e.Row.RowError = "";
            }
        }
    }
    ```

## <a name="see-also"></a>Ayrıca bkz.

- [n katmanlı veri uygulamalarına genel bakış](../data-tools/n-tier-data-applications-overview.md)
- [İzlenecek yol: N katmanlı veri uygulaması oluşturma](../data-tools/walkthrough-creating-an-n-tier-data-application.md)
- [Veri kümelerindeki verileri doğrulama](../data-tools/validate-data-in-datasets.md)