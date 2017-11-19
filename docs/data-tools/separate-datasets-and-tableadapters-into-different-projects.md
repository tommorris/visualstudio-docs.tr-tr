---
title: "Veri kümeleri ve TableAdapters öğelerini farklı projelere ayırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TableAdapters, n-tier applications
- n-tier applications, separating Datasets and TableAdapters
ms.assetid: f66a3940-6227-46af-a930-9177f425f4fd
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 4ae00a8b3a51b088100d4a27893dd100d5d7ba71
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2017
---
# <a name="separate-datasets-and-tableadapters-into-different-projects"></a>Ayrı veri kümeleri ve TableAdapters öğelerini farklı projelere içine
Yazılan veri kümeleri Gelişmiş böylece [TableAdapters](create-and-configure-tableadapters.md) ve veri kümesi sınıfları ayrı projelere oluşturulabilir. Bu, hızlı bir şekilde n katmanlı veri uygulamalarını oluşturmak ve uygulama katmanları ayrı sağlar.  
  
Aşağıdaki yordamı kullanarak işlemi açıklanır **veri kümesi Tasarımcısı** oluşturulan TableAdapter kod içeren projeden ayrı projesine dataset kodu oluşturmak için.  
  
## <a name="separate-datasets-and-tableadapters"></a>Ayrı veri kümeleri ve TableAdapters öğelerini  
TableAdapter koddan dataset kod ayırdığınızda, veri kümesi kodu içeren projeye geçerli çözümde bulunması gerekir. Bu proje geçerli çözümde bulunmuyorsa, kullanılabilir olmayacaktır **DataSet projesi** listesinde **özellikleri** penceresi.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
#### <a name="to-separate-the-dataset-into-a-different-project"></a>Veri kümesi farklı bir projeye ayırmak için  
  
1.  Veri kümesi (.xsd dosyası) içeren bir çözüm açın.  
  
    > [!NOTE]
    >  Çözüm dataset kodunuzu ayırmak istediğiniz proje içermiyorsa projesi oluşturduğunuzda veya mevcut bir proje ekleyin.  
  
2.  İçinde bir türü belirtilmiş veri kümesi dosyasını (.xsd dosyası) çift **Çözüm Gezgini** kümesinde açmak için **veri kümesi Tasarımcısı**.  
  
3.  Boş alanı seçin **veri kümesi Tasarımcısı**.  
  
4.  İçinde **özellikleri** penceresinde bulun **DataSet projesi** düğümü.  
  
5.  İçinde **DataSet projesi** listesinde, veri kümesi kodu oluşturmak istediğiniz projesinin adını seçin.  
  
     Veri kümesi kodu oluşturmak istediğiniz proje seçtikten sonra **veri kümesi dosyası** özelliği, bir varsayılan dosya adıyla doldurulur. Gerekirse, bu adı değiştirebilirsiniz. Ayrıca, belirli bir dizine veri kümesi kodunu oluşturmak istiyorsanız, ayarlayabileceğiniz **proje klasörünü** özelliği için bir klasör adı.  
  
    > [!NOTE]
    >  Ne zaman, ayrı veri kümeleri ve TableAdapters öğelerini (ayarlayarak **DataSet projesi** özelliği), projedeki mevcut kısmi veri kümesi sınıflarını olmaz taşınabilir otomatik olarak. Var olan kısmi dataset sınıfları el ile dataset projesi taşınması gerekir.  
  
6.  Veri kümesi kaydedin.  
  
     Seçili projeye oluşturulan veri kümesi kodda **DataSet projesi** özelliği ve **TableAdapter** kodu geçerli projede oluşturulur.  
  
TableAdapter kod ve veri kümesi ayrı sonra varsayılan olarak, her proje ayrık sınıf dosyasında sonucudur. Bir dosyanın özgün proje sahip DatasetName.Designer.vb (veya DatasetName.Designer.cs) olarak adlandırılan, TableAdapter kodunu içerir. İçinde belirtilen proje **Dataset projesi** özelliğine sahip bir dosya DatasetName.DataSet.Designer.vb (veya DatasetName.DataSet.Designer.cs) adlı, veri kümesi kodunu içerir.  
  
> [!NOTE]
>  Oluşturulan sınıf dosyayı görüntülemek için veri kümesi veya TableAdapter projesini seçin. Ardından **Çözüm Gezgini**seçin **tüm dosyaları göster**.  
  
## <a name="see-also"></a>Ayrıca bkz.
[N katmanlı veri uygulamalarına genel bakış](../data-tools/n-tier-data-applications-overview.md)   
[İzlenecek yol: N katmanlı veri uygulaması oluşturma](../data-tools/walkthrough-creating-an-n-tier-data-application.md)   
[Hiyerarşik güncelleştirme](../data-tools/hierarchical-update.md)   
[Visual Studio'da veri erişimi](../data-tools/accessing-data-in-visual-studio.md)   
[ADO.NET](/dotnet/framework/data/adonet/index)