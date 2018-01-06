---
title: "(Windows Forms) erişim veritabanındaki verilere bağlanma | Microsoft Docs"
ms.custom: 
ms.date: 09/15/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- databases, connecting to
- databases, Access
- data [Visual Studio], connecting
- connecting to data, from Access databases
- Access databases, connecting
ms.assetid: 4159e815-d430-4ad0-a234-e4125fcbef18
caps.latest.revision: "29"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 8d55ecd52b3fa817e9a5ee199a69e3d29644346e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="connect-to-data-in-an-access-database-windows-forms"></a>(Windows Forms) erişim veritabanındaki verilere bağlanma
Visual Studio kullanarak bir Access veritabanı (.mdf dosyasının veya bir .accdb dosyası) bağlanabilir. Veri bağlantısı tanımladıktan sonra görünür **veri kaynakları** penceresi. Burada, tabloları veya görünümleri formlarınıza sürükleyebilirsiniz.   
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu yordamları kullanmak için bir Windows Forms uygulaması projesi ve bir Access veritabanı (.accdb dosyası) veya bir Access 2000-2003 veritabanı (.mdb dosyası) gerekir. Dosya türünüze karşılık gelen yordamı izleyin.  
  
## <a name="creating-the-dataset-for-an-accdb-file"></a>Veri kümesi için bir .accdb dosyası oluşturma  
 Aşağıdaki yordamı kullanarak erişim 2013, Office 365, Access 2010 veya Access 2007 oluşturulan veritabanlarını bağlanabilir.  
  
#### <a name="to-create-the-dataset"></a>Veri kümesi oluşturma  
  
1.  Veri bağlanmak istediğiniz Windows Forms uygulaması açın.  
  
2.  Üzerinde **Görünüm** menüsünde, select **diğer pencereler** > **veri kaynakları**.  
  
     ![Diğer Windows veri kaynaklarını görüntülemek](../data-tools/media/viewdatasources.png "ViewDataSources")  
  
3.  İçinde **veri kaynakları** penceresinde tıklatın **yeni veri kaynağı Ekle**.  

     **Veri kaynağı Yapılandırma Sihirbazı** açar.  
  
4.  Seçin **veritabanı** üzerinde **bir veri kaynağı türü seç** sayfasında ve ardından **sonraki**.  
  
5.  Seçin **Dataset** üzerinde **bir veritabanı modeli seçin** sayfasında ve ardından **sonraki**.  
  
6.  Üzerinde **veri bağlantınızı seçin** sayfasında, **yeni bağlantı** yeni bir veri bağlantısı yapılandırmak için.  

     **Bağlantı Ekle** iletişim kutusu açılır.  
  
7.  Seçin **değişiklik** düğmesine **veri kaynağı** metin kutusu.

     **Change Data Source** iletişim kutusu açılır.  
  
8.  Veri kaynakları listesinden seçip  **\<diğer\>**. İçinde **veri sağlayıcısı** açılan listesinde, select **OLE DB için .NET Framework veri sağlayıcısı**, ardından **Tamam**.  

9. Geri **Bağlantı Ekle** iletişim kutusunda **Microsoft Office 12.0 Access veritabanı altyapısı OLE DB sağlayıcısı** gelen **OLE DB sağlayıcısı** açılır.  
  
     ![OLE DB sağlayıcısı Microsoft Office 12.0 Access](../data-tools/media/dataoledbprovideroffice12access.png "dataOLEDBProviderOffice12Access")  

     > [!NOTE]
     >  Görmüyorsanız, **Microsoft Office 12.0 Access veritabanı altyapısı OLE DB sağlayıcısı** açılır OLE DB Sağlayıcısında yüklemeniz gerekebilir [2007 Office sistemi sürücüsü: veri bağlantısı bileşenlerinin](https://www.microsoft.com/download/confirmation.aspx?id=23734).
  
9. İçinde **sunucu veya dosya adı** metin kutusuna yolunu belirtin ve bağlanmak istediğiniz .accdb dosyasının adını ve ardından dosya **Tamam**. (Veritabanı dosyası bir kullanıcı adı ve parola varsa, seçmeden önce bunları belirtin **Tamam**.)    
  
10. Seçin **sonraki** üzerinde **veri bağlantınızı seçin** sayfası.  

     Veri dosyası, geçerli projede değil söyleyen bir iletişim kutusu alabilirsiniz. Seçin **Evet** veya **Hayır**.
  
11. Seçin **sonraki** üzerinde **bağlantı dizesi için uygulama yapılandırma dosyasını kaydetmek** sayfası.  
  
12. Genişletme **tabloları** düğümde **veritabanı nesnelerini seçin** sayfası.  
  
13. Hangi tabloları veya görünümleri, bir veri kümesini istediğiniz ve ardından seçin **son**.  
  
     Veri kümesi projenize eklenir ve tabloları ve görünümleri görüntülenmesini **veri kaynakları** penceresi.  
  
## <a name="creating-the-dataset-for-an-mdb-file"></a>Veri kümesi için bir .mdb dosyasını oluşturma  
 Çalıştırarak veri kümesi oluşturma **veri kaynağı Yapılandırma Sihirbazı**.  
  
#### <a name="to-create-the-dataset"></a>Veri kümesi oluşturma  
  
1.  Veri bağlanmak istediğiniz Windows Forms uygulaması açın.  
  
2.  Üzerinde **Görünüm** menüsünde, select **diğer pencereler** > **veri kaynakları**.  
  
     ![Diğer Windows veri kaynaklarını görüntülemek](../data-tools/media/viewdatasources.png "ViewDataSources")  
  
3.  İçinde **veri kaynakları** penceresinde tıklatın **yeni veri kaynağı Ekle**.  

     **Veri kaynağı Yapılandırma Sihirbazı** açar.
  
4.  Seçin **veritabanı** üzerinde **bir veri kaynağı türü seç** sayfasında ve ardından **sonraki**.  
  
5.  Seçin **Dataset** üzerinde **bir veritabanı modeli seçin** sayfasında ve ardından **sonraki**.  
  
6.  Üzerinde **veri bağlantınızı seçin** sayfasında, **yeni bağlantı** yeni bir veri bağlantısı yapılandırmak için.  
  
7.  Veri kaynağı değilse **Microsoft Access veritabanı dosyası (OLE DB)**seçin **değişiklik** açmak için **Change Data Source** iletişim kutusu ve select **Microsoft Veritabanı dosyası erişim**ve ardından **Tamam**.  
  
8.  İçinde **veritabanı dosya adı**, bağlanmak ve ardından istediğiniz .mdb dosyasının adını ve yolunu belirtin **Tamam**.  
  
     ![Bağlantı Access veritabanı dosyası ekleme](../data-tools/media/dataaddconnectionaccessmdb.png "dataAddConnectionAccessMDB")  
  
9. Seçin **sonraki** üzerinde **veri bağlantınızı seçin** sayfası.  
  
10. Seçin **sonraki** üzerinde **bağlantı dizesi için uygulama yapılandırma dosyasını kaydetmek** sayfası.  
  
11. Genişletme **tabloları** düğümde **veritabanı nesnelerini seçin** sayfası.  
  
12. Hangi tabloları veya görünümleri, bir veri kümesini istediğiniz ve ardından seçin **son**.  
  
     Veri kümesi projenize eklenir ve tabloları ve görünümleri görüntülenmesini **veri kaynakları** penceresi.  
  
## <a name="security"></a>Güvenlik  
 Önemli bilgileri depolamak (örneğin bir parolayı), uygulamanızın güvenliğini etkileyebilir. Windows Kimlik Doğrulaması (tümleşik güvenlik olarak da bilinir) kullanılarak bir veritabanına erişimi denetlemek için daha güvenli bir yoldur. Daha fazla bilgi için bkz: [koruma bağlantı bilgilerini](/dotnet/framework/data/adonet/protecting-connection-information).  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Yeni oluşturduğunuz veri kümesi artık kullanılabilir **veri kaynakları** penceresi. Artık aşağıdaki görevleri gerçekleştirebilirsiniz:  
  
-   Öğe seçin **veri kaynakları** penceresi ve formunuza sürükleyin (bkz [bağlamak Windows Forms denetimleri Visual Studio'da verilere](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)).  
  
-   Veri kaynağında açmak **veri kümesi Tasarımcısı** eklemek veya veri kümesi nesnelerini düzenlemek için.  
  
-   Doğrulama mantığı ekleyin <xref:System.Data.DataTable.ColumnChanging> veya <xref:System.Data.DataTable.RowChanging> olay kümesindeki veri tabloları (bkz [veri kümelerindeki verileri doğrulama](../data-tools/validate-data-in-datasets.md)).  
  
## <a name="see-also"></a>Ayrıca bkz.
[Bağlantıları ekleme](../data-tools/add-new-connections.md)
