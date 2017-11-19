---
title: "Yeni bağlantı ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8a93c287-2834-4a83-a590-bdc3fe8d293f
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: accf99d7a1d230bac64ebd8ebf9c9f1071ad1876
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="add-new-connections"></a>Yeni bağlantı ekleme
Bir veritabanı veya hizmet bağlantınızı test ve veritabanı içeriklerini ve şemalarını kullanarak keşfedin **Sunucu Gezgini**, **Cloud Explorer**, veya **SQL Server Nesne Gezgini**. Bu windows işlevselliğini bazı ölçüde çakışıyor. Temel farklılıklar şunlardır:  
  
 - Server Explorer  
 Visual Studio'da varsayılan olarak yüklüdür. Bağlantıları sınamak ve SQL Server veritabanları, yüklü bir ADO.NET sağlayıcısı diğer veritabanlarına ve bazı Azure hizmetleri görüntülemek için kullanılabilir. Ayrıca Sistem performans sayaçları, olay günlüklerini ve ileti kuyrukları gibi alt düzey nesneleri gösterir. Bir veri kaynağı hiçbir ADO.NET sağlayıcısı varsa, burada görüntülenmeyecektir, ancak bunu Visual Studio'dan program aracılığıyla bağlanarak kullanmaya devam edebilirsiniz.  
  
 - Bulut Gezgini  
 Visual Studio uzantısı olarak el ile yüklemeniz seçerek bu pencereyi **Araçları** > **Uzantılar ve güncelleştirmeler** > **çevrimiçi**  >  **Visual Studio Galerisi**. Keşfetmek ve Azure hizmetlerine bağlanmak için özel işlevler sağlar.  
  
 - SQL Server Nesne Gezgini  
 SQL Server veri araçları ile birlikte yüklenir ve altında görünür **Görünüm** menüsü. Var. görmüyorsanız, Git **programlar ve Özellikler** Denetim Masası ' nda Visual Studio bulun ve ardından **değişiklik** SQL Server veri araçları için onay kutusunu işaretledikten sonra yükleyiciyi yeniden çalıştırın. Kullanım **SQL Server Nesne Gezgini** görünümü SQL veritabanları (bunlar bir ADO.NET sağlayıcısı varsa) için yeni veritabanları oluşturma, şemalar değiştirmek, saklı yordamlar oluşturma, bağlantı dizeleri almak, verileri görüntüleyebilir. Yüklü hiçbir ADO.NET sağlayıcısı SQL veritabanları burada görünmez, ancak hala kendisine programlı olarak bağlayabilirsiniz.  
  
## <a name="add-a-connection-in-server-explorer"></a>Sunucu Gezgini Bağlantı Ekle  
 Veritabanına bir bağlantı oluşturmak için tıklatın **Bağlantı Ekle** simgesine **Sunucu Gezgini**, veya sağ **Sunucu Gezgini** üzerinde **veri Bağlantıları** düğümü ve select **Bağlantı Ekle**. Buradan, başka bir sunucuda, bir SharePoint hizmeti veya bir Azure hizmeti bir veritabanına bağlanabilir.  
  
 ![Sunucu Gezgini yeni bağlantı simgesi](../data-tools/media/raddata-server-explorer-new-connection-icon.png "raddata Sunucu Gezgini yeni bağlantı simgesi")  
  
 Bu işlem sonrasında **Bağlantı Ekle** iletişim kutusu. Burada, biz SQL Server yerel veritabanı örneğinin adı girdiniz.  
  
 ![Yeni bağlantı ekleme](../data-tools/media/raddata-add-new-connection-dialog.png "raddata Ekle yeni bağlantı iletişim kutusu")  
  
## <a name="change-the-provider"></a>Sağlayıcı değiştirme  
 Veri kaynağı istemezsiniz ise, tıklatın **değişiklik** düğmesi yeni bir veri kaynağı ve/veya yeni bir ADO.NET veri sağlayıcı seçin. Yeni sağlayıcıyı nasıl yapılandırdığınıza bağlı olarak, kimlik bilgilerini isteyebilir.  
  
 ![Değiştirme AD0.NET veri sağlayıcısı](../data-tools/media/raddata-change-ad0.net-data-provider.png "raddata değişiklik AD0.NET veri sağlayıcısı")  
  
## <a name="test-the-connection"></a>Bağlantıyı sınayın  
 Veri kaynağını seçtikten sonra tıklatın **Bağlantıyı Sına**. İşlemi başarılı değil, sorun giderme satıcısının belgelerine göre yapmanız gerekir.  
  
 ![Bağlantı sınama](../data-tools/media/raddata-test-connection.png "raddata Bağlantıyı Sına")  
  
 Test başarılı olursa, oluşturmak için hazır bir *veri kaynağı*, gerçekten anlamına gelir bir Visual Studio terimi olduğu bir *veri modeli* temel alınan veritabanı veya hizmet tabanlı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [.NET için Visual Studio veri araçları](../data-tools/visual-studio-data-tools-for-dotnet.md)