---
title: Bir veri kümesini doldururken kısıtlamaları kapatma Aç
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- DataRow.BeginEdit
- DataRow.EndEdit
- DataRow.CancelEdit
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- updating datasets, constraints
- constraints [Visual Basic], datasets
- datasets [Visual Basic], constraints
- constraints [Visual Basic], suspending during dataset update
ms.assetid: 553f7d0c-2faa-4c17-b226-dd02855bf1dc
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 40e19e7595c91429a8c52ddcdd01808a84197cc4
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="turn-off-constraints-while-filling-a-dataset"></a>Bir veri kümesini doldururken kısıtlamaları kapatma Aç

Bir veri kümesi (örneğin, yabancı anahtar kısıtlamaları) kısıtlamalarını içeriyorsa, bunlar dataset karşı gerçekleştirilen işlemleri {ilgili hatalar yükseltebilirsiniz. Örneğin, alt kayıtları yüklemeden önce yükleme üst kayıtlar bir kısıtlamayı ihlal ediyor ve hataya neden ilgili. Bir alt kayıt yük hemen kısıtlaması ilgili üst kayıt için denetler ve hata başlatır.

Geçici kısıtlaması askıya izin vermek için bir mekanizma olsaydı, alt tablosuna bir kayıt yüklemeye çalıştığınız her zaman bir hata oluşturdu. Bir veri kümesindeki tüm kısıtlamalar askıya almak için başka bir yolu <xref:System.Data.DataRow.BeginEdit%2A>, ve <xref:System.Data.DataRow.EndEdit%2A> özellikleri.

> [!NOTE]
> Doğrulama olayları (örneğin, <xref:System.Data.DataTable.ColumnChanging> ve<xref:System.Data.DataTable.RowChanging>) kısıtlamaları devre dışı bırakıldığında oluşturulmaz.

## <a name="to-suspend-update-constraints-programmatically"></a>Güncelleştirme kısıtlamaları programlı olarak askıya almak için

-   Aşağıdaki örnek, bir veri kümesinde denetleme kısıtlaması geçici olarak kapatmak gösterilmektedir:

     [!code-csharp[VbRaddataEditing#10](../data-tools/codesnippet/CSharp/turn-off-constraints-while-filling-a-dataset_1.cs)]
     [!code-vb[VbRaddataEditing#10](../data-tools/codesnippet/VisualBasic/turn-off-constraints-while-filling-a-dataset_1.vb)]

## <a name="to-suspend-update-constraints-using-the-dataset-designer"></a>Veri kümesi Tasarımcısı'nı kullanarak güncelleştirme kısıtlamaları askıya almak için

1.  Bir veri kümesini açma **veri kümesi Tasarımcısı**. Daha fazla bilgi için bkz: [izlenecek yol: veri kümesi tasarımcısında bir veri kümesi oluşturma](walkthrough-creating-a-dataset-with-the-dataset-designer.md).

2.  İçinde **özellikleri** penceresindeki ayarlayın <xref:System.Data.DataSet.EnforceConstraints%2A> özelliğine `false`.

## <a name="see-also"></a>Ayrıca Bkz.

- [TableAdapters kullanarak veri kümelerini doldurma](../data-tools/fill-datasets-by-using-tableadapters.md)
- [Veri kümelerindeki ilişkiler](../data-tools/relationships-in-datasets.md)