---
title: Sorgu veri kümeleri
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
ms.assetid: 7b1a91cf-8b5a-4fc0-ac36-0dc2d336fa1b
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 0fb1310649a1aeba7fd46acf9277ef7ea5825472
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="query-datasets"></a>Sorgu veri kümeleri
Bir veri kümesinde belirli kayıtları aramak için DataTable nesnesinde FindBy yöntemini kullanmak, tablonun satır koleksiyon üzerinde döngü veya kullanmak için kendi foreach deyimi yazma [LINQ-DataSet](/dotnet/framework/data/adonet/linq-to-dataset).

## <a name="dataset-case-sensitivity"></a>Veri kümesi büyük/küçük harfe duyarlılık
Tablo ve sütun adları bir veri kümesi içinde varsayılan olarak büyük küçük harf duyarsız — diğer bir deyişle, bir tablodaki "Müşteri" adlı bir veri kümesi de için "Müşteri" olarak belirtilebilir Bu SQL Server dahil olmak üzere birçok veritabanlarında adlandırma kuralları eşleşir. SQL Server ' veri öğelerinin adları yalnızca örneğe göre ayırt varsayılan davranıştır.

> [!NOTE]
>  Şemalarda tanımlanan veri öğelerinin adları büyük/küçük harfe duyarlıdır şekilde veri kümeleri farklı olarak, XML belgeleri, küçük harf duyarlıdır. Örneğin, "Müşteri" ve "Müşteri" olarak adlandırılan farklı bir tablo adında bir tablo tanımlamak şema şema protokol sağlar Yalnızca örneğe göre farklılık öğeleri içeren bir şema dataset sınıfı oluşturmak için kullanıldığında, bu ad çakışmalarına neden olabilir.

Büyük küçük harfe duyarlılığın, ancak, veri kümesi içinde nasıl yorumlanacağını bir etken olabilir. Örneğin, bir veri kümesi tablodaki verileri filtre uygularsanız, arama ölçütlerini karşılaştırma büyük küçük harfe duyarlı olup olmamasına bağlı olarak farklı sonuçlar döndürebilir. Filtreleme, aramayı ve veri kümesi'nin ayarlayarak sıralama büyük küçük harfe duyarlılığın denetleyebilirsiniz <xref:System.Data.DataSet.CaseSensitive%2A> özelliği. Veri kümesi tüm tablolarda bu özelliğin değeri varsayılan olarak devralır. (Bu özellik tek tek her tablo için tablonun ayarlayarak kılabilirsiniz <xref:System.Data.DataTable.CaseSensitive%2A> özelliğini.)

## <a name="locate-a-specific-row-in-a-data-table"></a>Bir veri tablosunda belirli bir satırdan bulun

#### <a name="to-find-a-row-in-a-typed-dataset-with-a-primary-key-value"></a>Türü belirtilmiş veri kümesi birincil anahtar değerine sahip bir satır bulmak için

-   Bir satır bulmak için türü kesin belirlenmiş çağrı `FindBy` tablonun birincil anahtarı kullanan yöntemi.

     Aşağıdaki örnekte, `CustomerID` sütundur birincil anahtarı `Customers` tablo. Oluşturulan buna `FindBy` yöntemi `FindByCustomerID`. Örnek, belirli bir atama gösterir <xref:System.Data.DataRow> oluşturulan kullanarak bir değişkene `FindBy` yöntemi.

     [!code-csharp[VbRaddataEditing#18](../data-tools/codesnippet/CSharp/query-datasets_1.cs)]
     [!code-vb[VbRaddataEditing#18](../data-tools/codesnippet/VisualBasic/query-datasets_1.vb)]

#### <a name="to-find-a-row-in-an-untyped-dataset-with-a-primary-key-value"></a>Birincil anahtar değerine sahip bir türsüz kümesindeki bir satır bulmak için

-   Çağrı <xref:System.Data.DataRowCollection.Find%2A> yöntemi bir <xref:System.Data.DataRowCollection> koleksiyonu, birincil anahtar parametre olarak geçirme.

     Aşağıdaki örnek olarak adlandırılan yeni bir satır bildirmek nasıl gösterir `foundRow` ve dönüş değerini atayın <xref:System.Data.DataRowCollection.Find%2A> yöntemi. Birincil anahtar bulunursa, sütun dizini 1 içeriğini bir ileti kutusu görüntülenir.

     [!code-csharp[VbRaddataEditing#19](../data-tools/codesnippet/CSharp/query-datasets_2.cs)]
     [!code-vb[VbRaddataEditing#19](../data-tools/codesnippet/VisualBasic/query-datasets_2.vb)]

## <a name="find-rows-by-column-values"></a>Sütun değerleri tarafından satırları bulur

#### <a name="to-find-rows-based-on-the-values-in-any-column"></a>Bir sütundaki değerlere göre satırları bulmak için

-   Veri tabloları ile oluşturulan <xref:System.Data.DataTable.Select%2A> bir dizi döndürür yöntemi <xref:System.Data.DataRow>ifadesi temelinde s geçirilen <xref:System.Data.DataTable.Select%2A> yöntemi. Geçerli ifadeler oluşturma hakkında daha fazla bilgi için sayfanın "İfade sözdizimini" bölümüne bakın <xref:System.Data.DataColumn.Expression%2A> özelliği.

     Aşağıdaki örnekte nasıl kullanılacağını gösterir <xref:System.Data.DataTable.Select%2A> yöntemi <xref:System.Data.DataTable> belirli satır bulunamadı.

     [!code-csharp[VbRaddataEditing#20](../data-tools/codesnippet/CSharp/query-datasets_3.cs)]
     [!code-vb[VbRaddataEditing#20](../data-tools/codesnippet/VisualBasic/query-datasets_3.vb)]

## <a name="access-related-records"></a>Erişim ilgili kayıtları
Bir veri kümesi tablolarda işlerken bir <xref:System.Data.DataRelation> nesne yapabilir ilgili kayıtlar başka bir tablodaki kullanılabilir. Örneğin, veri kümesi içeren bir `Customers` ve `Orders` tablolar kullanılabilir hale getirebilir.

Kullanabileceğiniz bir <xref:System.Data.DataRelation> çağırarak ilgili kayıtları bulun nesnesine <xref:System.Data.DataRow.GetChildRows%2A> yöntemi bir <xref:System.Data.DataRow> üst tablodan. Bu yöntem, ilgili alt kayıtları bir dizi döndürür. Ya da çağırabilirsiniz <xref:System.Data.DataRow.GetParentRow%2A> yöntemi bir <xref:System.Data.DataRow> alt tablosundaki. Bu yöntem tek bir <xref:System.Data.DataRow> üst tablodan.

Bu sayfa yazılan veri kümeleri kullanan örnekler sağlar. Yazılmayan veri kümeleri ilişkilerde gezinme hakkında daha fazla bilgi için bkz: [gezinme DataRelations](/dotnet/framework/data/adonet/dataset-datatable-dataview/navigating-datarelations).

> [!NOTE]
>  Bir Windows Forms uygulamasında çalışma ve verileri görüntülemek için veri bağlama özellikleri kullanarak, tasarımcısı tarafından oluşturulan form uygulamanız için yeterli işlevler sağlayabilir. Daha fazla bilgi için bkz: [Visual Studio'da verilere denetimler bağlama](../data-tools/bind-controls-to-data-in-visual-studio.md). Özellikle, görmek [kümelerindeki ilişkiler](relationships-in-datasets.md).

Aşağıdaki kod örnekleri, yazılan veri kümeleri ilişkilerde yukarı ve aşağı gidin göstermektedir. Yazılan kod örnekleri kullan <xref:System.Data.DataRow>s (`NorthwindDataSet.OrdersRow`) ve oluşturulan FindBy*PrimaryKey* (`FindByCustomerID`) istenen satırı bulun ve ilgili kayıtları döndürmek için yöntemler. Örnekler derlemek ve yalnızca varsa doğru çalıştırın:

-   Adlı bir veri örneği `NorthwindDataSet` ile bir `Customers` tablo.

-   Bir `Orders` tablo.

-   Adlı bir ilişki `FK_Orders_Customers`iki tablo ilgili.

Ayrıca, her iki tabloyu döndürülecek herhangi bir kayıt için verileri ile doldurulması gerekir.

#### <a name="to-return-the-child-records-of-a-selected-parent-record"></a>Seçilen üst kaydının kayıtları alt döndürmek için

-   Çağrı <xref:System.Data.DataRow.GetChildRows%2A> belirli bir yöntemi `Customers` veri satırın ve satır içeren bir dizi döndürecek `Orders` tablosu:

     [!code-csharp[VbRaddataDatasets#6](../data-tools/codesnippet/CSharp/query-datasets_4.cs)]
     [!code-vb[VbRaddataDatasets#6](../data-tools/codesnippet/VisualBasic/query-datasets_4.vb)]

#### <a name="to-return-the-parent-record-of-a-selected-child-record"></a>Seçili alt kaydının üst kaydı döndürmek için

-   Çağrı <xref:System.Data.DataRow.GetParentRow%2A> belirli bir yöntemi `Orders` veri satırı ve tek bir satır başı `Customers` tablosu:

     [!code-csharp[VbRaddataDatasets#7](../data-tools/codesnippet/CSharp/query-datasets_5.cs)]
     [!code-vb[VbRaddataDatasets#7](../data-tools/codesnippet/VisualBasic/query-datasets_5.vb)]

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da veri kümesi araçları](../data-tools/dataset-tools-in-visual-studio.md)