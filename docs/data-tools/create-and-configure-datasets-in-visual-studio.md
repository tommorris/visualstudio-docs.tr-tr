---
title: "Oluşturma ve Visual Studio'da veri kümelerini yapılandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- typed datasets, creating
- datasets, creating
- datasets, configuring
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: da81d141e453e0106d329565338f7893b4fad758
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="create-and-configure-datasets-in-visual-studio"></a>Oluşturma ve Visual Studio'da veri kümelerini yapılandırma

A *dataset* bellekte bir veritabanındaki verileri depolamak ve etkinleştirmek için değişiklik izleme destekleyen nesneleri kümesi oluşturma, okuma, güncelleştirme ve bu verileri her zaman veritabanına bağlanması gerek kalmadan (CRUD) işlemleridir silme. Veri kümeleri basit için tasarlanmış *forms veriler üzerinde* iş uygulamaları. Yeni uygulamalar için depolamak ve bellekte veri modeli için Entity Framework kullanarak göz önünde bulundurun. Veri kümeleriyle çalışmak için veritabanı kavramlarını temel bilgiye sahip.

Yazılmış bir oluşturduğunuz <xref:System.Data.DataSet> Visual Studio'da sınıfı kullanarak tasarım zamanında **veri kaynağı Yapılandırma Sihirbazı**. Veri kümeleri program aracılığıyla oluşturma hakkında daha fazla bilgi için bkz: [bir veri kümesi (ADO.NET) oluşturma](/dotnet/framework/data/adonet/dataset-datatable-dataview/creating-a-dataset).

## <a name="create-a-new-dataset-by-using-the-data-source-configuration-wizard"></a>Veri Kaynağı Yapılandırma Sihirbazı'nı kullanarak yeni bir veri kümesi oluşturma

1.  Üzerinde **proje** menüsünde tıklatın **yeni veri kaynağı Ekle** başlatmak için **veri kaynağı Yapılandırma Sihirbazı**.

2.  İçin bağlanırsınız veri kaynağı türünü seçin.

     ![Veri Kaynağı Yapılandırma Sihirbazı'nı](../data-tools/media/data-source-configuration-wizard.png "veri kaynağı Yapılandırma Sihirbazı")

3.  Veritabanları için veritabanı veya Veri kümenizi veri kaynağının veritabanlarını seçin.

     ![Veri kaynağı bağlantısı seçin](../data-tools/media/data-source-choose-a-connection.png "veri kaynağı bağlantısı seçin")

4.  Tabloları (veya tek tek sütun) saklı yordamları, işlevleri ve veritabanından veri kümesini temsil etmek istediğiniz görünümleri seçin.

     ![Veritabanı nesneleri seçin](../data-tools/media/raddata-chose-objects.png "raddata seçtiğiniz nesneleri")

5.  **Son**'a tıklayın.

6.  Veri kümesi bir düğüm olarak görünür **Çözüm Gezgini**:

     ![Çözüm Gezgini'nde DataSet](../data-tools/media/dataset-in-solution-explorer.png "Çözüm Gezgini'nde veri kümesi")

     Bu düğümünü tıklatın ve veri kümesi görünür **veri kümesi Tasarımcısı**. Veri kümesi her tabloda altındaki temsil edilen bir ilişkili TableAdapter nesnesi olduğuna dikkat edin. Tablo bağdaştırıcısı DataSet'i ve isteğe bağlı olarak veritabanına komutlarını göndermek için kullanılır.

     ![Veri kümesi Tasarımcısı](../data-tools/media/dataset-designer.png "veri kümesi Tasarımcısı")

7.  Tabloları bağlanma ilişkisi satırları tablo ilişkileri veritabanında tanımlanan temsil eder. Varsayılan olarak, bir veritabanındaki yabancı anahtar kısıtlamaları yalnızca bir ilişki güncelleştirme ile temsil edilir ve Yok'a kuralları silin. Genellikle, istediğiniz olmasıdır. Ancak, ortaya çıkarmak için satırları tıklayabilirsiniz **ilişkisi** hiyerarşik güncelleştirmeleri davranışını değiştirebileceğiniz iletişim. Daha fazla bilgi için bkz: [kümelerindeki ilişkiler](../data-tools/relationships-in-datasets.md) ve [hiyerarşik güncelleştirme](../data-tools/hierarchical-update.md).

     ![Veri kümesi ilişkisi iletişim](../data-tools/media/raddata-relation-dialog.png "raddata ilişkisi iletişim")

8.  Tablo, tablo bağdaştırıcısı veya bir tablodaki sütun adı, özelliklerini görmek için tıklatın **özellikleri** penceresi. Bazı değerleri burada değiştirebilirsiniz. Yalnızca kaynak veritabanı veri kümesi değiştiriyorsunuz unutmayın.

     ![Veri kümesi sütun özellikleri](../data-tools/media/dataset-column-properties.png "DataSet sütun özellikleri")

9. Yeni Tablo veya tablo bağdaştırıcıları kümesine eklemek veya var olan tablo bağdaştırıcıları için yeni sorgular eklemek veya bu öğelerden sürükleyerek tablolar arasındaki yeni ilişkileri belirtin **araç** sekmesi. Bu sekme ne zaman görünür **veri kümesi Tasarımcısı** odaklanılan.

     ![Veri kümesi araç](../data-tools/media/raddata-dataset-toolbox.png "raddata Dataset araç kutusu")

10. Ardından, büyük olasılıkla veri kümesini verilerle doldurmak nasıl belirtmek isteyebilirsiniz. Bunun için kullandığınız **TableAdapter Yapılandırma Sihirbazı'nı**. Daha fazla bilgi için bkz: [TableAdapters kullanarak veri kümelerini doldurma](../data-tools/fill-datasets-by-using-tableadapters.md).

## <a name="add-a-database-table-or-other-object-to-an-existing-dataset"></a>Bir veritabanı tablosu veya başka bir nesne var olan bir veri kümesine ekleme

Bu yordamda, bir tablo ilk veri kümesi oluşturmak için kullanılan aynı veritabanı eklemek gösterilmiştir.

1.  Veri kümesi düğümü tıklatın **Çözüm Gezgini** veri kümesi Tasarımcısı odaklanmak için.

2.  Tıklatın **veri kaynakları** sekmesinde Visual Studio'nun sol kenar boşluğunda veya girin `Data Sources` içinde **hızlı başlatma**.

3.  Veri kümesi düğümünü sağ tıklatın ve seçin **veri kaynağı Yapılandırma Sihirbazı ile**.

     ![Veri kaynağı bağlam menüsü](../data-tools/media/data-source-context-menu.png "veri kaynağı bağlam menüsü")

4.  Sihirbaz, hangi ek tablolar veya saklı yordam veya kümesine eklemek için diğer veritabanı nesnesi belirtmek için kullanın.

## <a name="add-a-stand-alone-data-table-to-a-dataset"></a>Tek başına veri tablosu ekleme

1.  Bir veri kümesini açma **veri kümesi Tasarımcısı**.

2.  Sürükleme bir <xref:System.Data.DataTable> sınıfıyla **DataSet** sekmesinde **araç** üzerine **veri kümesi Tasarımcısı**.

3.  Veri tablosu tanımlamak için sütunları ekleyin. Tabloyu sağ tıklatın ve seçin **Ekle > sütun**. Kullanım **özellikleri** gerekirse sütun ve bir anahtar veri türünü ayarlamak için penceresi.

4.  Tek başına tabloları uygulama için gereksinim `Fill` mantığı tek başına tabloları, böylece verilerle doldurmak için. Tek başına veri tabloları doldurma hakkında daha fazla bilgi için bkz: [DataAdapter kümesinden doldurma](/dotnet/framework/data/adonet/populating-a-dataset-from-a-dataadapter).

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio'da veri kümesi araçları](../data-tools/dataset-tools-in-visual-studio.md)