---
title: SQL Server örnek veritabanları yükleme | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 38840167-c3f8-4cb3-8d15-8af04a0a20a1
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8a7e82091d93a14e53eed4ee67da086ee1a3c892
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692066"
---
# <a name="install-sql-server-sample-databases"></a>SQL Server örnek veritabanları yükleme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [yüklemek SQL Server örnek veritabanları](https://docs.microsoft.com/visualstudio/data-tools/install-sql-server-sample-databases).  
  
  
Örnek veritabanları, SQL ve LINQ sorguları, veri bağlama, Entity Framework modelleme ve benzeri ile denemek için kullanışlıdır.  Her veritabanı ürünün kendi örnek veritabanları vardır. Northwind ve AdventureWorks iki yaygın olarak kullanılan SQL Server örnek veritabanlarıdır.  
  
 **AdventureWorks** sağlanan SQL Server ürünleri için geçerli örnek veritabanı. Bir .mdf dosyasından olarak indirebilirsiniz [Codeplex AdventureWorks sayfasında](http://msftdbprodsamples.codeplex.com/). Kullanılabilir veritabanı normal ve basit (LT) sürümleri burada. Çoğu senaryo için daha az karmaşık olduğundan LT sürümü tercih edilir.  
  
 **Northwind** yıllardır kullanılan oldukça basit bir SQL Server veritabanıdır. .bak dosyası olarak indirebilirsiniz [Northwind veritabanı CodePlex sayfasında](https://northwinddatabase.codeplex.com/). İzin sorunları önlemek için kullanıcı klasörünüzün altında olmayan yeni bir klasöre dosyanın sıkıştırmasını açın.  
  
#### <a name="to-restore-a-database-from-a-bak-file-in-visual-studio"></a>Visual Studio .bak dosyasından bir veritabanını geri yüklemek için  
  
1.  Bir Microsoft SQL Server veritabanını yedeklediğinizde, .bak dosyasının sonuç olur. Bir veritabanı dosyası olarak kullanılabilir dosya yeniden .bak yapmak için bu olmalıdır *geri*. Ana menüden**görünümü** > **SQL Server Nesne Gezgini**. Görmüyorsanız, yüklemeniz gerekebilir. Git **Denetim Masası** > **programlar ve Özellikler**, Microsoft Visual Studio 2015'i bulun ve tıklayın **değişiklik** düğmesi. Yüklü bileşenlerin listesini yükleyici penceresinde göründüğünde seçin **SQL Server Nesne Gezgini**onay kutusunu işaretleyin ve ardından yükleme işlemine devam edin.  
  
2.  SQL Server nesne Gezgini'nde, tüm SQL Server Veritabanı Altyapısı'nı (örneğin, localdb) sağ tıklayın ve seçin**yeni sorgu**.  
  
     ![SQL Server Nesne Gezgini yeni sorgu](../data-tools/media/raddata-sql-server-object-explorer-new-query.png "raddata SQL Server Nesne Gezgini yeni sorgu")  
  
3.  İlk olarak, veritabanı ve günlük dosyaları .bak dosyasının içindeki mantıksal adları gerekir. Buna ulaşmak için bu sorguyu SQL sorgu Düzenleyicisi'ne girin ve yeşil seçip **çalıştırma** pencerenin üstünde düğme. Dosya yolu, gerekiyorsa .bak dosyasına işaret edecek şekilde değiştirin.  
  
    ```  
    RESTORE FILELISTONLY  
    FROM DISK = 'C:\nw\northwind.bak'  
    GO  
    ```  
  
     Sonuçları penceresinde görüntülenen mantıksal adlarını yazın.  İçin Northwind veritabanı, iki mantıksal Northwind ve Northwind_log adlarıdır.  
  
4.  Şimdi bir veritabanı oluşturmak için bu sorguyu çalıştırın. Kendi kaynak ve hedef yolunu, mantıksal veritabanı adları ve Northwind fiziksel dosya adlarını uygun şekilde değiştirin. .Mdf ve .ldf dosyası uzantıları tutun.  
  
    ```  
    RESTORE DATABASE Northwind  
    FROM DISK = 'c:\nw\northwind.bak'  
    WITH MOVE 'Northwind' TO 'c:\nw\northwind.mdf',  
    MOVE 'Northwind_log' TO 'c:\nw\northwind.ldf'  
    ```  
  
5.  SQL Server nesne Gezgini'nde sağ **veritabanları** düğüm ve Northwind veritabanı düğümü görmelisiniz. Aksi takdirde, daha sonra veritabanları sağ tıklatın ve **yeni veritabanı Ekle**. Ad ve yeni oluşturduğunuz .mdf dosyasının konumunu girin.  
  
6.  Veritabanı artık Visual Studio'da veri kaynağı olarak kullanmak hazırdır.  
  
#### <a name="to-restore-a-database-from-a-bak-file-in-sql-server-management-studio"></a>SQL Server Management Studio .bak dosyasından bir veritabanını geri yüklemek için  
  
1.  SQL Server Management Studio'yu indirme sitesinden indirin.  
  
2.  Ssms'de **Nesne Gezgini** penceresinde sağ **veritabanları** düğümünü**Restore Database**ve .bak dosyasının konumunu belirtin.  
  
     ![SSMS Restore Database](../data-tools/media/raddata-ssms-restore-database.png "raddata SSMS veritabanını geri yükle")

