---
title: Bir veri kümesini doldururken kısıtlamaları kapatma kapatma | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- DataRow.BeginEdit
- DataRow.EndEdit
- DataRow.CancelEdit
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- updating datasets, constraints
- constraints [Visual Basic], datasets
- datasets [Visual Basic], constraints
- constraints [Visual Basic], suspending during dataset update
ms.assetid: 553f7d0c-2faa-4c17-b226-dd02855bf1dc
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4b14830b7ed4922b4e383ef245c0366c184b606e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684274"
---
# <a name="turn-off-constraints-while-filling-a-dataset"></a>Bir veri kümesini doldururken kısıtlamaları kapatma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [bir veri kümesini doldururken kısıtlamaları kapatma kapatma](https://docs.microsoft.com/visualstudio/data-tools/turn-off-constraints-while-filling-a-dataset).  
  
  
Bir veri kümesi (örneğin, yabancı anahtar kısıtlamaları) kısıtlamaları içeriyorsa, theycan veri kümesinde gerçekleştirilen işlemleri sırayla ilgili hataları yükseltin. Örneğin, alt kayıtları loadingrelated üst kayıtlar önce yükleme bir kısıtlamayı ihlal ve hataya neden. Alt kayıt yük hemen sonra kısıtlaması ilgili üst kaydını denetler ve bir hata oluşturur.  
  
 Geçici kısıtlaması askıya alma izin vermek için bir mekanizma bulunmadığından varsa, alt tabloya bir kayıt yüklemeye çalıştığınız her zaman bir hata oluşturulması. Bir veri kümesindeki tüm kısıtlamalar askıya almak için başka bir yöntem, <xref:System.Data.DataRow.BeginEdit%2A>, ve <xref:System.Data.DataRow.EndEdit%2A> özellikleri.  
  
> [!NOTE]
>  Doğrulama olayları (örneğin, <xref:System.Data.DataTable.ColumnChanging> ve<xref:System.Data.DataTable.RowChanging>) kısıtlamaları devre dışı bırakıldığında oluşturulmaz.  
  
### <a name="to-suspend-update-constraints-programmatically"></a>Güncelleştirme kısıtlamaları programlı olarak askıya alma  
  
-   Aşağıdaki örnek, bir veri kümesinde denetleme kısıtlaması geçici olarak kapatmak gösterilmektedir:  
  
     [!code-csharp[VbRaddataEditing#10](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#10)]
     [!code-vb[VbRaddataEditing#10](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#10)]  
  
### <a name="to-suspend-update-constraints-using-the-dataset-designer"></a>Veri kümesi Tasarımcısı'nı kullanarak güncelleştirme kısıtlamaları askıya alma  
  
1.  Kümenizde açın [oluşturma ve yazılan veri kümelerini düzenleme](../data-tools/creating-and-editing-typed-datasets.md). Daha fazla bilgi için [nasıl yapılır: bir veri kümesini veri kümesi Tasarımcısı'nda açma](http://msdn.microsoft.com/library/36fc266f-365b-42cb-aebb-c993dc2c47c3).  
  
2.  İçinde **özellikleri** penceresinde <xref:System.Data.DataSet.EnforceConstraints%2A> özelliğini `false`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [TableAdapters'ı kullanarak veri kümelerini doldurma](../data-tools/fill-datasets-by-using-tableadapters.md)   
 [Veri kümelerindeki ilişkiler](../data-tools/relationships-in-datasets.md)

