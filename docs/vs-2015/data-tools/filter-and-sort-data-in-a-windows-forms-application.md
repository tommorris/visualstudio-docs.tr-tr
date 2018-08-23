---
title: Bir Windows Forms uygulamasındaki verileri filtreleme ve sıralama | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- row states, filtering
- data views, sorting
- row version, filtering
- row states
- data views, filtering
- sorting datasets, using data views
- dataset filtering, using data views
ms.assetid: f4f100f1-776d-46dc-b2fd-5b35b98d9561
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e32e64672fc01f328643e78e572e12d57b751f39
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686423"
---
# <a name="filter-and-sort-data-in-a-windows-forms-application"></a>Bir Windows Forms uygulamasındaki verileri filtreleme ve sıralama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [bir Windows Forms uygulamasındaki verileri filtreleme ve sıralama](https://docs.microsoft.com/visualstudio/data-tools/filter-and-sort-data-in-a-windows-forms-application).  
  
  
Ayarlayarak verileri filtreleme <xref:System.Windows.Forms.BindingSource.Filter%2A> özelliğini istenen kayıtlar döndüren bir dize ifadesi.  
  
 Ayarlayarak verileri sıralamak <xref:System.Windows.Forms.BindingSource.Sort%2A> özelliğini sütun adı, sıralama yapmak istediğiniz; ekleme `DESC` azalan düzende sıralamak veya ekleme için `ASC` artan düzende sıralamak için.  
  
> [!NOTE]
>  Uygulamanızı kullanmıyorsa <xref:System.Windows.Forms.BindingSource> bileşenleri filtreleyebilirsiniz ve kullanarak verileri sıralama <xref:System.Data.DataView> nesneleri. Daha fazla bilgi için [DataViews](http://msdn.microsoft.com/library/0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b).  
  
## <a name="to-filter-data-by-using-a-bindingsource-component"></a>BindingSource bileşenini kullanarak verilere filtre uygulamak için  
  
-   Ayarlama <xref:System.Windows.Forms.BindingSource.Filter%2A> özelliğini döndürmek istediğiniz ifade. Örneğin, aşağıdaki kod ile müşteriler döndürür bir `CompanyName` "B" ile başlar:  
  
     [!code-csharp[VbRaddataDisplaying#6](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataDisplaying/CS/Form1.cs#6)]
     [!code-vb[VbRaddataDisplaying#6](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataDisplaying/VB/Form1.vb#6)]  
  
## <a name="to-sort-data-by-using-a-bindingsource-component"></a>BindingSource bileşenini kullanarak verileri sıralama  
  
-   Ayarlama <xref:System.Windows.Forms.BindingSource.Sort%2A> özelliğini sıralamak istediğiniz sütunu. Örneğin, aşağıdaki kod üzerinde müşterileri sıralar `CompanyName` azalan düzende sütun:  
  
     [!code-csharp[VbRaddataDisplaying#7](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataDisplaying/CS/Form1.cs#7)]
     [!code-vb[VbRaddataDisplaying#7](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataDisplaying/VB/Form1.vb#7)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da verilere denetimler bağlama](../data-tools/bind-controls-to-data-in-visual-studio.md)

