---
title: Bir TableAdapter işlevini genişletme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Visual Studio], TableAdapters
- data [Visual Studio], extending TableAdapters
- TableAdapters, adding functionality
ms.assetid: 418249c8-c7f3-47ef-a94c-744cb6fe6aaf
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: d163461f559432752815d2f1e1fec103d93a84ec
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="extend-the-functionality-of-a-tableadapter"></a>Bir TableAdapter işlevini genişletme
Kod TableAdapter'ın parçalı sınıf dosyasına ekleyerek bir TableAdapter işlevini genişletebilirsiniz.  
  
 TableAdapter içinde yapılan herhangi bir değişiklik olduğunda bir TableAdapter tanımlar kod yeniden **veri kümesi Tasarımcısı**, veya ne zaman bir sihirbaz değiştiren bir TableAdapter yapılandırma. Kodunuzu bir TableAdapter yeniden oluşturma işlemi sırasında silinmesini engellemek için kodu TableAdapter'ın parçalı sınıf dosyasına ekleyin.  
  
 Kısmi sınıflar arasında birden çok fiziksel dosya bölünür için belirli bir sınıf için kod sağlar. Daha fazla bilgi için bkz: [kısmi](/dotnet/visual-basic/language-reference/modifiers/partial) veya [partial (tür)](/dotnet/csharp/language-reference/keywords/partial-type).  
  
## <a name="locate-tableadapters-in-code"></a>Kod içinde TableAdapters bulun  
 TableAdapters ile tasarlanmıştır sırada **veri kümesi Tasarımcısı**, oluşturulan TableAdapter sınıfları, iç içe geçmiş sınıflar olmayan <xref:System.Data.DataSet>. TableAdapters TableAdapter'ın ilişkili veri kümesi adını temel alarak bir ad alanı bulunur. Örneğin, uygulamanız adlı bir veri içeriyorsa `HRDataSet`, TableAdapters içinde bulunması `HRDataSetTableAdapters` ad alanı. (Bu deseni adlandırma kuralını izler: *DatasetName* + `TableAdapters`).  
  
 Aşağıdaki örnek adlı bir TableAdapter varsayar `CustomersTableAdapter`sahip bir proje olarak `NorthwindDataSet`.  
  
#### <a name="to-create-a-partial-class-for-a-tableadapter"></a>TableAdapter için bir parçalı sınıf oluşturmak için  
  
1.  Giderek projeniz için yeni bir sınıf ekleyin **proje** menü ve seçerek **sınıfı Ekle**.  
  
2.  Sınıf adını `CustomersTableAdapterExtended`.  
  
3.  Seçin **eklemek**.  
  
4.  Kod şu şekilde doğru ad alanını ve projeniz için kısmi sınıf adı ile değiştirin:  
  
     [!code-csharp[VbRaddataTableAdapters#2](../data-tools/codesnippet/CSharp/extend-the-functionality-of-a-tableadapter_1.cs)]
     [!code-vb[VbRaddataTableAdapters#2](../data-tools/codesnippet/VisualBasic/extend-the-functionality-of-a-tableadapter_1.vb)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [TableAdapters kullanarak veri kümelerini doldurma](../data-tools/fill-datasets-by-using-tableadapters.md)