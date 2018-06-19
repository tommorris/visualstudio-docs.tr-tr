---
title: Azure işlevleri giriş
description: Azure işlevleri, Mac için Visual Studio kullanarak
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.topic: article
ms.technology: vs-ide-install
ms.assetid: 25CD47A4-5B32-4734-8EF3-E24A02AABF29
ms.openlocfilehash: 5d787efbd09ad7f2d4a1f5f72b8f1493d8c6c587
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33871088"
---
# <a name="introduction-to-azure-functions"></a>Azure işlevleri giriş

Azure işlevleri oluşturmak ve – – işlevleri – – kod parçacıkları olay denetimli açıkça sağlamak veya altyapısını yönetmek zorunda kalmadan bulutta çalıştırmak için bir yoldur. Azure işlevleri hakkında daha fazla bilgi için bkz: [Azure işlevleri belgelerine](https://docs.microsoft.com/azure/azure-functions/).

## <a name="requirements"></a>Gereksinimler

Azure işlevi araçları dahil edilmiştir **Mac 7.5 için Visual Studio**.

Oluşturup işlevleri dağıtmak için de kullanılabilir ücretsiz bir Azure aboneliğine ihtiyacınız [ https://azure.com/free ](https://azure.com/free).

## <a name="creating-your-first-azure-functions-project"></a>İlk Azure işlevleri projenizi oluşturma

1. Mac için Visual Studio'da seçin **Dosya > Yeni bir çözüm...** 
2. Yeni Proje iletişim kutusundan altında Azure işlevleri şablonunu seçin **bulut > Genel** tıklatıp **sonraki**:

    ![Azure işlevleri seçeneğini gösteren yeni proje iletişim kutusu](media/azure-functions-image1.png)

3. Girin bir **proje adı** seçip **oluşturma**.

Mac için Visual Studio .NET standart proje bir varsayılan HttpTrigger işlevine yer oluşturur. Ayrıca, çeşitli NuGet başvurular içerir **AzureWebJobs** paketleri, yanı sıra **Newtonsoft.Json** paket.

![Visual Studio için yepyeni bir azure işlevi şablondan görüntüleme Mac Düzenleyicisi](media/azure-functions-newproj.png)

Yeni Proje aşağıdaki dosyaları içerir:

* **HttpTrigger.cs** – Bu sınıf, bir HTTP tetiklemeli işlevin Demirbaş kod içerir. İçerdiği bir **FunctionName** işlev adı ve bir tetikleyici özniteliği özniteliğiyle **HttpTrigger**, belirtir işlevi bir HTTP isteği tarafından tetiklenir. İşlev yöntemi hakkında daha fazla bilgi için başvurmak [Azure işlevleri C# Geliştirici Başvurusu](https://docs.microsoft.com/azure/azure-functions/functions-dotnet-class-library) makalesi.
* **Host.JSON** – bu dosya işlevleri ana bilgisayar için genel yapılandırma seçeneklerini açıklar. Bir örnek dosyası ve bu dosya için kullanılabilen ayarlar hakkında bilgi için bkz: [host.json başvuru Azure işlevleri için](https://docs.microsoft.com/azure/azure-functions/functions-host-json).
* **Local.Settings.JSON** – bu dosya işlevleri yerel olarak çalıştırmak için tüm ayarları içerir. Bu ayarlar Azure işlevleri çekirdek araçları tarafından kullanılır. Daha fazla bilgi için bkz: [yerel ayarları dosyasına](https://docs.microsoft.com/en-us/azure/azure-functions/functions-run-local#local-settings-file) Azure işlevleri çekirdek araçları makalede.

Mac için Visual Studio'da yeni bir Azure işlevleri proje oluşturduğunuza göre yerel makinenizden varsayılan HTTP tetiklemeli işlevin test edebilirsiniz.

<!--
## Create an Azure storage account

[Describe why this step is necessary and what it does]

1. Log on to your account at [https://portal.azure.com](https://portal.azure.com).
2. Under the **Favorites** section, located on the left of the screen, select **Storage Accounts**:
    ![]()
3. Select **Add** to create a new storage account:
    ![]()
4. Enter a globally unique name for the **Name** and reuse it for the **Resource group**. You can keep all the other items as their default.
    ![]()
5. Click **Create**. It might take a few minutes to create the storage account. You'll get a notification once it has been successfully created.
6. Select the **Go to resource** button from the notification:
    ![]()
-->

## <a name="testing-the-function-locally"></a>İşlev yerel olarak test etme

Mac için Azure işlevleri desteği Visual Studio'da test edin ve işlevinizi yerel geliştirme bilgisayarınızda hata ayıklama.

1. İşlevinizi yerel olarak test için basın **çalıştırmak** Mac için Visual Studio düğmesini:

    ![Düğme mac için visual Studio'da hata ayıklamayı Başlat](media/azure-functions-run.png)

1. Proje çalışan Azure işlev hata ayıklama yerel başlar ve aşağıdaki görüntüde gösterildiği gibi yeni bir Terminal penceresi açılır: 

    ![Terminal penceresi gösteren işlevi çıktı](media/azure-functions-terminal.png) 

    URL çıktıdan kopyalayın.

3. HTTP istek URL'sini tarayıcınızın adres çubuğuna yapıştırın. Sorgu dizesi eklemenize `?name=<yourname>` URL'nin sonuna ve istek yürütülemiyor. Aşağıdaki resimde, tarayıcıda işlev tarafından döndürülen yerel GET isteğine yanıt gösterilmektedir:

    ![HTTP isteği tarayıcıda](media/azure-functions-httpreq.png)

## <a name="creating-a-new-function"></a>Yeni bir işlev oluşturma

İşlev şablonları, yeni işlevler en yaygın tetikleyiciler ve şablonlar kullanarak hızlı bir şekilde oluşturmanızı sağlar. Yeni bir Azure işlevleri projesi oluşturduğunuzda, otomatik olarak bir HttpTrigger işlevi içerir. Başka türde bir işlev oluşturmak için aşağıdakileri yapın:

1. Kaldırma **HttpTrigger.cs** sağ tıklayarak ve seçerek dosya **kaldırmak**. Aşağıdaki uyarıyı seçin **silmek** projenizden kaldırmak için:

    ![Dosya projeden kaldırmak için iletişim kutusu](media/azure-functions-remove.png)

2. Yeni bir işlev eklemek için proje adına sağ tıklayın ve seçin **Ekle > işlev Ekle...** :

    ![Yeni işlev eklemek için bağlam eylemi](media/azure-functions-addnew.png)

3. Gelen **yeni Azure işlevi** iletişim kutusunda, ihtiyaç duyduğunuz işlevi seçin:

    ![Yeni bir azure işlevi iletişim kutusu](media/azure-functions-newfunction.png)

    Bir Azure işlevi şablonlar listesi aşağıdaki bölümde sağlanır.

## <a name="available-function-templates"></a>Kullanılabilir işlev şablonları

- **HTTP** – bir HTTP isteği kullanarak kodunuzun yürütülmesini tetikler. Açık şablonları için aşağıdaki HTTP Tetikleyicileri vardır:
    - HTTP GET CRUD
    - HTTP POST CRUD
    - HTTP tetikleyicisini parametrelere sahip
    - HTTP tetikleyici
- **Zamanlayıcı** – önceden tanımlanmış bir zamanlamaya göre temizleme veya diğer toplu işlem görevlerini yürütün. Bu şablon iki alanlarını alır: bir ad ve altı alan CRON ifade bir zamanlama. Daha fazla bilgi için bkz: [Azure işlevleri makalesi saat](https://docs.microsoft.com/azure/azure-functions/functions-create-scheduled-function)
- **GitHub tetikleyici** – GitHub depolarınızda gerçekleşen olaylara yanıt. Daha fazla bilgi için bkz: [github'da Azure işlevleri makale](https://docs.microsoft.com/azure/azure-functions/functions-create-github-webhook-triggered-function)
    - GitHub Web kancası için bir sorun veya çekme isteği alır ve bir açıklama ekler GitHub commenter – bu işlev çalışır.
    - GitHub Web kancası aldığında, bu işlev GitHub Web kancası – çalıştırılır
- **BLOB tetikleyici** – Azure Storage bloblarını bir kapsayıcıya eklendiğinde. İşlev adı yanı sıra bu şablon bir yol ve bağlantı özelliği de alır. Path özelliği tetikleyici izleyeceğiniz depolama hesabınızda yoludur. Bağlantı hesabı, depolama hesabı bağlantı dizesi içeren uygulama ayarının adıdır. Daha fazla bilgi için bkz: [Azure işlevleri Blob Storage makale](https://docs.microsoft.com/azure/azure-functions/functions-create-storage-blob-triggered-function).
- **Tetikleyici sıraya** – bu Azure Storage kuyruğuna geldiklerinde iletilere yanıt vereceği bir işlevdir. İşlev adı yanı sıra bu şablon geçen bir **yolu** (içinden ileti okunabilir sırasının adı) ve depolama hesabı **bağlantı** (depolama alanınızı içeren uygulama ayarı adı Hesap bağlantı dizesi). Daha fazla bilgi için bkz: [Azure işlevleri makale üzerinde kuyruk depolama](https://docs.microsoft.com/azure/azure-functions/functions-create-storage-queue-triggered-function).
- **Genel Web kancası** – bu Web kancalarını destekleyen herhangi bir hizmetinden bir istek aldığında, çalışacak, basit bir işlevdir. Daha fazla bilgi için bkz: [Azure işlevleri makale üzerinde genel Web kancaları](https://docs.microsoft.com/azure/azure-functions/functions-create-generic-webhook-triggered-function)
- **Görüntü Boyutlandır** – bu işlev bir kapsayıcıya bir blob eklendiğinde yeniden boyutlandırılan görüntülerini oluşturur. Şablon tetikleyici, küçük resim çıkışı ve bir orta görüntü çıkış yolu ve bağlantı dizesini alır.
- **SAS belirteci** – bu işlev belirli bir Azure depolama kapsayıcısı ve blob adı için bir SAS belirteci oluşturur. İşlev adı yanı sıra bu şablon bir yol ve bağlantı özelliği de alır. Path özelliği tetikleyici izleyeceğiniz depolama hesabınızda yoludur. Bağlantı hesabı, depolama hesabı bağlantı dizesi içeren uygulama ayarının adıdır. **Erişim hakları** de ayarlanması gerekir. Yetki düzeyini olup işlevi bir API anahtarı gerektirir ve kullanmak için hangi anahtarı denetler; Bir işlev tuşu işlevi kullanır; Yönetici, ana anahtarı kullanır. Daha fazla bilgi için bkz: [C# SAS belirteci oluşturmak için Azure işlevi](https://azure.microsoft.com/resources/samples/functions-dotnet-sas-token/) örnek.
- **Dayanıklı işlevleri orchestration** – dayanıklı işlevleri sunucusuz bir ortamda durum bilgisi olan işlevler yazmanızı sağlar. Uzantı durumu, kontrol noktaları ve yeniden başlatmalar sizin için yönetir. Daha fazla bilgi için Azure işlevleri kılavuzlara bakın [dayanıklı işlevleri](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)