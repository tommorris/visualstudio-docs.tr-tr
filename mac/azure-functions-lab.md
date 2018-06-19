---
title: 'Öğretici: Azure işlevleri'
description: Azure işlevleri, Mac için Visual Studio kullanarak
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.topic: article
ms.technology: vs-ide-install
ms.assetid: 38FD2070-5151-482E-B0A9-993715128736
ms.openlocfilehash: 80c04182733204a18ee669d3851deab867cc56cd
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33877338"
---
# <a name="tutorial-getting-started-with-azure-functions"></a>Öğretici: Azure işlevlerini kullanmaya başlama

Bu laboratuvarda, Mac için Visual Studio kullanarak Azure işlevleri oluşturmaya başlamak nasıl öğreneceksiniz. Azure işlevleri geliştiricileri için bağlamalar ve Tetikleyicileri kullanılabilir birçok türde birini temsil eden Azure depolama tablolar ile tümleştirmeniz.

## <a name="objectives"></a>Amaçlar

> [!div class="checklist"]
> * Oluşturma ve yerel Azure işlevlerinde hata ayıklama
> * Web ve Azure storage kaynakları ile tümleştirme
> * Birden çok Azure işlevleri içeren bir iş akışı düzenlemek

## <a name="requirements"></a>Gereksinimler

- Visual Studio Mac 7.5 veya daha yüksek.
- Bir Azure aboneliği (kullanılabilir boş [ https://azure.com/free ](https://azure.com/free)).

## <a name="exercise-1-creating-an-azure-functions-project"></a>Alıştırma 1: bir Azure işlevleri projesi oluşturma

1. Başlatma **Mac için Visual Studio**.

1. Seçin **Dosya > Yeni bir çözüm**.

1. Gelen **bulut > Genel** kategorisi, select **Azure işlevleri** şablonu. Azure işlevleri barındıran bir .NET sınıf kitaplığı oluşturmak için C# kullanır. **İleri**'ye tıklayın.

    ![Azure işlevleri Şablon Seçimi](media/azure-functions-lab-image1.png)

1. Ayarlama **proje adı** için **"AzureFunctionsLab"** tıklatıp **oluşturma**.

    ![adlandırma ve azure işlevi projenizi oluşturma](media/azure-functions-lab-image2.png)

1. Düğümleri genişletin **çözüm paneli**. Varsayılan proje şablonu Newtonsoft.Json paket yanı sıra, Azure Web işleri paketleri çeşitli NuGet başvurular içerir. 

     Ayrıca üç dosyası yok:- **host.json** genel açıklamak için - konak için yapılandırma seçeneklerini **local.settings.json** hizmet ayarlarını yapılandırma. 
        -Proje şablonu varsayılan HttpTrigger da oluşturur. Bu Laboratuvar amacıyla, silmeniz gerekir **HttpTrigger.cs** proje dosyasından.

    Açık **local.settings.json**. İki boş bir bağlantı dizesi ayarlarının zorunda varsayılan olarak ayarlanır.

    ![Çözüm paneli görüntüleme local.settings.json dosyası](media/azure-functions-lab-image3.png)

## <a name="exercise-2-creating-an-azure-storage-account"></a>Alıştırma 2: Azure storage hesabı oluşturma

1. Adresindeki Azure hesabınızda oturum [ https://portal.azure.com ](https://portal.azure.com).
 
1. Altında **Sık Kullanılanlar** ekranın sol tarafta bulunan bölümünde seçin **depolama hesapları**:

    ![Azure portal gösteren depolama hesapları öğesini Sık Kullanılanlar bölümü](media/azure-functions-lab-image4.png)

1. Seçin **Ekle** yeni bir depolama hesabı oluşturmak için:

    ![Yeni depolama hesabı Ekle düğmesi](media/azure-functions-lab-image5.png)

1. Genel olarak benzersiz bir ad girin **adı** ve için yeniden **kaynak grubu**. Varsayılan olarak tüm diğer öğeler kullanmaya devam edebilir.

    ![Yeni depolama hesabı ayrıntıları](media/azure-functions-lab-image6.png)

1. **Oluştur**'u tıklatın. Depolama hesabı oluşturmak için birkaç dakika sürebilir. Başarılı bir şekilde oluşturulduktan sonra bir bildirim alacaksınız.

    ![Dağıtım başarılı bildirim](media/azure-functions-lab-image7.png)

1. Seçin **kaynağa gidin** bildirim düğmesinden.

1. Seçin **erişim anahtarları** sekmesi.

    ![erişim anahtarı ayarı](media/azure-functions-lab-image8.png)

1. İlk kopyalama **bağlantı dizesi**. Bu dize, Azure depolama daha sonra Azure işlevleri ile tümleştirmek için kullanılır.

    ![Anahtar 1 için bilgi](media/azure-functions-lab-image9.png)

1. Geri dönüp **Mac için Visual Studio** içinde tam bağlantı dizesi olarak Yapıştır **AzureWebJobsStorage** ayarı **local.settings.json**. Şimdi öznitelikleri ayarında adı kaynaklarına erişmesi işlevler için başvuruda bulunabilir.

    ![yerel ayarlar dosyasıyla girilen bağlantı anahtarı](media/azure-functions-lab-image10.png)

## <a name="example-3-creating-and-debugging-an-azure-function"></a>Örnek 3: Oluşturma ve bir Azure işlevi hata ayıklama

1. Artık biraz kod eklemeye başlamak hazırsınız. Azure işlevleri, bir .NET sınıf kitaplığı ile çalışırken, statik yöntemleri olarak eklenir. Gelen **çözüm paneli**, sağ **AzureFunctions** proje düğümüne ve seçin **Ekle > işlev Ekle...** :

    ![İşlev seçenek ekleme](media/azure-functions-lab-image11.png)

1. Yeni Azure işlevleri iletişim kutusunda, genel Web kancası şablonu seçin. Ayarlama **adı** için **Ekle** tıklatıp **Tamam** işlevinizi oluşturmak için:

    ![Yeni azure işlevleri iletişim kutusu](media/azure-functions-lab-image12.png)

1. Yeni dosyasının üstüne ekleyin **kullanarak** yönergeleri aşağıdaki:

    ```csharp
    using Microsoft.Azure.WebJobs.Extensions.Http;
    using System.Web;
    using Microsoft.WindowsAzure.Storage.Table;
    ```
1. Varolan kaldırmak `Run` yöntemi ve Azure işlevinizi olarak sınıfına aşağıdaki yöntemi ekleyin:

    ```csharp
    [FunctionName("Add")]
    public static int Run(
    [HttpTrigger(AuthorizationLevel.Function, "get", Route = null)]
    HttpRequestMessage req,
    TraceWriter log)
    {
        int x = 1;
        int y = 2;

        return x + y;
    }
    ```
1. Şimdi yöntemi tanımıyla tarafından parça parça yol. 
    
    İlk şey göreceksiniz **FunctionName** bu yöntemi bir Azure işlevi olarak işaretler özniteliği. Öznitelik işlevi genel adını belirtir. Öznitelik adı gerçek yöntemi adıyla eşleşmesi gerekmez.

    ![Vurgulanan FunctionName özniteliğiyle yeni çalışma yöntemi](media/azure-functions-lab-image13.png)

1. Ardından, yöntem olarak işaretlenmiş bir **ortak statik** gereklidir yöntemi. Dönüş değeri olduğunu göreceksiniz bir **int**. Yöntem öznitelikleri kullanarak aksi belirtilmediği sürece, bir Azure işlevi herhangi void olmayan dönüş değerini metin olarak istemciye döndürülür. Varsayılan olarak döndürülür **XML**, ancak değiştirilebilir **JSON**, laboratuar ortamında bunu daha sonra.

    ![Vurgulanan yöntemi başlatma ile yeni çalışma yöntemi](media/azure-functions-lab-image14.png)

1. İlk parametre ile işaretlenmiş **HttpTrigger** bu yöntem bir HTTP isteği tarafından çağrılan belirten özniteliği. Öznitelik de desteklediği fiiller yanı sıra yöntemi yetkilendirme düzeyini belirtir (yalnızca **"GET"** bu durumda). Ayrıca isteğe bağlı olarak tanımlayabilir bir **rota** yolunu yöntemini geçersiz kılar ve otomatik olarak değişkenleri yolundan ayıklamak için bir yol sunar. Bu yana **rota** burada bu yöntem yoluna varsayılan NULL'dur **/api/Add**.

    ![Vurgulanan parametresiyle yeni çalışma yöntemi](media/azure-functions-lab-image15.png)

1. Yöntemine son parametre bir **TraceWriter** tanılama ve hata iletilerini günlüğe kaydetmek için kullanılabilir.

    ![Vurgulanan TraceWriter ile yeni çalışma yöntemi](media/azure-functions-lab-image16.png)

1. Bir kesme noktası ayarlayın **dönmek** satır kenar boşluğunda tıklayarak yönteminin satır:

    ![Dönüş satırında kesme](media/azure-functions-lab-image17.png)

1. Derleme ve tuşlarına basarak projenin hata ayıklama oturumunda çalıştırma **F5** veya seçerek **Çalıştır > hata ayıklamayı Başlat**. Alternatif olarak tıklatabilir **çalıştırmak** düğmesi. Bu seçeneklerin tümü aynı görevi gerçekleştirin. Bu Laboratuvarın geri kalanı başvuran **F5**, ancak en deneyimli bulma yöntemini kullanabilirsiniz.

    ![Projesini derlemeyi ve çalıştırmayı](media/azure-functions-lab-image18.png)

1. Proje çalıştıran Terminal uygulama otomatik olarak açılır.

1. Projeyi Azure yöntem öznitelikleri ve bu makalenin sonraki bölümlerinde ele bir dosya kuralını temel işlevleri algılama bir süreci başlatılır. Bu durumda, tek bir Azure işlevi algılar ve "1 iş işlevi oluşturur".

    ![Terminal Azure işlevinde çıktısı](media/azure-functions-lab-image19.png)

1. Başlangıç iletileri altındaki tüm HTTP tetikleyicisini API'leri URL'lerini Azure işlevleri konak yazdırır. Yalnızca olmamalıdır biri. Bu URL'yi kopyalayın ve yeni bir tarayıcı sekmesinde yapıştırın.

    ![Azure işlevi API URL'si](media/azure-functions-lab-image20.png)

1. Kesme noktası hemen tetiklemesi gereken. Web isteği, işleve yönlendirilir ve artık hata ayıklaması yapılabilir. Fare üzerindeyken **x** değerini görmek için değişkeni. 

    ![Kesme noktası tetiklendi](media/azure-functions-lab-image21.png)

1. Daha önce eklemek için kullanılan yöntemin aynısını kullanarak kesme noktası kaldırma (kenar boşluğu tıklatın veya satır seçip tuşuna **F9**).

1. Tuşuna **F5** çalışmaya devam edebilmesi için.

1. Tarayıcıda yöntemi XML sonucunu işlenir. Beklendiği gibi yatkýn toplam sabit kodlanmış toplama işlemi oluşturur. Yalnızca "3" Safari'de, Git için görürseniz, Not **Safari > Tercihler > Gelişmiş** ve değer "**menü çubuğunu göster geliştirmek menüde**" onay kutusunu ve sayfayı yeniden yükleyin.

1. İçinde **Mac için Visual Studio**, tıklatın **durdurmak** hata ayıklama oturumu sona erdirmek için düğmesi. Yeni değişiklikler toplanma emin olmak için (durdurun ve ardından Çalıştır) hata ayıklama oturumu başlatmayı unutmayın.

    ![Seçenek hata ayıklamayı durdurun](media/azure-functions-lab-image22.png)

1. İçinde **çalıştırmak** yöntemi Değiştir **x** ve **y** tanımları aşağıdaki kod ile. Böylece toplama işlemi sağlanan parametreler göre dinamik olarak gerçekleştirilebilir. Bu kodu URL'nin Sorgu dizesinden değerlerini ayıklar.

    ```csharp
    var query = HttpUtility.ParseQueryString(req.RequestUri.Query);

    int x = int.Parse(query["x"]);

    int y = int.Parse(query["y"]);

    return x + y;
    ```
1. Uygulamayı çalıştırın.

1. Tarayıcı penceresine dönün ve dize `/?x=2&y=3` URL. URL'nin tamamı şimdi olmalıdır `http://localhost:7071/api/Add?x=2&y=3`. Yeni URL'ye gidin.

1. Bu süre sonucu yeni parametreler yansıtmalıdır. Projeyi farklı değerlerle çalıştırın çekinmeyin. Eksik veya geçersiz parametreler bir hata özel durum oluşturacak şekilde denetleme, herhangi bir hata olmadığını unutmayın.

1. Hata ayıklama oturumu durdurun.


## <a name="exercise-4-working-with-functionjson"></a>Alıştırma 4: function.json ile çalışma

1.  Bir önceki alıştırmada Mac için Visual Studio "iş işlevi Kitaplığı'nda tanımlanan Azure işlev için üretilen" değinilen. Azure işlevleri yöntem öznitelikleri çalışma zamanında gerçekten kullanmaz, ancak bunun yerine nerede yapılandırmak için derleme zamanı dosya sistemi kuralını kullanır ve Azure işlevleri kullanılabilir hale getirilir nasıl budur. Gelen **çözüm paneli**, proje düğümüne sağ tıklayın ve seçin **Finder ortaya**.

     ![Bulucu menü seçeneğini göster](media/azure-functions-lab-image23.png)

1. Ulaşana kadar dosya sisteminde gezinmek **bin/Debug/netstandard2.0**. Adlı bir klasör olmalıdır **Ekle**. Bu klasör, C# kodunda işlevi ad özniteliği olan karşılık gelecek şekilde oluşturuldu. Tek bir ortaya çıkarmak üzere Ekle klasörünü genişletin **function.json** dosya. Bu dosya çalışma zamanı tarafından barındırmak ve Azure işlevi yönetmek için kullanılır. Derleme zamanı desteği (C# betik veya JavaScript gibi) diğer dil modeller için bu klasörleri el ile sürdürülür ve oluşturulmalıdır. C# geliştiricileri için bunlar otomatik olarak derleme sırasında öznitelik meta verilerden oluşturulur. Sağ **function.json** ve Visual Studio'da açmak için seçin.

    ![dosya dizininde Function.JSON](media/azure-functions-lab-image24.png)

1. Bu öğreticinin önceki adımları verilen, C# özniteliklerini temel bilgilere sahip olmalıdır. Dikkate alarak, bu JSON benzer görünmelidir. Ancak, önceki alıştırmalarda kapsamında olmayan birkaç öğe yok. Örneğin, her **bağlama** olmalıdır, **yönü** ayarlayın. Infer olarak **"içinde"** parametresi giriş gelirken demektir **"out"** parametresi bir dönüş değeri olduğunu gösterir (aracılığıyla **$return**) veya bir **çıkışı** yöntemine parametre. Belirtmeniz gerekir **KomutDosyası** (göre bu son konum) ve **entryPoint** derlemedeki yöntemi (ortak ve statik). Sonraki adımlarda bu modeli kullanarak bir özel işlevi yolu ekleyeceksiniz bu nedenle bu dosyanın içeriğini panoya kopyala.

    ![mac için visual Studio'da Aç Function.JSON dosyası](media/azure-functions-lab-image25.png)

1. İçinde **çözüm paneli**, sağ **AzureFunctionsLab** proje düğümüne ve seçin **Ekle > Yeni bir klasör**. Yeni bir klasör adı **ekleyici**. Varsayılan kurala göre bu klasörün adını yolunu API'sine gibi tanımlayacak **API/ekleyici**.

    ![Yeni klasör seçeneği](media/azure-functions-lab-image26.png)

1. Sağ **ekleyici** klasörü ve select **Ekle > yeni dosya**.

    ![Yeni dosya seçeneği](media/azure-functions-lab-image27.png)

1. Seçin **Web** kategori ve **boş JSON dosyası** şablonu. Ayarlama **adı** için **işlevi** tıklatıp **yeni**.

    ![Boş json dosya seçeneği](media/azure-functions-lab-image28.png)

1. Diğer içeriğini Yapıştır **function.json** (gelen 3. adım) uygulamasındaki yeni oluşturulan dosya varsayılan içeriğini değiştirin.

1. Aşağıdaki satırları json dosyasının üst kısmından kaldırın:

    ```json
    "configurationSource":"attributes",
    "generatedBy":"Microsoft.NET.Sdk.Functions-1.0.13",
    ```

1. İlk bağlama işleminin sonunda (sonra **"name": "req"** satırı), aşağıdaki özellikleri ekleyin. Önceki satırdaki virgül eklemeyi unutmayın. Şimdi ayıklanır gibi bu özellik varsayılan kök geçersiz kılar **int** yolundan parametreleri ve adlandırıldığı yöntem parametreleri yerleştirin **x** ve **y**.

    ```json
    "direction": "in",
    "route": "Adder/{x:int?}/{y:int?}"
    ```

1. Başka bir bağlama ilk altına ekleyin. Bu bağlama işlevinin dönüş değeri işler. Önceki satırdaki virgül eklemeyi unutmayın:

    ```json
    {
    "name": "$return",
    "type": "http",
    "direction": "out"
    }
    ```

1. Ayrıca güncelleştirme **entryPoint** özelliği bir yöntem kullanmak için dosyanın sonuna adlı **"Add2"**, aşağıda gösterildiği gibi. Bu, göstermektir yolu **API/ekleyici...**  uygun bir yöntem herhangi bir ad ile eşlemek (**Add2** burada).

    ```json
    "entryPoint": "<project-name>.<function-class-name>.Add2"
    ```

1. Son **function.json** dosya, aşağıdaki json gibi görünmelidir:

    ```json
    {
    "bindings": [
        {
        "type": "httpTrigger",
        "methods": [
            "get"
        ],
        "authLevel": "function",
        "direction": "in",
        "name": "req",
        "route": "Adder/{x:int?}/{y:int?}"
        },
        {
        "name": "$return",
        "type": "http",
        "direction": "out"
        }
    ],
    "disabled": false,
    "scriptFile": "../bin/AzureFunctionsProject.dll",
    "entryPoint": "AzureFunctionsProject.Add.Add2"
    }
    ```

1. Bunu yapmak için gerekli bir son tüm iş her değiştiğinde bu dosyayı çıktı dizini aynı göreli yolda kopyalamak Mac için Visual Studio istemek üzere adımdır. Seçilen dosya ile Özellikler sekmesini sağ taraftaki çubuğu ve için seçebileceğiniz **çıktı dizinine Kopyala** seçin **yeniyse Kopyala**:

    ![Json dosyası özellikleri seçenekleri](media/azure-functions-lab-image30.png)

1. İçinde **Add.cs**, yerine `Run` beklenen işlevi gerçekleştirmek için aşağıdaki yöntemiyle yöntemini (öznitelik dahil). Çok benzer `Run`, açık parametrelerini vardır ve hiçbir öznitelik kullanır ancak bu **x** ve **y**.

    ```csharp
    public static int Add2(
        HttpRequestMessage req,
        int x,
        int y,
        TraceWriter log)
    {
        return x + y;
    }
    ```
1. Tuşuna **F5** projesini derlemeyi ve çalıştırmayı için.

1. Yapı tamamlandıktan ve yukarı platform döner gibi artık bir ikinci yol yeni eklenen yöntemiyle eşleşen istekler için kullanılabilir olduğunu gösterir:

    ![Http işlevleri için URL](media/azure-functions-lab-image31.png)

1. Tarayıcı penceresine dönün ve gidin **http://localhost:7071/api/Adder/3/5**.

1. Bu süre yöntemi bir kez daha, yolun parametrelerinden çekme ve toplam oluşturan çalışır.

1. Geri dönüp **Mac için Visual Studio** ve hata ayıklama oturumunu sonlandırın.

## <a name="exercise-5-working-with-azure-storage-tables"></a>Alıştırma 5: Azure depolama sekmelerle çalışma

Genellikle, yapı hizmeti ne biz kadarki oluşturduktan ve önemli miktarda zaman ve/veya yürütmek için altyapı gerektiren daha çok daha karmaşık olabilir. Durumda, bu kaynakları kullanılabilir duruma geldiğinde işlenmek üzere sıraya alınan isteklerini kabul etmek etkili bulabilirsiniz olduğunu, hangi Azure işlevleri için destek sağlar. Diğer durumlarda, veri merkezi olarak depolamak istersiniz. Azure depolama tabloları, hızlı bir şekilde gerçekleştirmenize olanak tanır. 

1. Aşağıda sınıfına ekleyin **Add.cs**. Ad alanı içinde ancak mevcut bir sınıf dışında tamamlamalıdır.

    ```csharp
    public class TableRow : TableEntity
    {
        public int X { get; set; }
        public int Y { get; set; }
        public int Sum { get; set; }
    }
    ```
1. İçinde **Ekle** sınıfı, başka bir işlevi tanıtmak için aşağıdaki kodu ekleyin. Bir HTTP yanıtının içermeyen, bunu şu ana kadar benzersiz olduğunu unutmayın. Son satırı yeni döndürür **TableRow'a** daha sonra almak kolaylaştıracak bazı temel bilgilerle doldurulmuş (**PartitionKey** ve **RowKey**), yanı sıra kendi parametreleri ve topla. Yöntem içindeki kod ayrıca kullanır **TraceWriter** işlev çalıştığında bilmeniz kolay hale getirmek için.

    ```csharp
    [FunctionName("Process")]
    [return: Table("Results")]
    public static TableRow Process(
        [HttpTrigger(AuthorizationLevel.Function, "get",
            Route = "Process/{x:int}/{y:int}")]
        HttpRequestMessage req,
        int x,
        int y,
        TraceWriter log)
    {
        log.Info($"Processing {x} + {y}");
    
        return new TableRow()
        {
            PartitionKey = "sums",
            RowKey = $"{x}_{y}",
            X = x,
            Y = y,
            Sum = x + y
        };
    }
    ```
1. Tuşuna **F5** projesini derlemeyi ve çalıştırmayı için.

1. Tarayıcı sekmesinde gidin **http://localhost:7071/api/Process/4/6**. Bu tabloya eklenen başka bir satırda sonunda sonuçlanması gerektiğini kuyruğa başka bir ileti sokar.

1. Geri dönüp **Terminal** ve izlemek için gelen isteğin **4 + 6**.

    ![Terminal çıktısı gösteren eklenmesi isteği](media/azure-functions-lab-image32.png)

1. Aynı URL'sine yönelik istek yenilemek için tarayıcıya dönün. Bu tarihten bir hata görürsünüz **işlem** yöntemi. Kodu zaten varolan bir bölüm ve satır tuş bileşimini kullanarak Azure Table Storage tabloya satır eklemek çalışıyor olmasıdır.

    ``` 
    System.Private.CoreLib: Exception while executing function: Process. Microsoft.Azure.WebJobs.Host: Error while handling parameter $return after function returned:. Microsoft.Azure.WebJobs.Host: The specified entity already exists.
    ```

1. Hata ayıklama oturumunu sonlandırın.

1. Hata etkisini azaltmak için aşağıdaki parametreyi yöntemi tanımına hemen önce ekleyin **TraceWriter** parametresi. Bu parametre alma denemesi için Azure işlevleri platform bildirir bir **TableRow'a** gelen **sonuçları** üzerinde tablo **PartitionKey** biz depolamak için kullanmakta olduğunuz sonuçları. Ancak, bazı gerçek Sihirli gelen oyuna olduğunu fark edersiniz, **RowKey** dinamik olarak oluşturulan diğer temel **x** ve **y** parametrelerini çok aynı yöntem. Bu satır, ardından zaten varsa **TableRow'a** olacaktır, yöntem geliştirici tarafından gerekli ek hiçbir iş ile başlıyorsa. Satır yok sonra yalnızca null olması. Bu tür bir verimlilik, önemli iş mantığı ve altyapı üzerinde odaklanmak geliştiricilerin sağlar.

    ```csharp
    [Table("Results", "sums", "{x}_{y}")]
    TableRow tableRow,
    ```
1. Aşağıdaki kodu yöntemi başlangıcına ekleyin. Varsa **TableRow'a** biz zaten sonuçlara yol istenen işlem için hemen dönebilirsiniz tıklatıp null değil. Aksi takdirde işlevi önceki gibi devam eder. Bu verileri döndürmek için en sağlam yolu olmayabilir olsa da, çok az kod ile birden çok ölçeklenebilir katman boyunca son derece Gelişmiş işlemleri düzenleyebilirsiniz noktayı gösterir.

    ```csharp
    if (tableRow != null)
    {
        log.Info($"{x} + {y} already exists");
        return null;
    }
    ```
1. Tuşuna **F5** projesini derlemeyi ve çalıştırmayı için.

1. URL'de tarayıcı sekmesinde yenileme **http://localhost:7071/api/Process/4/6**. Bu kayıt için tablo satırı mevcut olmadığından, hemen ve hatasız döndürmelidir. HTTP çıktı olduğundan, Terminal çıktıda görebilirsiniz.

    ![Tablo satırı zaten gösteren terminal çıktı var.](media/azure-functions-lab-image33.png)

1. Bir birleşim değil yansıtacak biçimde URL'yi henüz test, gibi güncelleştirme **http://localhost:7071/api/Process/5/7**. Tablo satırı (beklendiği gibi) bulunamadı gösterir Terminal iletisinde unutmayın.

    ![Terminal çıkış gösteren yeni işlem](media/azure-functions-lab-image34.png)

1. Geri dönüp **Mac için Visual Studio** ve hata ayıklama oturumunu sonlandırın.

<!--
1. Finally, let's take a look at what it's like to work with multiple input records. Rather than specify a specific **TableRow**, you can request an **IQueryable<TableRow>** using the same attributes, and the runtime will fill it with the appropriate resource you need. Add the code below to create a **List** function that lists all items that currently exist in the Azure table we've been working with. Also note that we're specifying that the MIME type of the response is **application/json**, so the runtime will automatically render as JSON. 

    ```csharp
    [FunctionName("List")]
    public static HttpResponseMessage List(
        [HttpTrigger(AuthorizationLevel.Function, "get", Route = null)]
        HttpRequestMessage req,
        [Table("Results", "sums")]
        IQueryable<TableRow> table,
        TraceWriter log)
    {
        return req.CreateResponse(HttpStatusCode.OK, table, "application/json");
    }
    ```
1. Press **F5** to build and run the project.

1. In the browser tab, navigate to **http://localhost:7071/api/List**. This should pull down the list of all items in the Azure table and render it as JSON.

    ![](https://user-images.githubusercontent.com/3944468/29033725-be9d5a5e-7b4a-11e7-8b55-df0a200b6320.png)
-->

## <a name="summary"></a>Özet

Bu laboratuvarda, Mac için Visual Studio ile Azure işlevleri oluşturmaya başlamak nasıl öğrendiniz

