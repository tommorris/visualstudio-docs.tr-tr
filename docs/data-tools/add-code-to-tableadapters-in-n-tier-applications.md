---
title: N katmanlı uygulamalarda TableAdapter’lara kod ekleme
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- TableAdapters, n-tier applications
- n-tier applications, extending TableAdapters
ms.assetid: dafac00e-df9d-4d4a-95a6-e34b4d099425
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: e5a9aad4aaecb629f5860fadf56e35a55455be63
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2018
ms.locfileid: "34844101"
---
# <a name="add-code-to-tableadapters-in-n-tier-applications"></a>N katmanlı uygulamalarda TableAdapter’lara kod ekleme
TableAdapter için bir parçalı sınıf dosya oluşturarak ve kod eklemeyi bir TableAdapter işlevini genişletme (kod eklemek yerine *DatasetName.DataSet.Designer* dosyası). Kısmi sınıflar arasında birden çok fiziksel dosya bölünür için belirli bir sınıf için kod etkinleştirin. Daha fazla bilgi için bkz: [kısmi](/dotnet/visual-basic/language-reference/modifiers/partial) veya [partial (tür)](/dotnet/csharp/language-reference/keywords/partial-type).

TableAdapter veri kümesinde yapılan bir değişiklik her zaman bir TableAdapter tanımlayan kodu oluşturulur. TableAdapter yapılandırma değiştirir Sihirbazı çalıştırma sırasında değişiklik yapıldığında bu kodu aynı zamanda oluşturulur. Kodunuzu bir TableAdapter yeniden oluşturma işlemi sırasında silinmesini engellemek için kodu TableAdapter parçalı sınıf dosyasına ekleyin.

TableAdapter kod ve veri kümesi ayrı sonra varsayılan olarak, her proje ayrık sınıf dosyasında sonucudur. Özgün proje adlı bir dosya var *DatasetName.Designer.vb* (veya *DatasetName.Designer.cs*) TableAdapter kodunu içerir. İçinde belirtilen proje **Dataset projesi** özelliğinin adlı bir dosya *DatasetName.DataSet.Designer.vb* (veya *DatasetName.DataSet.Designer.cs*), veri kümesi kodunu içerir.

> [!NOTE]
>  Ne zaman, ayrı veri kümeleri ve TableAdapters öğelerini (ayarlayarak **DataSet projesi** özelliği), projedeki mevcut kısmi veri kümesi sınıflarını değil taşınabilir otomatik olarak. Var olan kısmi dataset sınıfları el ile dataset projesi taşınması gerekir.

> [!NOTE]
> Veri kümesi oluşturmak için işlevsellik sağlar <xref:System.Data.DataTable.ColumnChanging> ve <xref:System.Data.DataTable.RowChanging> doğrulama gerektiğinde olay işleyicileri. Daha fazla bilgi için bkz: [n katmanlı veri kümesine doğrulama ekleme](../data-tools/add-validation-to-an-n-tier-dataset.md).

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="to-add-user-code-to-a-tableadapter-in-an-n-tier-application"></a>Bir TableAdapter n katmanlı uygulama içinde kullanıcı kodu eklemek için

1.  İçeren projeye bulun *.xsd* dosya.

2.  Çift tıklayarak *.xsd* açmak için dosya **veri kümesi Tasarımcısı**.

3.  Kodu ekleyin ve ardından istediğiniz TableAdapter sağ **görünümü kodu**.

     Bir parçalı sınıf oluşturulur ve Kod Düzenleyicisi'nde açar.

4.  Parçalı sınıf bildirimi içinde kodu ekleyin.

5.  Aşağıdaki örnek, nereye kodu ekleneceğini gösterir `CustomersTableAdapter` içinde `NorthwindDataSet`:

    ```vb
    Partial Public Class CustomersTableAdapter
        ' Add code here to add functionality
        ' to the CustomersTableAdapter.
    End Class
    ```

    ```csharp
    public partial class CustomersTableAdapter
    {
        // Add code here to add functionality
        // to the CustomersTableAdapter.
    }
    ```

## <a name="see-also"></a>Ayrıca bkz.

- [n katmanlı veri uygulamalarına genel bakış](../data-tools/n-tier-data-applications-overview.md)
- [N katmanlı uygulamalarda veri kümelerine kod ekleme](../data-tools/add-code-to-datasets-in-n-tier-applications.md)
- [TableAdapter’lar oluşturma ve yapılandırma](create-and-configure-tableadapters.md)
- [Hiyerarşik güncelleştirmeye genel bakış](hierarchical-update.md)
