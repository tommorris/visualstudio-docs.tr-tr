---
title: Bir Windows Forms uygulamasındaki verileri filtreleme ve sıralama
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- row states, filtering
- data views, sorting
- row version, filtering
- row states
- data views, filtering
- sorting datasets, using data views
- dataset filtering, using data views
ms.assetid: f4f100f1-776d-46dc-b2fd-5b35b98d9561
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 21ebae03dd2ba58a751a839f5e3151654faa39e0
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36757601"
---
# <a name="filter-and-sort-data-in-a-windows-forms-application"></a>Bir Windows Forms uygulamasındaki verileri filtreleme ve sıralama
Ayarlayarak verilere filtre <xref:System.Windows.Forms.BindingSource.Filter%2A> özelliği istenen kayıtları döndüren bir dize ifadesi.

 Ayarlayarak verileri sıralamak <xref:System.Windows.Forms.BindingSource.Sort%2A> sıralamak istediğiniz; append sütun adı özelliğine `DESC` azalan sırada sıralar veya eklemek için `ASC` azalan sırada sıralayın.

> [!NOTE]
>  Uygulamanızı kullanmıyorsa <xref:System.Windows.Forms.BindingSource> bileşenleri filtreleyebilir ve verileri kullanarak sıralama <xref:System.Data.DataView> nesneleri. Daha fazla bilgi için bkz: [DataView](/dotnet/framework/data/adonet/dataset-datatable-dataview/dataviews).

## <a name="to-filter-data-by-using-a-bindingsource-component"></a>BindingSource bileşenini kullanarak verileri filtrelemek için

-   Ayarlama <xref:System.Windows.Forms.BindingSource.Filter%2A> döndürmek istediğiniz ifade özelliğine. Örneğin, aşağıdaki kod müşterilerle döndürür bir `CompanyName` "B" ile başlar:

     [!code-csharp[VbRaddataDisplaying#6](../data-tools/codesnippet/CSharp/filter-and-sort-data-in-a-windows-forms-application_1.cs)]
     [!code-vb[VbRaddataDisplaying#6](../data-tools/codesnippet/VisualBasic/filter-and-sort-data-in-a-windows-forms-application_1.vb)]

## <a name="to-sort-data-by-using-a-bindingsource-component"></a>BindingSource bileşenini kullanarak verileri sıralama

-   Ayarlama <xref:System.Windows.Forms.BindingSource.Sort%2A> sıralamak istediğiniz sütunu özelliğine. Örneğin, aşağıdaki kodu müşteriler sıralandığı `CompanyName` sütununu azalan düzende:

     [!code-csharp[VbRaddataDisplaying#7](../data-tools/codesnippet/CSharp/filter-and-sort-data-in-a-windows-forms-application_2.cs)]
     [!code-vb[VbRaddataDisplaying#7](../data-tools/codesnippet/VisualBasic/filter-and-sort-data-in-a-windows-forms-application_2.vb)]

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da verilere denetimler bağlama](../data-tools/bind-controls-to-data-in-visual-studio.md)