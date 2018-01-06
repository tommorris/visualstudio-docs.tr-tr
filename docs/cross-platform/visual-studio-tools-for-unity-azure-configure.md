---
title: "Azure izlenecek yapılandırma Unity için Visual Studio Araçları | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: BAE62C27-CA7A-4466-8738-3DB880221CE1
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- azure
- unity
ms.openlocfilehash: 25424ea06c01224bb1b35f783be82a857b991adf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="configure-easy-tables-in-azure"></a>Azure'da kolay tablolarını yapılandırmak

Kolay tablolardır bir özelliği olan [Azure Mobile Apps](https://azure.microsoft.com/services/app-service/mobile/) izin Kurulum ve yönetim SQL tablolarını doğrudan Azure portalında GUI. Azure Mobile Apps birçok özellik desteklese de, kapsamı Bu örnek, bir Azure mobil uygulama arka ucu Unity projeden depolanan verileri okurken ve yazarken sınırlıdır.

## <a name="create-a-new-azure-mobile-app"></a>Yeni bir Azure mobil uygulaması oluşturma

Oturum [Azure portal](https://ms.portal.azure.com). Bir Azure aboneliğiniz yoksa [ücretsiz deneme sürümü](https://azure.microsoft.com/en-us/free/) veya gelen krediler dahil [Visual Studio geliştirme Essentials](https://www.visualstudio.com/dev-essentials/) birden fazla bu kılavuzu tamamlamak için yeterli olacaktır.

**Portalın içinde bir kez:**

1. Seçin **yeni > Web + mobil > mobil uygulama > oluşturma**.

  ![Yeni bir mobil uygulaması oluşturma](media/vstu_azure-configure-easy-tables-image1.png)

2. Yeni mobil uygulamayı yapılandırın:

  * **Uygulama adı**. Bu Azure mobil uygulama arka ucuna bağlanmak için kullanılan URL oluşturacaksınız. Yeşil onay işareti tarafından gösterilen benzersiz bir ad seçmeniz gerekir.

  * **Abonelik**. Yeni mobil uygulama için fatura kullanır abonelik seçin.

  * **Kaynak grubu**. Kaynak grupları ilgili kaynakların daha kolay yönetim sağlar. Varsayılan olarak Azure yeni uygulama olarak aynı ada sahip yeni bir kaynak grubu oluşturur. Varsayılan ayar gözden geçirme için iyi çalışır.

  *  **Uygulama hizmeti planı/konumu**. Hizmet planı bilgi işlem gücü, konum ve yeni mobil uygulamanızı barındırmak için Azure kullandığı kaynakları maliyetini belirler. Varsayılan olarak Azure bazı varsayılan ayarlarla yeni bir hizmet planı oluşturur. Bu kılavuz en basit seçenek budur. Ancak, bir yeni service planının fiyatlandırma katmanı veya coğrafi konum özelleştirmek için bu menüyü kullanın. Ayrıca, hizmet planı için ayarları dağıttıktan sonra değiştirilebilir.

  ![Yeni bir mobil uygulaması oluşturma](media/vstu_azure-configure-easy-tables-image2.png)

3. Seçin **oluşturma** ve Azure yeni kaynak dağıtmak için kaç dakika verin. Dağıtım tamamlandığında, Azure Portal'da bir bildirim görürsünüz.

## <a name="add-a-new-data-connection"></a>Yeni bir veri bağlantısı Ekle

4. Dağıtım tamamlandıktan sonra tıklatın **tüm kaynakları** düğmesine tıklayın ve ardından yeni oluşturduğunuz mobil uygulamayı seçin.

  ![Yeni mobil uygulama seçin](media/vstu_azure-configure-easy-tables-image3.png)

5. Yeni açılan dikey pencerede, sol taraftaki-menüde aşağı kaydırın ve tıklayın **kolay tablolar** altında listelenen düğmesi **mobil** başlığı.

  ![Kolay tabloları seçin](media/vstu_azure-configure-easy-tables-image4.png)

6. Mavi tıklatın **kolay tablolar/kolay API'leri yapılandırmanıza gerek** kolay tabloları dikey pencerenin üst kısmında görüntüleme dikkat edin.

  ![Kolay tabloları bildirim yapılandırmak tıklayın](media/vstu_azure-configure-easy-tables-image5.png)

7. Diyor bildirim tıklatın **kolay tabloları kullanılacak bir veritabanı gerekir. Bir oluşturmak için buraya tıklayın**.

  ![Create veritabanı bildirim tıklatın](media/vstu_azure-configure-easy-tables-image6.png)

8. Veri bağlantıları dikey penceresinde **Ekle** düğmesi.

  ![Ekle düğmesini tıklatın](media/vstu_azure-configure-easy-tables-image7.png)

9. Bir veri bağlantısı dikey penceresinde Ekle'yi üzerinde **SQL veritabanı**.

  ![SQL veritabanı seçin](media/vstu_azure-configure-easy-tables-image8.png)

10. Yeni SQL database ve SQL server yapılandırmak için bir dikey pencere açılır:

  * **Ad**. Veritabanı için bir ad girin.

  * **Hedef sunucu**. Tıklatın **hedef sunucu** yeni sunucu dikey penceresini açın.

      * **Sunucu adı**. Sunucu için bir ad girin.

      * **Sunucu Yöneticisi oturum açma ve parola**. Bir kullanıcı adı ve parola sunucu yöneticisinin oluşturun

      * **Konum**. Sunucu için yakın bir konum seçin.

      * Emin **azure hizmetlerinin sunucuya erişmesine izin** onay kutusu işaretli kalır.

      * Tıklatın **seçin** sunucu yapılandırmasını tamamlamak için.

    * **Fiyatlandırma katmanı**. İzlenecek yol için varsayılan ayarı koruyun. Bu daha sonra değiştirilebilir.

    * **Harmanlama**. Varsayılan ayarı koruyun.

    * Tıklatın **seçin** veritabanı yapılandırmayı tamamlamak için.

    ![SQL server ve veritabanı yapılandırma](media/vstu_azure-configure-easy-tables-image9.png)

11. Geri Ekle veri bağlantısı dikey penceresine tıklayın **bağlantı dizesi**. Bağlantı dizesi dikey penceresi görüntülendiğinde, varsayılan ayarları bırakın ve tıklatın **Tamam**.

  ![Bağlantı dizesi tıklatın](media/vstu_azure-configure-easy-tables-image9.1.png)

12. Geri Ekle veri bağlantısı dikey penceresine metin "MS_TableConnectionString" artık italik olmalıdır. Tıklatın **Tamam** ve Azure yeni veri bağlantısı oluşturmak için kaç dakika verin. İşlem tamamlandığında bildirim ulaşırsınız.

  ![Tamam'ı tıklatın](media/vstu_azure-configure-easy-tables-image9.2.png)

## <a name="complete-the-easy-table-initialization"></a>Kolay tablo başlatma işlemini tamamlamak

13. Yeni veri bağlantısı başarıyla oluşturulduktan sonra tıklatın **tüm kaynakları** düğmesine tıklayın ve mobil uygulamaya tekrar tekrar gidin. Kolay tablo yapılandırma uyarısı yenilemek için bu adımı tamamlamak önemlidir.

14. Seçin ve aşağı kaydırma **kolay tablolar**ve bir kez daha mavi seçin **kolay tablolar/kolay API'leri yapılandırmanıza gerek** dikkat edin.

  ![Kolay tabloları bildirimi tıklatın](media/vstu_azure-configure-easy-tables-image5.png)

15. Açılan dikey durum "Zaten bir veri bağlantısı elinizde" aşağıda bu sefer **1** başlığı. Altında **2** başlığı belirten onay kutusuna tıklayın **bu site içeriğinin üzerine yazacağını kabul ediyorum.** Şimdi **başlatma uygulama** ve başlatma işlemini tamamlamak Azure birkaç dakika bekleyin. İşlem tamamlandığında, yeni bir bildirim Duyurusu.

  ![Initialize uygulamaya tıklayın](media/vstu_azure-configure-easy-tables-image10.png)

## <a name="next-step"></a>Sonraki adım

* [Kolay Tablolar Oluşturma](visual-studio-tools-for-unity-azure-setup.md)
