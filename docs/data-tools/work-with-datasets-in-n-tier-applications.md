---
title: N katmanlı uygulamalarda veri kümeleriyle çalışma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- datasets [Visual Basic], n-tier applications
- multi-tier database applications
- DataSet project [VS n-tier applications]
- distributed applications [VS n-tier applications]
- data [Visual Basic], n-tier applications
- TableAdapters, n-tier applications
- n-tier applications
- tiers, n-tier applications
- typed datasets, n-tier applications
- multiple tier applications
ms.assetid: f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 0858a99dfb56dcdfabb66479788097e4fe272fe9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="work-with-datasets-in-n-tier-applications"></a>N katmanlı uygulamalarda veri kümeleriyle çalışma
*N katmanlı veri uygulamalarını* birden çok mantıksal katmanlara ayrılır veri merkezli uygulamalar (veya *katmanları*). Diğer bir deyişle, n katmanlı veri uygulaması veri erişim katmanı, iş mantığı katmanından ve sunu katmanı her kendi projesinde ile birden çok projelerine ayrılmış bir uygulamadır. Daha fazla bilgi için bkz: [N katmanlı veri uygulamalarına genel bakış](../data-tools/n-tier-data-applications-overview.md).  
  
Yazılan veri kümeleri, böylece TableAdapters ve veri kümesi sınıfları ayrık projelere oluşturulabilir geliştirilmiştir. Bu hızlı bir şekilde uygulama katmanları ayırın ve n katmanlı veri uygulamaları oluşturma olanağı sağlar.  
  
Yazılan veri kümeleri N katmanlı desteği n katmanlı tasarım uygulama mimarisinin yinelemeli bir geliştirme sağlar. Ayrıca el ile birden çok projeye kodu ayıran gereksinimini ortadan kaldırır. Veri katmanı kullanarak tasarlama çıkışı Başlat **veri kümesi Tasarımcısı**. N katmanlı bir tasarım için uygulama mimarisi almaya hazır olduğunuzda, ayarlamak **DataSet projesi** özelliği ayrı bir projeye dataset sınıfı oluşturmak için bir veri kümesi.  
  
## <a name="reference"></a>Başvuru  
<xref:System.Data.DataSet>  
<xref:System.Data.TypedTableBase%601>  
  
## <a name="see-also"></a>Ayrıca bkz.
[N katmanlı veri uygulamalarına genel bakış](../data-tools/n-tier-data-applications-overview.md)  
[İzlenecek yol: N katmanlı veri uygulaması oluşturma](../data-tools/walkthrough-creating-an-n-tier-data-application.md)  
[N katmanlı uygulamalarda TableAdapter’lara kod ekleme](../data-tools/add-code-to-tableadapters-in-n-tier-applications.md)  
[N katmanlı uygulamalarda veri kümelerine kod ekleme](../data-tools/add-code-to-datasets-in-n-tier-applications.md)  
[N Katmanlı bir veri kümesine doğrulama ekleme](../data-tools/add-validation-to-an-n-tier-dataset.md)  
[Veri kümeleri ile TableAdapter’ları farklı projelere ayırma](../data-tools/separate-datasets-and-tableadapters-into-different-projects.md)  
[Hiyerarşik güncelleştirme](../data-tools/hierarchical-update.md)  
[Visual Studio'da veri kümesi araçları](../data-tools/dataset-tools-in-visual-studio.md)  
[Visual Studio'da verilere erişime](../data-tools/accessing-data-in-visual-studio.md)  
[Oluşturma ve TableAdapters öğelerini yapılandırma](../data-tools/create-and-configure-tableadapters.md)  
[LINQ to SQL ile N Katmanı ve Uzak Uygulamalar](/dotnet/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql)