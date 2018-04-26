---
title: Parametreleştirilmiş TableAdapter sorguları oluşturma
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Visual Studio], TableAdapters
- TableAdapters, parameterized queries
- data [Visual Studio], searching data
- queries [Visual Studio], creating
- TableAdapters, searching data
- queries [Visual Studio], TableAdapters
ms.assetid: 104d1d19-b5a9-4071-b81e-1b3af08e9c7b
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 7d3985cc8faf76c5c5767090abd5b87101ddbb45
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="create-parameterized-tableadapter-queries"></a>Parametreleştirilmiş TableAdapter sorguları oluşturma
Parametreli bir sorgu WHERE yan tümcesi sorgusundan koşullarını karşılayan verileri döndürür. Yalnızca Müşteriler ekleyerek belirli bir şehirde görüntülemek için bir müşteri listesi gibi Parametreleştirme `WHERE City = @City` bitiş SQL deyiminin müşterilerin listesini döndürür.

 Parametreleştirilmiş TableAdapter sorguları oluşturma **veri kümesi Tasarımcısı**. Bir Windows uygulaması de oluşturabilirsiniz **Parametreleştirme veri kaynağı** komutunu **veri** menüsü. **Parametreleştirme veri kaynağı** komut burada parametre değerlerini girin ve sorguyu çalıştırmak, formdaki denetimlerin oluşturur.

> [!NOTE]
> Parametreleştirilmiş sorgu oluşturma sırasında karşı kodlama veritabanına özel parametre gösterimini kullanın. Örneğin, soru işareti erişim ve OleDb veri kaynaklarını kullanmak '?' parametrelerini belirtmek için bu nedenle WHERE yan tümcesi şuna benzeyebilir: `WHERE City = ?`.

> [!NOTE]
> İletişim kutuları ve menü komutlarını gördüğünüz açıklanana Yardım'da active ayarlarınızı veya kullanmakta olduğunuz edition bağlı olarak farklı olabilir. Ayarlarınızı değiştirmek için Git **Araçları** menü ve select **içeri ve dışarı aktarma ayarları**. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).

## <a name="create-a-parameterized-tableadapter-query"></a>Parametreleştirilmiş TableAdapter sorgu oluşturma

#### <a name="to-create-a-parameterized-query-in-the-dataset-designer"></a>Veri kümesi Tasarımcısı'nda parametreli bir sorgu oluşturmak için

-   SQL deyimindeki WHERE yan tümcesi istenen parametrelerle ekleme yeni bir TableAdapter oluşturun. Daha fazla bilgi için bkz: [oluşturma ve TableAdapters öğelerini yapılandırma](../data-tools/create-and-configure-tableadapters.md).

     -veya-

-   Sorguda WHERE yan tümcesi istenen parametrelerle SQL deyiminde ekleme varolan bir TableAdapter ekleyin.

#### <a name="to-create-a-parameterized-query-while-designing-a-data-bound-form"></a>Veri bağlama form tasarlarken parametreli bir sorgu oluşturmak için

1.  Formunuzda zaten bir veri kümesine bağlı bir denetim seçin. Daha fazla bilgi için bkz: [bağlamak Windows Forms denetimleri Visual Studio'da verilere](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md).

2.  Üzerinde **veri** menüsünde, select **Sorgu Ekle**.

3.  Tamamlamak **arama ölçütleri Oluşturucu** iletişim kutusunda, istenen parametrelere sahip bir WHERE yan tümcesi SQL deyiminde ekleme.

### <a name="to-add-a-query-to-an-existing-data-bound-form"></a>Varolan bir veri bağlama forma bir sorgu ekleme

1.  Formunda açmak **Windows Form Tasarımcısı**.

2.  Üzerinde **veri** menüsünde, select **Sorgu Ekle** veya **veri akıllı etiketler**.

    > [!NOTE]
    >  Varsa **Sorgu Ekle** bulunmaz **veri** menüsü, görüntüler veri kaynağı, formdaki bir denetime parametrelemeyi eklemek için seçin. Örneğin, form verileri görüntüleyen bir <xref:System.Windows.Forms.DataGridView> denetlemek, onu seçin. Form verilerini tek tek denetimlerinde görüntüler, herhangi bir veri bağlama denetimi seçin.

3.  İçinde **Select veri kaynağı tablosu** alanı, seçin, istediğiniz tablo için parametrelemeyi ekleyin.

4.  Bir ad yazın **yeni sorgu adı** yeni bir sorgu oluşturuyorsanız kutusu.

     -veya-

     Sorguda seçin **varolan sorgu adı** kutusu.

5.  İçinde **sorgu metni** parametreler isteyen bir sorgu yazın.

6.  Seçin **Tamam**.

     Bir giriş parametresi için denetimi ve bir **yük** düğmesi, formda eklenir bir <xref:System.Windows.Forms.ToolStrip> denetim.

#### <a name="querying-for-null-values"></a>Null değerler için sorgulama
Geçerli bir değere sahip kayıtları için sorgu istediğinizde TableAdapter parametreleri null değerler atanabilir. Örneğin, sahip aşağıdaki sorguyu göz önünde bulundurun bir `ShippedDate` parametresinde kendi `WHERE` yan tümcesi:

 ```sql
SELECT CustomerID, OrderDate, ShippedDate
FROM Orders
WHERE (ShippedDate = @ShippedDate) OR (ShippedDate IS NULL)
```

 Bu bir TableAdapter sorgu olsaydı, aşağıdaki kod ile birlikte değil tüm siparişler için sorgu:

 [!code-csharp[VbRaddataTableAdapters#8](../data-tools/codesnippet/CSharp/create-parameterized-tableadapter-queries_1.cs)]
 [!code-vb[VbRaddataTableAdapters#8](../data-tools/codesnippet/VisualBasic/create-parameterized-tableadapter-queries_1.vb)]

 Null değerleri kabul etmek bir sorgu etkinleştirmek için:

1.  İçinde **veri kümesi Tasarımcısı**, boş parametre değerleri kabul etmek için gereken TableAdapter sorgu seçin.

2.  İçinde **özellikleri** penceresinde, seçin **parametreleri**, üç nokta düğmesine (**...** ) açmak için düğmeye **parametreler koleksiyonu Düzenleyicisi**.

3.  Null değerlere izin verdiği parametre seçin ve ayarlayın **AllowDbNull** özelliğine `true`.

## <a name="see-also"></a>Ayrıca bkz.

- [TableAdapters kullanarak veri kümelerini doldurma](../data-tools/fill-datasets-by-using-tableadapters.md)