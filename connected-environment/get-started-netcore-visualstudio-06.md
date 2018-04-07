---
title: Visual Studio - adım 6 - ile bulutta Kubernetes kullanarak kapsayıcılarla .NET Core geliştirme ortamı oluşturmak team geliştirme hakkında bilgi edinin | Microsoft Docs
author: johnsta
ms.author: johnsta
ms.date: 04/05/2018
ms.topic: get-started-article
ms.technology: vsce-kubernetes
description: Kapsayıcılar ve Azure üzerinde mikro ile hızlı Kubernetes geliştirme
keywords: Docker, Kubernetes, Azure, AKS, Azure kapsayıcı hizmeti, kapsayıcıları
manager: ghogen
ms.openlocfilehash: d8d81afbe4fbf99c52107c8afc6f1eb9938de792
ms.sourcegitcommit: 3724338a5da5a6d75ba00452b0a607388b93ed0c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/06/2018
---
# <a name="get-started-on-connected-environment-with-net-core-and-visual-studio"></a>Bağlı ortam .NET Core ve Visual Studio ile çalışmaya başlama

Önceki adımda: [başka bir kapsayıcı çağırın](get-started-netcore-visualstudio-05.md)

## <a name="learn-about-team-development"></a>Takım geliştirme hakkında bilgi edinin

Şu ana kadar biz uygulama üzerinde çalışan tek Geliştirici değilmiş gibi biz bizim uygulamanın kodu çalıştırma. Bu bölümde, nasıl takım geliştirme ortamı bağlı kolaylaştırır öğreneceksiniz:
* Aynı geliştirme ortamında geliştiricilerin ekibi etkinleştirin.
* Her geliştirici kendi kodunda yalıtımı ve diğerleri parçalamak, korkusu olmadan yineleme destekler.
* Kod uçtan uca, kod tamamlama önce mocks oluşturmak veya bağımlılıkları benzetimini yapmak zorunda kalmadan sınayın.

## <a name="challenges-with-developing-microservices"></a>Mikro geliştirme ile zorlukları
Örnek uygulamamız şu anda çok karmaşık değil. Ancak gerçek geliştirme zorluklar yakında daha fazla hizmet eklenir ve geliştirme ekibi büyür olarak ortaya çıkan.

Kendinizi etkileşimde bulunan diğer hizmetler düzinelerce hizmetiyle çalışan görüntüleyin.

1. Her şey geliştirme için yerel olarak çalıştırmak için belirtmeyi gerçekçi hale gelebilir. Geliştirme makinenizde tüm uygulamayı çalıştırmak için yeterli kaynağı olmayabilir. Veya, belki de uygulamanız genel olarak erişilebilir olması gereken uç noktaları (örneğin, uygulamanızı bir Web kancası için bir SaaS uygulamadan yanıt verir).
1. Yalnızca üzerinde bağlı olan hizmetleri çalıştırmasına deneyin, ancak bu bağımlılıkları (örneğin, bağımlılıkları bağımlılıklarını) tam kapatması bilmeniz anlamına gelir. Veya, kolayca nasıl oluşturulacağı ve bunlar üzerinde işe yaramadı bağımlılıklarınızı çalıştırılamıyor bilmesinin bir konudur.
1. Bazı geliştiriciler benzetimini yapma veya birçok Hizmet bağımlılıklarını, mocking çözümlemelere. Bu bazen yardımcı olabilir, ancak bu mocks yönetme kendi geliştirme çaba kısa sürebilir. Ayrıca, geliştirme ortamınızı üretime çok farklı görmek için bu müşteri adayları ve zarif hatalar işi.
1. Bu, uçtan uca test herhangi bir türünü yapmak zor izler. Tümleştirme sınaması biz sorunları daha sonra geliştirme döngüsü göreceğiniz anlamına gelir sonrası tamamlama yalnızca gerçekçi oluşabilir.

    ![](media/microservices-challenges.png)

## <a name="work-in-a-shared-development-environment"></a>Paylaşılan geliştirme ortamında çalışma
Bağlı bir ortam ayarlayabilirsiniz bir *paylaşılan* Azure geliştirme ortamında. Her geliştirici yalnızca uygulamanın postalara odaklanabilirsiniz ve yinelemeli olarak geliştirebilirsiniz *önceden yürüttüğünüzde kodunuz* bir ortamda zaten tüm diğer hizmetler ve bunların senaryoları bağımlı bulut kaynakları içerir. Bağımlılıkları her zaman güncel ve geliştiriciler, üretim yansıtan bir şekilde çalışıyoruz.

## <a name="work-in-your-own-space"></a>Kendi alanında çalışır
Hizmetiniz için kod geliştirirken ve iade hazırsınız önce kodu genellikle iyi bir durumda olmayacaktır. Hala tekrarlayarak, test ve çözümlerle denemeler şekillendirme. Bağlı bir ortam sağlar kavramı bir **alanı**, yalıtım ve ekip üyelerinizin sapması korkusu olmadan iş sağlar.

Her ikisi de emin olmak için aşağıdakileri bizim `webfrontend` ve `mywebapi` hizmetleri bizim geliştirme ortamında çalışan **ve `mainline` alanı**.
1. Her iki hizmet için tüm F5/hata ayıklama oturumları kapatmak, ancak projeleri, Visual Studio Windows'da açık tutun.
2. Visual Studio penceresiyle geçin `mywebapi` proje ve hata ayıklayıcısı ekli hizmetini çalıştırmak için Ctrl + F5 tuşuna basın
3. Visual Studio penceresiyle geçin `webfrontend` proje ve de çalıştırmak için Ctrl + F5 tuşuna basın.

> [!Note]
Bazen, tarayıcınızın web sayfası, başlangıçta Ctrl + F5 aşağıdaki görüntülenir, sonra yenilemek gereklidir.

Ortak URL açar ve web uygulaması'na götürür herkes biz çalıştığı varsayılan kullanarak her iki hizmet aracılığıyla yazdığınız kodu yolunu çağırma `mainline` alanı. Şimdi biz geliştirmeye devam istediğinizi varsayalım `mywebapi` -nasıl biz bunu ve geliştirme ortamını kullanma diğer geliştiriciler kesme değil mi? Bunu yapmak için kendi alan boşaltın yaparız.

### <a name="create-a-new-space"></a>Yeni bir alanı oluşturma
Visual Studio içinde olacağı ek boşluk oluşturabilirsiniz kullanılır, F5 veya Ctrl + F5 hizmetinizi. Bir alanı istediğiniz herhangi bir şey çağırabilir ve esnek (örn. anlamı hakkında `sprint4` veya `demo`).

Yeni bir alan oluşturmak için aşağıdakileri yapın:
1. Visual Studio penceresiyle geçin `mywebapi` projesi.
2. Projeye sağ tıklayın **Çözüm Gezgini** seçip **özellikleri**.
3. Seçin **hata ayıklama** bağlı ortam ayarlarını görüntülemek için sol sekmesinde.
4. Buradan değiştirmek veya bağlı ortam ve/veya olacaktır alanı oluşturmak kullanılır, F5 veya Ctrl + F5'e. *Daha önce oluşturduğunuz bağlı ortam seçildiğinden emin olun*.
5. İçinde **alanı** açılan seçin **< yeni alan oluştur... >**.

    ![](images/Settings.png)

6. İçinde **alanı Ekle** iletişim türü için bir ad alanı ve tıklatın **Tamam**. Yeni alan için my adı ("tan"), böylece çalışıyorum içinde hangi alanı my eşlere tanımlanabilen kullanmış olduğunuz.

    ![](images/AddSpace.png)

7. Geliştirme ortamı ve proje özellikleri sayfasında seçtiğiniz yeni alanı görmelisiniz.

    ![](images/Settings2.png)

### <a name="update-code-for-mywebapi"></a>Kod için güncelleştirme *mywebapi*

1. İçinde `mywebapi` proje olun değiştirmek bir kod `string Get(int id)` dosyasındaki yöntemi `ValuesController.cs` gibi:
 
    ```csharp
    [HttpGet("{id}")]
    public string Get(int id)
    {
        return "mywebapi now says something new";
    }
    ```

2. Bu güncelleştirilmiş (zaten bir önce kümeden olabilir) kod bloğu bir kesme noktası ayarlayın.
3. Başlatmak için F5 isabet `mywebapi` hizmet. Bu hizmet geliştirme ortamınızı my durumda seçili alanını kullanarak başlatır `scott`.

Aşağıda, farklı alanları nasıl çalıştığını anlamanıza yardımcı olacak bir diyagram verilmiştir. Mavi yol üzerinden isteği gösterir `mainline` boşluk URL'sine eklenir, kullanılan varsayılan yol alanı. Yeşil yolu üzerinden isteği gösterir `scott` alanı.

![](media/Space-Routing.png)

Bu yerleşik yetenek bağlı ortamının yerlerini Hizmetleri'nde tam yığını yeniden oluşturmak her geliştirici gerek kalmadan paylaşılan bir ortamından kod uçtan uca test etmenizi sağlar. Bu yönlendirme, uygulama kodunuzda iletilecek yayma üstbilgileri bu kılavuzun önceki adımda gösterildiği gibi gerektirdiğini unutmayın.

## <a name="test-code-running-in-the-scott-space"></a>Test çalıştırma kodu `scott` alanı
Bizim yeni bir sürümü test etmek için `mywebapi` birlikte `webfrontend`, genel erişim noktası URL'si tarayıcınızı açın `webfrontend` (örneğin. https://webfrontend-teamenv.vsce.io) ve hakkında sayfasına gidin. "Merhaba webfrontend gelen ve mywebapi gelen Hello" özgün iletiyi görmeniz gerekir.

Şimdi, aşağıdakine benzer okunacak şekilde "tan-" bölümü URL'sini ekleyin https://scott-webfrontend-teamenv.vsce.io ve tarayıcıyı yenileyin. İçinde ayarladığınız kesme noktası, `mywebapi` proje isabet. Devam etmek için F5'e tıklayın ve tarayıcınızda yeni ileti artık görmelisiniz "Merhaba webfrontend ve mywebapi artık yeni bir şey diyor". Bunun nedeni, güncelleştirilmiş kodunuzdaki yolu `mywebapi` çalıştığı `scott` alanı.

> [!div class="nextstepaction"]
> [Özet](get-started-netcore-visualstudio-07.md)