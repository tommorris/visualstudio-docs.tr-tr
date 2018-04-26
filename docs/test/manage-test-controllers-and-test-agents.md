---
title: Visual Studio'da test aracılarını ve test denetleyicilerini Yönet
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 59c676424dbba0cea17670df5a99ac0f9dbbfb5f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="manage-test-controllers-and-test-agents"></a>Test denetleyicileri yönetmek ve test aracıları

Visual Studio testleri uzaktan çalıştırmak, testleri birden fazla makine arasında dağıtmak için kullanacağınız ya da yük testleri çalıştırmak, bir test denetleyicisi yapılandırmanız gerekir, test aracılarını ve test ayarları dosyası. Bu konu, test denetleyicilerini Yönet ve test aracılarını yükleyip ilk kez yapılandırdıktan sonra açıklar.

Laboratuvar ortamlarında testleri Microsoft Test Yöneticisi'ni kullanırsanız, test denetleyicileri ve bunların aracıları kullanarak yönettiğiniz **Test denetleyicisi Yöneticisi** içinde **Laboratuvar Merkezi** Microsoft Test Yöneticisi için. Bu konuda, yalnızca testleri çalıştırmak için Visual Studio kullanıyorsanız geçerlidir.

Yükleme ve test aracılarını yapılandırma ve test denetleyicileri Visual Studio ile testleri çalıştırma hakkında daha fazla bilgi için bkz: [yapılandırmak test aracılar ve denetleyiciler](../test/configure-test-agents-and-controllers-for-load-tests.md).

Test denetleyicisi ve tüm kayıtlı aracıları izlemek ve yapılandırmak için test projenizde çalıştırmak istediğiniz testleri içeren bir test ayarları dosyası olmalıdır. Test ayarları dosyasını açın, seçin **rol** ve **Test Denetleyicilerini Yönet** için açılan **denetleyicisi** alan.

Bir yük testi projesi için de seçebilirsiniz **Test Denetleyicilerini Yönet** gelen **yük testi** menüsü.

## <a name="add-a-test-agent-to-a-test-controller"></a>Bir Test aracısı Test denetleyicisine ekleme

Test aracısı, yeni yüklediğiniz test denetleyicisine eklemeniz gerekebilir veya test aracısı için farklı bir test denetleyicisi eklemek isteyebilirsiniz.

### <a name="to-add-a-test-agent-to-a-test-controller"></a>Test aracısı test denetleyicisine eklemek için

1. Seçin **Başlat** > **Test Aracısı Yapılandırma Aracı**.

     **Test aracısını Yapılandır** iletişim kutusu görüntülenir.

    > [!NOTE]
    > Bir test aracısı test denetleyicisine eklemek için önceden yüklü olması gerekir. Test aracısı yükleme hakkında daha fazla bilgi için bkz: [yükleme ve test aracılarını yapılandırma](../test/lab-management/install-configure-test-agents.md).

2. Şeklini değiştirmek istiyorsanız, test aracısı'nı çalıştırın, seçin **Çalıştırma Seçenekleri**.

     Çalıştırılacak nasıl test aracısı gitmek için iki seçenek sunulur:

     **Hizmet** masaüstü ile etkileşimde otomatikleştirilmiş testleri çalıştırmak yoksa gibi kodlanmış UI testleri veya video testinizi, altında çalıştığında kaydı oluşturma **olarak test aracısı'nı çalıştırın**seçin **hizmet**. Test aracısı hizmet olarak başlatılır. Seçin **sonraki**.

     Test aracısı hizmet olarak başlatıldığında, artık kullanıcı hakkındaki ayrıntıları girebilirsiniz.

    1. Bir ad girin **kullanıcı adı**.

    2. Parolayı girin **parola**.

        |**Önemli kullanıcı hesabı bilgileri**|
        |--------------------------------------------|
        |-Null parolalar kullanıcı hesapları için desteklenmez.|
        |-IntelliTrace Toplayıcı ya da ağ öykünmesini kullanmak istiyorsanız, kullanıcı hesabını Administrators grubunun bir üyesi olması gerekir.|
        |-Aracı kullanıcı adı test denetleyicisi izinleri gerektirir, eklemeyi deneyin Aracı hizmeti bulunmuyorsa.|
        |-Test denetleyicisi kullanmaya çalışıyor kullanıcı test denetleyicisinin kullanıcı hesabında olmalıdır veya denetleyiciye karşı testleri çalıştırmak mümkün olmayacaktır.|

     **Etkileşimli işlem** masaüstü ile etkileşimde otomatikleştirilmiş testleri çalıştırmak istiyorsanız, aşağıdaki gibi kodlanmış UI testleri veya video testinizi çalıştığında kaydı oluşturma, seçin **etkileşimli işlem**. Test aracısı, bir hizmet yerine etkileşimli bir işlem olarak başlatılacak.

     Bir işlem ve diğer seçenekleri test aracısı başladığında, sonraki sayfada kullanıcı ayrıntılarını girin.

    1. Bir ad girin **kullanıcı adı**.

    2. Parolayı girin **parola**.

        > [!NOTE]
        > Şu anda etkin kullanıcı olmayan farklı bir kullanıcı ile etkileşimli bir işlem olarak çalıştırmak için test aracısı yapılandırırsanız, bilgisayarı yeniden başlatın ve Aracısı'nı başlatmak bu farklı bir kullanıcı oturum açın. Ayrıca, null parolalar kullanıcı hesapları için desteklenmez. IntelliTrace Toplayıcı ya da ağ öykünmesini kullanmak istiyorsanız, kullanıcı hesabını Administrators grubunun bir üyesi olması gerekir.

        |**Önemli kullanıcı hesabı bilgileri**|
        |--------------------------------------------|
        |-Null parolalar kullanıcı hesapları için desteklenmez.|
        |-IntelliTrace veya ağ öykünmesi veri ve tanılama bağdaştırıcısını kullanmak istiyorsanız, kullanıcı hesabını Administrators grubunun bir üyesi olması gerekir. Test aracısı çalıştıran makinede en az ayrıcalıklı kullanıcı hesabı olan bir işletim sistemi varsa, çalıştırmak yönetici olarak da sahip (yükseltilmiş).|
        |-Aracı kullanıcı adı test denetleyicisi izinleri gerektirir, eklemeyi deneyin Aracı hizmeti bulunmuyorsa.|
        |-Test denetleyicisi kullanmaya çalışıyor kullanıcı test denetleyicisinin kullanıcı hesabında olmalıdır veya denetleyiciye karşı testleri çalıştırmak mümkün olmayacaktır.|

    3. Test aracısı olan bir bilgisayar yeniden başlatıldıktan sonra testleri çalıştırabilirsiniz emin olmak için bilgisayarı otomatik olarak test aracısı kullanmak oturum ayarlayabilirsiniz. Seçin **otomatik olarak oturum açma**. Bu kullanıcı adı ve parola kayıt defterinde şifrelenmiş biçimde depolar.

    4. Bu masaüstü ile etkileşimde olması gereken otomatikleştirilmiş testleri engelleyebilmesi yüzünden ekran koruyucusu devre dışı bırakıldığından emin olmak için seçin **olun ekran koruyucusu devre dışı**.

        > [!WARNING]
        > Otomatik olarak oturum açın veya ekran koruyucusu devre dışı bırakırsanız güvenlik riskleri vardır. Otomatik oturum açmayı etkinleştirerek, diğer kullanıcıların bu bilgisayarı başlatmak için ve otomatik oturum açan hesap kullanabilmek için etkinleştirin. Ekran koruyucu devre dışı bırakırsanız, bilgisayarda oturum açmak bir kullanıcı için bilgisayarın kilidini açmak için istemeyebilir. Bu herkes bilgisayara fiziksel erişimi makineye erişim sağlar. Bu özellikler bir bilgisayarda etkinleştirirseniz, bu bilgisayarların fiziksel olarak güvenli olduğundan emin olun. Örneğin, bu bilgisayarların fiziksel olarak güvenli bir laboratuar ortamında bulunur. (Silerseniz **olun ekran koruyucusu devre dışı**, ekran koruyucusu etkinleştirmez.)

3. Bu aracıyı farklı bir test denetleyicisi ile kaydetmek için seçin **test denetleyicisi ile kaydedin.** Ardından, test denetleyicisinin adını yazın **:** ve içinde kullandığınız bağlantı noktası numarasını **test aracısı aşağıdaki test denetleyicisiyle**. Örneğin, **agent1: 6901**.

    > [!NOTE]
    > Varsayılan bağlantı noktası numarası 6901'dir.

4. Değişikliklerinizi kaydetmek üzere seçim yapın **ayarlarını uygula**. Kapat **Yapılandırma Özeti** iletişim kutusunu ve ardından Kapat Test Aracısı Yapılandırma aracı.

> [!WARNING]
> Aracı şu anda başka bir test denetleyicisi üzerinde çalıştırmak için yapılandırılmışsa, test aracısı bu denetleyicisinden kaldırmanız gerekir.

## <a name="remove-a-test-agent-from-a-test-controller"></a>Test aracısı Test denetleyicisinden kaldırın

Kaldırılabilmesi için önce bir test aracısı çevrimdışı duruma ayarlanması gerekir.

> [!NOTE]
> Bir denetleyiciye bir laboratuar ortamında bir parçası olarak kaydedilen aracıları kaldırmak için bu yordamı kullanamazsınız. Bu aracıları bir denetleyicisinden kaldırmak için Microsoft Test Yöneticisi'ni kullanarak ortam kaldırmanız gerekir.

### <a name="to-remove-a-test-agent-from-a-test-controller"></a>Test aracısı test denetleyicisinden kaldırmak için

1. Test denetleyicisi takım projesi ile kayıtlı değilse, aşağıdaki adımları izleyin.

    1. Visual Studio'dan test projeniz için test ayarları dosyasını açın, seçin **rol** ve **Test Denetleyicilerini Yönet** için açılan **denetleyicisi** alan.

         **Test denetleyicisi yönetme** iletişim kutusu görüntülenir.

    2. İçinde **denetleyicisi** aşağı açılan listesinde, üzerinde ayarladığınız test denetleyicisi bilgisayarın adını yazın. Belirli bir test denetleyicisi önceden yönetilen değilse, adı listeden seçebilirsiniz.

    3. İçinde **aracıları** bölmesinde test aracısı adı seçin. Aracı çevrimiçiyse seçin **çevrimdışı.** Kaldırmak için seçin **kaldırmak**.

        > [!NOTE]
        > Yalnızca bir test aracısı kaldırma test denetleyicisinden keser. Test aracısı tamamen kaldırmak için kullanın **programlar ve Özellikler** test aracısı bilgisayardaki Denetim Masası.

2. Test denetleyicisi takım projesi ile kayıtlı değilse, Microsoft Test Yöneticisi'ni kullanarak aracısını kaldırın.

## <a name="change-the-settings-for-a-test-agent"></a>Test aracısı ayarlarını değiştirme

Test aracısı durumu aşağıdaki değerlerden biri olabilir:

|Durum|Açıklama|
|------------|-----------------|
|Çalışan testi|Testleri çalıştırma|
|Hazır|Testleri çalıştırmak veya veri ve tanılama toplamak kullanılabilir|
|Çevrimdışı|Testleri çalıştırmak veya veri ve tanılama toplamak için kullanılamaz|
|bağlantısı kesilmiş|Test aracısı başlatılmadı|

Durum ve aşağıdaki yordamları kullanarak test aracısı için diğer ayarları değiştirebilirsiniz.

### <a name="to-change-the-settings-of-a-test-agent"></a>Test aracısı ayarlarını değiştirmek için

> [!NOTE]
> Bir takım projesi ile kayıtlı bir test denetleyicisine test aracısı kaydettiyseniz, Microsoft Test Yöneticisi'nde ayarları değiştirin.

1. Test denetleyicisi ve bir yük testi için kayıtlı tüm aracıları izlemek ve yapılandırmak için tercih **yük testi** Visual Studio menüsünde ve ardından **Test Denetleyicilerini Yönet**. Diğer herhangi bir test için Visual Studio'da test projeniz için test ayarları dosyasını açın, seçin **rol** ve **Test Denetleyicilerini Yönet** için açılan **denetleyicisi**alan.

   **Yönetmek Test denetleyicisi** iletişim kutusu açılır.

1. Test aracıları test denetleyicisi listesinde değiştirmek istediğiniz test denetleyicisi adını seçin. Test denetleyicisi listede görünmüyorsa, test denetleyicisi doğru şekilde kaydedildiğini denetleyin. Aşağıdaki yordam bir test denetleyicisi yapılandırma hakkında daha fazla bilgi için bkz.

1. (İsteğe bağlı) İçinde **Test aracıları** bölmesinde, özelliklerini değiştirmek istediğiniz test aracısı bilgisayarı seçin.

1. Seçin **özellikleri**.

1. Aşağıdaki test aracısı özelliklerini gerektiği gibi değiştirin:

|Test aracısı özelliği|Açıklama|
|-------------------------|-----------------|
|**Ağırlığı**|Test aracıları farklı performans düzeyleriyle kullandığınızda yükü dağıtmak için kullanılır. Örneğin, bir test aracısı 100 ağırlığı ile 50 ağırlığı ile bir test aracısı olarak iki kez yük alır.|
|**IP geçişi**|IP geçişi yapılandırmak için kullanılır. IP geçişi, bir dizi IP adreslerini kullanarak bir sunucuya istek göndermek bir test aracısı sağlar. Bu, farklı istemci bilgisayarlardan gelen çağrıların benzetimini yapar.<br /><br /> IP geçişi, bir Web grubu yük testlerini erişiyorsa önemlidir. Çoğu yük dengeleyicileri istemcinin IP adresini kullanarak bir istemci belirli bir Web sunucusu arasında benzeşim kurar. Tek bir istemciden gelen tüm istekleri görünmesini, yük dengeleyici yükü dengelemez. Web grubunda iyi Yük Dengeleme elde etmek için istekleri bir dizi IP adreslerinden gelen emin olun. **Not:** bir ağ bağdaştırıcı belirtin veya kullanmak **(Tümü Atanmamış)** otomatik olarak şu anda kullanılmayan birini seçmek için. <br /><br /> IP geçiş özelliğini kullanmak için Visual Studio Test Aracısı hizmeti bu aracı bilgisayar için Yöneticiler grubunun bir kullanıcı olarak çalışmalıdır. Bu kullanıcı aracısı kurulumu sırasında seçilir, ancak hizmet özelliklerini değiştirme ve yeniden başlatmayı değiştirilebilir.<br /><br /> IP geçişinin düzgün çalıştığını doğrulamak için IIS Web sunucusunda günlüğe kaydetmeyi etkinleştirmek için isteklerin yapılandırdığınız IP adreslerinden geldiğini doğrulamak için IIS günlüğü işlevini kullanın.|
|**Öznitelikler**|Test aracısı seçiminde kullanılan ad/değer çiftleri kümesi. Örneğin, bir test belirli bir işletim sistemi gerektirebilir. Öznitelikler ekleyebilirsiniz **rolleri** sekmesi test öznitelikleri eşleşen bir test aracısı seçmek için ayarları dosyası ve bunlar kullanılabilir. Birden çok makineye bir sınama çalıştırmak istiyorsanız test ayarları rolünde testleri çalıştırmak için yapılandırılmış bir öznitelik oluşturun ve o role kullanmak istediğiniz her test aracısı eşleşen bir öznitelik yapılandırmasına... **Not:** Bu ayar yalnızca bu öznitelikler yalnızca Visual Studio için test ayarları kullanıldığından, bir takım projesine kayıtlı olmayan bir test denetleyicisi ile kaydedilen test aracıları için kullanılabilir.|

Değişiklikler hemen yürürlüğe girer, ancak çalışan testleri etkilemez Aracısı ağırlığı ve test aracısı özniteliği sınayın. IP adresi aralığı, test denetleyicisi yeniden başlatıldıktan sonra etkinleşir.

(İsteğe bağlı) Test aracısı durumunu değiştirmek için listedeki Aracısı'nı seçin ve aracı mevcut duruma dayanarak kullanılabilir seçeneklerden eylemi seçin.

> [!NOTE]
> Test aracınızı bir işlem olarak çalışıyorsa, test aracınızı yüklendiği bilgisayarda çalışan bildirim alanında simgesinden test aracısı durumunu yönetin. Bu test aracısı durumunu gösterir. Başlatma, durdurma veya bu aracı kullanarak bir işlem olarak çalışıyorsa, aracıyı yeniden başlatın. Test aracısı çalışır durumda değilse bir işlem olarak başlatmak için tercih **Başlat**, **tüm programlar**, **Microsoft Visual Studio** , **Microsoft Visual Studio Test Aracı**. Bu bildirim alanı simgesini ekler.

## <a name="configure-a-test-controller"></a>Test denetleyicisi yapılandırmak

Test denetleyicisi yapılandırmak için kullanmanız gerekir **Takım Test denetleyicisi yapılandırma aracı**. Test denetleyicisi yapılandırdığınızda, farklı bir takım projesi koleksiyonu ile test denetleyicisi kaydetmek veya bir takım projesi koleksiyonu, test denetleyicisinden kaydı silinemedi.

Team Foundation Server projeniz ile test denetleyicisi kaydetmek istiyorsanız, test denetleyicisi hizmeti için kullandığınız hesabın takım projesi koleksiyonu için proje koleksiyonu Test hizmet hesapları grubunun bir üyesi olmanız gerekir veya test denetleyicisi yapılandırma aracını çalıştırmak için kullandığınız hesap proje koleksiyonu yöneticisi olmalıdır.

> [!NOTE]
> Bir takım projesi koleksiyonu mevcut ortamlarına sahip bir takım projesi koleksiyonu test denetleyicisinden kaydı, ortamları hala bu takım projesi koleksiyonu taşıdıysanız korunur ve bu taşınan takım test denetleyicisine yeniden kaydolun Proje koleksiyonu.

### <a name="to-configure-a-test-controller"></a>Bir test denetleyicisi yapılandırmak için

1. Herhangi bir zamanda test denetleyicinizi yapılandırmak üzere aracı çalıştırmak için tercih **Başlat** > **tüm programlar** >  **Microsoft Visual Studio**  >  **Microsoft Visual Studio Test denetleyicisi yapılandırma aracı**.

     **Test denetleyicisi yapılandırma** iletişim kutusu görüntülenir.

2. Test denetleyicisi hizmetiniz için oturum açma hesabı olarak kullanılacak olan kullanıcıyı seçin.

    > [!NOTE]
    > Null parolalar kullanıcı hesapları için desteklenmez.

4. (İsteğe bağlı) Bir laboratuvar ortamında test denetleyicinizi kullanmak istemediğiniz, ancak yalnızca çalıştırmak için Visual Studio'dan temizleyin testleri **kaydetmek takım projesi koleksiyonu ile**.

5. (İsteğe bağlı) Yük testi için test denetleyicisi yapılandırmak için seçin **yük testi için yapılandırma**. SQL Server örneğinizi yazın **aşağıdaki SQL Server örneğinde veritabanı oluşturma yük testi sonuçlarını**.

> [!NOTE]
> Daha fazla sorun giderme test denetleyicileri hakkında bilgi için bkz: [yüklemek ve test aracılarını yapılandırma](../test/lab-management/install-configure-test-agents.md).

## <a name="manage-your-agents-when-you-run-your-tests-with-a-test-controller"></a>Bir Test denetleyicisi ile testlerinizi çalıştırdığınızda aracılarınızı yönetme

Visual Studio için test ayarlarınız, uygulamanız için rolleri eklediğinizde, her rollerinizi Aracısı özellikleri ekleyebilirsiniz. Bu, hangi test aracılarını bu rol için kullanılabilir olduğunu belirler. Kullanarak testlerinizi çalıştırdığınızda bu test ayarları, test ayarları için seçilen test denetleyicisi gerekli aracıların kullanılabilirliğini belirler. Aracı kullanılabilirliği belirlendiğinde oluşabilecek aşağıdaki durumlarda bunlar:

-   Testleri çalıştırmak zorunda rolü için kullanılabilir bir aracı yoktur. Testlerinizi çalıştırılamaz. Aşağıdaki eylemlerden birini gerçekleştirin ve testleri yeniden çalıştırın:

    -   Testleri çalıştırmak bu rol için kullanılabilir hale gelmesi bir aracı için bekleyebilirsiniz.

    -   Çevrimdışı olan aracılar varsa, bu rol için kullanılabilir, böylece kullanılabilir, aracı yeniden başlatabilirsiniz.

    -   Bu rol için doğru aracı özellikleriyle başka bir aracı test denetleyicisine ekleyebilirsiniz.

    -   Kullanmak istediğiniz diğer aracıları etkinleştirmek için test ayarları bu rol için aracı özelliklerini değiştirebilirsiniz.

-   Tanılama veri bağdaştırıcıları çalıştıran bir veya daha fazla rol için bir aracı yok. Testlerinizi çalıştırılabilir, ancak tanılama veri bağdaştırıcısı çalıştırılamaz. Tanılama veri bağdaştırıcısı olmadan testleri çalıştırabilirsiniz veya aşağıdaki eylemlerden birini gerçekleştirin ve testleri yeniden çalıştırın:

    -   Bu roller için kullanılabilir hale gelmesi bir aracı için bekleyebilirsiniz.

    -   Çevrimdışı olan aracılar varsa bu rol için kullanılabilir, aracının durumunu Online'dan için değiştirmeniz gerekir **Test denetleyicisi yönetme** üzerinde **Test** menüsü. Ayrıca, denetleyicisinden kestiyseniz aracıyı yeniden başlatmanız gerekebilir.

    -   Bu test için gereksinim duyabileceğiniz tüm aracıları testleri çalıştırmakla meşgul olmadığından emin olun. Tüm aracılardan durumunu kontrol edebilirsiniz **Test denetleyicisi yönetme** üzerinde **Test** menüsü.

    -   Rolü için doğru aracı özellikleriyle başka bir aracı test denetleyicisine ekleyebilirsiniz.

    -   Kullanmak istediğiniz diğer aracıları etkinleştirmek için test ayarları rolünde aracı özelliklerini değiştirebilirsiniz.

## <a name="load-tests-from-delay-signed-assemblies"></a>Gecikmeli İmzalanmış Derlemelerden yük testleri

Test denetleyicisi ve test aracıları yalnızca kesinlikle imzalı derlemeler ya da imzasız derlemeler test derlemeleri yükleyebilir. Bazı test derlemeleri gecikme-üretim derlemelerine uygulama erişimi gerektiğinden oturum açtınız. Ancak, çünkü bunlar yalnızca test derlemeleri olan ve olmayan dağıtılan bu derlemeler kesinlikle imzalanmamış. Güçlü ad doğrulaması burada derlemeyi dahil olmak üzere test denetleyicisi makinesinde yüklenir tüm makinelerde bu derlemeler için devre dışı bırakmalısınız gecikmeli imzalanmış oldukları için bu derlemeler yüklenemiyor. Gecikmeli imzalanmış doğrulamayı devre dışı bırakmak için sn.exe kullanın. Ortak anahtar belirteci, güçlü ad doğrulaması atlanacak istenen gecikmeli imzalanmış derlemenin de dahil edilmesi gerekebilir.

Gecikmeli imzalanmış doğrulamayı devre dışı bırakmak için sn.exe (tanımlayıcı ad aracı) kullanın.

Bu yalnızca, belirtilen derleme için tanımlayıcı ad doğrulaması komutu çalıştırdığınız bilgisayarda devre dışı bırakır. Yalnızca yeterli izinlere sahipseniz, bunu yapabilirsiniz.

Test çalışması tamamlandıktan sonra SN.exe komutunu kullanarak Gecikmeli İmza doğrulamasını yeniden etkinleştirin.

Devre dışı bırakın ve imza doğrulamasını yeniden etkinleştirmek için önerilen yol, betiklerde SN.exe komutlarını kullanmaktır. Kurulum betik doğrulamayı devre dışı bırakmak ve temizleme betiğini doğrulama yeniden etkinleştirin.

## <a name="see-also"></a>Ayrıca bkz.

- [Test aracılarını yükleme ve yapılandırma](../test/lab-management/install-configure-test-agents.md)