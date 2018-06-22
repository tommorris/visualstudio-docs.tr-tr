---
title: (Windows Forms) erişim veritabanındaki verilere bağlanma
ms.date: 09/15/2017
ms.topic: conceptual
helpviewer_keywords:
- databases, connecting to
- databases, Access
- data [Visual Studio], connecting
- connecting to data, from Access databases
- Access databases, connecting
ms.assetid: 4159e815-d430-4ad0-a234-e4125fcbef18
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: f1d0b5d2d0391d401394929e16d5bfc97aa6d555
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/20/2018
ms.locfileid: "36282645"
---
# <a name="connect-to-data-in-an-access-database-windows-forms"></a>(Windows Forms) erişim veritabanındaki verilere bağlanma
Bir veritabanına bağlanabilir (ya da bir *.mdf* dosya veya bir *.accdb* dosyası) Visual Studio kullanarak. Veri bağlantısı tanımladıktan sonra görünür **veri kaynakları** penceresi. Burada, tabloları veya görünümleri formlarınıza sürükleyebilirsiniz.

## <a name="prerequisites"></a>Önkoşullar
 Bu yordamları kullanmak için bir Windows Forms uygulaması projesi ve bir Access veritabanı gerekir (*.accdb* dosya) veya bir Access 2000-2003 veritabanı (*.mdb* dosyası). Dosya türünüze karşılık gelen yordamı izleyin.

## <a name="creating-the-dataset-for-an-accdb-file"></a>Veri kümesi için bir .accdb dosyası oluşturma
 Aşağıdaki yordamı kullanarak erişim 2013, Office 365, Access 2010 veya Access 2007 oluşturulan veritabanlarını bağlanabilir.

#### <a name="to-create-the-dataset"></a>Veri kümesi oluşturma

1.  Veri bağlanmak istediğiniz Windows Forms uygulaması açın.

2.  Üzerinde **Görünüm** menüsünde, select **diğer pencereler** > **veri kaynakları**.

     ![Diğer Windows veri kaynaklarını görüntülemek](../data-tools/media/viewdatasources.png)

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

     ![OLE DB sağlayıcısı Microsoft Office 12.0 Access](../data-tools/media/dataoledbprovideroffice12access.png)

     > [!NOTE]
     >  Görmüyorsanız, **Microsoft Office 12.0 Access veritabanı altyapısı OLE DB sağlayıcısı** açılır OLE DB Sağlayıcısında yüklemeniz gerekebilir [2007 Office sistemi sürücüsü: veri bağlantısı bileşenlerinin](https://www.microsoft.com/download/confirmation.aspx?id=23734).

9. İçinde **sunucu veya dosya adı** metin kutusuna yolunu belirtin ve dosya adını *.accdb* bağlanın ve ardından istediğiniz dosyasını **Tamam**. (Veritabanı dosyası bir kullanıcı adı ve parola varsa, seçmeden önce bunları belirtin **Tamam**.)

10. Seçin **sonraki** üzerinde **veri bağlantınızı seçin** sayfası.

     Veri dosyası, geçerli projede değil söyleyen bir iletişim kutusu alabilirsiniz. Seçin **Evet** veya **Hayır**.

11. Seçin **sonraki** üzerinde **bağlantı dizesi için uygulama yapılandırma dosyasını kaydetmek** sayfası.

12. Genişletme **tabloları** düğümde **veritabanı nesnelerini seçin** sayfası.

13. Hangi tabloları veya görünümleri, bir veri kümesini istediğiniz ve ardından seçin **son**.

     Veri kümesi projenize eklenir ve tabloları ve görünümleri görüntülenmesini **veri kaynakları** penceresi.

## <a name="create-the-dataset-for-an-mdb-file"></a>Veri kümesi için bir .mdb dosyasını oluşturma
 Çalıştırarak veri kümesi oluşturma **veri kaynağı Yapılandırma Sihirbazı**.

#### <a name="to-create-the-dataset"></a>Veri kümesi oluşturma

1.  Veri bağlanmak istediğiniz Windows Forms uygulaması açın.

2.  Üzerinde **Görünüm** menüsünde, select **diğer pencereler** > **veri kaynakları**.

     ![Diğer Windows veri kaynaklarını görüntülemek](../data-tools/media/viewdatasources.png)

3.  İçinde **veri kaynakları** penceresinde tıklatın **yeni veri kaynağı Ekle**.

     **Veri kaynağı Yapılandırma Sihirbazı** açar.

4.  Seçin **veritabanı** üzerinde **bir veri kaynağı türü seç** sayfasında ve ardından **sonraki**.

5.  Seçin **Dataset** üzerinde **bir veritabanı modeli seçin** sayfasında ve ardından **sonraki**.

6.  Üzerinde **veri bağlantınızı seçin** sayfasında, **yeni bağlantı** yeni bir veri bağlantısı yapılandırmak için.

7.  Veri kaynağı değilse **Microsoft Access veritabanı dosyası (OLE DB)** seçin **değişiklik** açmak için **Change Data Source** iletişim kutusu ve select **Microsoft Veritabanı dosyası erişim**ve ardından **Tamam**.

8.  İçinde **veritabanı dosya adı**, adını ve yolunu belirtin *.mdb* bağlanın ve ardından istediğiniz dosyasını **Tamam**.

     ![Bağlantı Access veritabanı dosyası ekleme](../data-tools/media/dataaddconnectionaccessmdb.png)

9. Seçin **sonraki** üzerinde **veri bağlantınızı seçin** sayfası.

10. Seçin **sonraki** üzerinde **bağlantı dizesi için uygulama yapılandırma dosyasını kaydetmek** sayfası.

11. Genişletme **tabloları** düğümde **veritabanı nesnelerini seçin** sayfası.

12. Hangi tabloları veya görünümleri, bir veri kümesini istediğiniz ve ardından seçin **son**.

     Veri kümesi projenize eklenir ve tabloları ve görünümleri görüntülenmesini **veri kaynakları** penceresi.

## <a name="security"></a>Güvenlik
 Önemli bilgileri depolamak (örneğin bir parolayı), uygulamanızın güvenliğini etkileyebilir. Windows Kimlik Doğrulaması (tümleşik güvenlik olarak da bilinir) kullanılarak bir veritabanına erişimi denetlemek için daha güvenli bir yoldur. Daha fazla bilgi için bkz: [bağlantı bilgileri koruma](/dotnet/framework/data/adonet/protecting-connection-information).

## <a name="next-steps"></a>Sonraki adımlar
 Yeni oluşturduğunuz veri kümesi artık kullanılabilir **veri kaynakları** penceresi. Artık aşağıdaki görevleri gerçekleştirebilirsiniz:

-   Öğe seçin **veri kaynakları** penceresi ve formunuza sürükleyin (bkz [bağlamak Windows Forms denetimleri Visual Studio'da verilere](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)).

-   Veri kaynağında açmak **veri kümesi Tasarımcısı** eklemek veya veri kümesi nesnelerini düzenlemek için.

-   Doğrulama mantığı ekleyin <xref:System.Data.DataTable.ColumnChanging> veya <xref:System.Data.DataTable.RowChanging> olay kümesindeki veri tabloları (bkz [veri kümelerindeki verileri doğrulama](../data-tools/validate-data-in-datasets.md)).

## <a name="see-also"></a>Ayrıca bkz.

- [Bağlantı ekleme](../data-tools/add-new-connections.md)