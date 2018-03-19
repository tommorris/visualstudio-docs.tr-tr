---
title: "Visual Studio'da dağıtılmış yük testi için Test ayarı oluşturma | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- test settings, for distributed load tests
ms.assetid: b63d4b71-3b74-4872-b2d1-f0bd1a9a8544
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 38bcbe49850929105199cef360956f29f22a8d0c
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-create-a-test-setting-for-a-distributed-load-test"></a>Nasıl yapılır: Dağıtılmış Yük Testi için Test Ayarı Oluşturma

Yapılandırma *test ayarları* bu testleri test aracılarını kullanarak birden fazla makine arasında dağıtmak ve test denetleyicileri yükleme testleri için. Kullanmak için test ayarları da yapılandırabilirsiniz *tanılama veri bağdaştırıcıları*, toplamak istediğiniz veri türlerini belirtmek veya de nasıl Visual Studio'dan yük testlerini çalıştırdığınızda test makinelerini etkiler.

Örneğin, kod performans dökümünü toplamak için ASP.NET Profil oluşturucu tanılama veri bağdaştırıcısı kullanabilirsiniz. Ayrıca, tanılama veri bağdaştırıcıları olası performans sorunlarını test makinesindeki benzetimini yapmak veya kullanılabilir sistem belleğini azaltmak için kullanılabilir.

Visual Studio için test ayarları bir dosyada depolanır. Test ayarlarını her rol hakkında aşağıdaki bilgileri tanımlayın:

-   Test altındaki uygulamanız için gerekli olan roller kümesi

-   Testleri çalıştırmak için kullanılacak rolü

-   Her rol için kullanmak için tanılama veri bağdaştırıcıları

Testlerinizi çalıştırdığınızda, o belirli test çalışması için gerekli bağlı olarak etkin test ayarlarını kullanmak için test ayarlarını seçin. Test ayarları dosyası çözümünüzün bir parçası olarak depolanır. Dosya adı uzantısına sahip *.testsettings*.

Bir Web performansı ve yük testi bir çözüme proje eklediğinizde bir *Default.testsettings* dosyası oluşturulur. Dosyayı otomatik olarak altında çözüme eklenen **çözüm öğeleri** klasör. Bu dosya testlerinizi tanılama veri bağdaştırıcısı olmadan yerel olarak çalışır. Başka bir tane eklemek *.testsettings* dosya ya da Düzenle bir *.testsettings* tanılama veri bağdaştırıcıları belirtmek ve test denetleyicileri için dosya.

Test denetleyicisi test ayarlarınızda her rol için kullanılan aracılara sahip olacaktır. Test denetleyicileri ve test aracıları hakkında daha fazla bilgi için bkz: [yönetme Test denetleyicilerini ve Test aracıları Visual Studio ile](../test/manage-test-controllers-and-test-agents.md).

Oluşturma ve çözümünüzdeki Visual Studio'dan çalıştırmayı planladığınız yük testleri için test ayarları kaldırmak için aşağıdaki adımları izleyin.

## <a name="create-a-test-setting-for-a-distributed-load-test"></a>Dağıtılmış yük testi için Test ayarı oluşturma

### <a name="to-add-a-test-settings-for-a-distributed-load-test"></a>Dağıtılmış yük testi için test ayarları eklemek için

1.  Çözüm Gezgini'nde sağ **çözüm öğeleri**, işaret **Ekle**ve ardından **yeni öğe**.

     **Yeni Öğe Ekle** iletişim kutusu görüntülenir.

2.  İçinde **yüklü şablonlar** bölmesinde seçin **Test ayarlarını**.

3.  (İsteğe bağlı) İçinde **adı** kutusunda, test ayarları dosyası adını değiştirin.

4.  Seçin **eklemek**.

     Yeni test ayarları dosyasını Çözüm Gezgini'nde altında görünür **çözüm öğeleri** klasör.

    > [!NOTE]
    > Visual Studio Enterprise görüntüler test ayarları listesi test ayarları dosyalarında listesinden türetilen **çözüm öğeleri** klasör. Test ayarları dosyalarında çözüm öğeleri klasörü kullandığınızda Örneğin, görüntülenen **Etkin Test ayarlarını seçin** seçeneği **Test** menüsü. Bu çözüm hiyerarşinizdeki başka bir konuma test ayarları dosyasını taşırsanız, onu artık Visual Studio tümleşik geliştirme ortamında bir test ayarı olarak kullanılabileceğini anlamına gelir.

5.  **Test ayarlarını** iletişim kutusu görüntülenir. **Genel** sayfa seçilidir.

     Şimdi, düzenleme ve test ayarları değerlerini kaydedin.

    > [!NOTE]
    > Oluşturduğunuz her test ayarları için bir seçenek olarak listeleniyor **Etkin Test ayarlarını seçin** ve **Test Ayarlarını Düzenle** seçeneklerinden **Test** menüsü.

6.  Altında **adı**, test ayarları için bir ad yazın.

7.  (İsteğe bağlı) Altında **açıklama**, diğer takım üyeleri ne işe yaradığını bilmesi için test ayarında bir açıklama yazın.

8.  (İsteğe bağlı) Test çalışmaları için varsayılan adlandırma şeması seçmek için **adlandırma şeması varsayılan**. Adlandırma düzeninizi tanımlamak için seçin **kullanıcı tanımlı düzeni** ve istediğiniz metni yazın **önek metin**. Test çalışması adına tarih ve saat damgası eklemek için seçin **Append tarih-saat damgası**.

9. Seçin **rolleri**.

     **Rolleri** sayfası görüntülenir.

     ![Test ayarı rol](../test/media/load_testtestrole.png "Load_TestTestRole")

10. Testlerinizi uzaktan çalıştırmak veya testlerinizi uzaktan çalıştırmak ve uzaktan veri toplamak için kullanın **Test yürütme yöntemi** açılır ve select **uzaktan yürütme**.

11. Kullanım **denetleyicisi** test aracıları için bir test denetleyicisi seçmek için açılır **denetleyicisi** testleri çalıştırma veya veri toplamak için kullanılır.

    > [!NOTE]
    > Denetleyici eklediğiniz ilk kez kullanıyorsanız, aşağı açılan listesinde hiçbir denetleyicileri listelenir. Liste diğer test ayarlarında belirttiğiniz önceki denetleyiciler tarafından doldurulur. Denetleyicinin adı kutusuna yazın (örneğin, **TestControllerMachine1**).

12. Testleri çalıştırmak ve verileri toplamak için altında kullanmak istediğiniz rolleri eklemek için **rolleri**, seçin **Ekle**.

13. Rolü için bir ad yazın **adı** sütun. Örneğin, rol "Web sunucusu" olabilir.

14. 12 ve ihtiyaç duyduğunuz tüm rolleri Ekle-13 arası adımları yineleyin.

     Her rol test denetleyicisi tarafından yönetilen bir test aracısı kullanır.

15. Testleri çalıştırma ve ardından istediğiniz rolü seçin **testleri çalıştırmak için rol olarak ayarla**.

    > [!IMPORTANT]
    > Oluşturduğunuz ve tanımladığınız diğer rolleri testler çalışmaz, ancak yalnızca veri ve roller için belirttiğiniz tanılama bağdaştırıcılarını göre veri toplamak için kullanılan **veri ve tanılama** sayfası.

16. Bir rol için kullanılabilecek aracıları sınırlamak için rolü seçin ve ardından **Ekle** altında araç çubuğundaki **seçilen rol için aracı öznitelikleri**e.

     **Aracı seçim kuralı** iletişim kutusu görüntülenir.

     Adı yazın **öznitelik adı** ve değer **öznitelik değeri**ve ardından **Tamam**. Gereksinim duyduğunuz kadar çok sayıda öznitelik ekleyin.

     Örneğin, "RAM > 16 değerini"True"veya"False"birden fazla 16 GB belleği olan test aracı makinelerinde filtrelemek için olan GB" adlı bir öznitelik ekleyebilirsiniz. Aynı öznitelik için bir veya daha fazla test aracılarını uygulamak için Test Denetleyici Yönet iletişim kutusunu kullanın. Daha fazla bilgi için bkz: [yönetme Test denetleyicileri ve Test aracılarını Visual Studio ile](../test/manage-test-controllers-and-test-agents.md).

17. Seçin **veri ve tanılama**.

     **Veri ve tanılama** sayfası görüntülenir.

     ![Test ayarı veri ve tanılama](../test/media/load_testtest.png "Load_TestTest")

18. İçinde **veri ve tanılama** sayfasında, ne rolü seçerek tanımlarsınız *tanılama veri bağdaştırıcıları* rolü verileri toplamak için kullanır. Bu nedenle, bir veya daha fazla veri ve tanılama bağdaştırıcılarını rol için etkinleştirilirse, test denetleyicisi belirtilen veri ve tanılama bağdaştırıcıları rolü için tanımlı özniteliklerini temel alarak verileri toplamak için uygun bir test aracısı makine seçin. Veri ve her rol için toplamak istediğiniz tanılama veri bağdaştırıcıları seçmek için rolü seçin. Her rol için tanılama veri bağdaştırıcıları testlerin ihtiyaçlarına göre seçin. Her rol için seçtiğiniz her tanılama veri bağdaştırıcısı yapılandırmak için tercih **yapılandırma**.

     **Roller ve tanılama veri bağdaştırıcıları örneği:**

     Örneğin, bir öznitelik "" True"ve"RAM > 16 GB"olarak ayarlanan öznitelikle" SQL Server"adlı bir sunucu rolü ayarlanan SQL kullanır", "Masaüstü İstemcisi" adlı bir istemci rolü oluşturabilirsiniz. "Masaüstü İstemcisi" seçerek testleri çalıştırırsınız belirtirseniz **testleri çalıştırmak için rol olarak ayarla** içinde **rolleri** sayfasında, test denetleyicisi özniteliğini içeren test aracıları olan makineleri seçebilir "" True"üzerinde testleri çalıştırmak ayarladığı SQL kullanır". Test denetleyicisi aynı zamanda "RAM > 16 yalnızca veri ve rolüne dahil tanılama bağdaştırıcıları tarafından tanımlanan veri toplamak için GB" özniteliğini içeren test aracıları olan SQL sunucu makinelerini seçer. "Masaüstü İstemcisi" test aracısı, verileri ve tanılama bağdaştırıcıları bu rol için çok seçerseniz, çalıştığı makinelerin veri toplayabilirsiniz.

     Her tanılama veri bağdaştırıcısı ve nasıl yapılandırılacağı hakkında daha fazla ayrıntı için aşağıdaki tabloda ilişkilendirilen konuyu görüntüleyebilirsiniz.

     Tanılama veri bağdaştırıcıları hakkında daha fazla bilgi için bkz: [toplamak tanılama bilgileri Test ayarlarını kullanarak](../test/collect-diagnostic-information-using-test-settings.md).

     **Yük testleri için tanılama veri bağdaştırıcıları**

    |Tanılama veri bağdaştırıcısı|Yük testlerinde kullanma|İlişkili konu|
    |-----------------------------|-------------------------|----------------------|
    |**IntelliTrace ve Test etkisi için ASP.NET İstemci Proxy:** bu proxy, IntelliTrace ve Test etkisi tanılama veri bağdaştırıcıları için bir Web sunucusu istemciden gelen http çağrıları hakkında bilgi toplamanıza olanak tanır.|![Bilgi simgesi](../test/media/vc364f4.gif)<br /><br /> Test aracısı makineler sistem bilgilerini toplamak için belirli bir gereksiniminiz yoksa, bu bağdaştırıcı dahil etmeyin. **Dikkat:** yük testlerinde IntelliTrace bağdaştırıcısının kullanımını toplanan verileri büyük miktarda nedeniyle oluşan sorunlar nedeniyle önermiyoruz. <br /><br /> Yük testleri kullanarak test etkisi verilerini toplanmaz.||
    |**IntelliTrace:** bir günlük dosyasında depolanan özel Tanılama izleme bilgilerini yapılandırabilirsiniz. Bir günlük dosyası .tdlog uzantısına sahiptir. Başarısız test ve bir test adımı çalıştırdığınızda, bir hata oluşturabilirsiniz. Tanılama izleme içeren bir günlük dosyası bu hataya otomatik olarak eklenir. Günlük dosyasında toplanan verileri yeniden oluşturun ve kodda bir hata tanımak için gerekli olan zamanı azaltarak hata ayıklama verimliliğini artırır. Bu günlüğünden dosya yerel oturumun başka bir bilgisayarda yeniden oluşturulabilir. Bu hatayı çoğaltılamayan riskini azaltır.<br /><br /> Daha fazla bilgi için bkz: [toplamak IntelliTrace verilerini](../test/how-to-collect-intellitrace-data-to-help-debug-difficult-issues.md).|![Önemli simgesi](../test/media/vc364f3.gif)<br /><br /> Yük testlerinde IntelliTrace bağdaştırıcısının kullanımını büyük toplanan ve günlüğe kaydedilen veri miktarı nedeniyle oluşan sorunlar nedeniyle önermiyoruz. IntelliTrace bağdaştırıcısı uzun çalıştırmayın ve birçok test aracılarını kullanmayın yük testlerinde kullanma girişimi.|[Nasıl yapılır: hata ayıklama zorluklarını çözmeye yardımcı olması için IntelliTrace verilerini toplama](../test/how-to-collect-intellitrace-data-to-help-debug-difficult-issues.md)|
    |**ASP.NET Profil Oluşturucu:** ASP.NET Web uygulamaları üzerinde performans verilerini toplayan ASP.NET profil oluşturma, içeren bir test ayarı oluşturabilirsiniz.|Bir geliştirme Web sunucusuna karşı çalışmaması ASP.NET Profil oluşturucu tanılama veri bağdaştırıcısı Internet Information Services (IIS) işlem profilleri. Yük testlerini Web sitesinde profil için IIS çalıştıran makinede bir test aracısı yüklemeniz gerekir. Test aracısı yük oluşturmayacak ancak yalnızca koleksiyon aracı görüntülenir. Daha fazla bilgi için bkz: [yüklemek ve test aracılarını yapılandırma](../test/lab-management/install-configure-test-agents.md).|[Nasıl yapılır: Test ayarlarını kullanarak yük testleri için ASP.NET Profil Oluşturucu yapılandırma](../test/how-to-configure-aspnet-profiler-for-load-tests-using-test-settings.md)|
    |**Olay günlüğü:** test sonuçlarında bulunan olay günlüğü toplama, dahil etmek için test ayarı yapılandırabilirsiniz.||[Nasıl yapılır: Test ayarlarını kullanarak olay günlüğü koleksiyonunu yapılandırma](http://msdn.microsoft.com/en-us/48d67891-6018-4549-83e3-213d5d824a02)|
    |**Ağ öykünmesi:** test ayarı kullanarak, test yapay bir ağ yükü yerleştirmek istediğiniz belirtebilirsiniz. Ağ öykünmesi çevirmeli gibi belirli bir ağ bağlantısı hızı öykünen tarafından iletişimi makine etkiler. **Not:** ağ öykünmesi, ağ bağlantı hızını artırmak için kullanılamaz.|Ağ öykünmesi bağdaştırıcısı yük testleri tarafından göz ardı edilir. Bunun yerine, yük testleri yük testi senaryosuna ağ karışımı belirtilen ayarları kullanın.<br /><br /> Daha fazla bilgi için bkz: [sanal ağ türlerini belirtme](../test/specify-virtual-network-types-in-a-load-test-scenario.md).||
    |**Sistem bilgileri:** sistem bilgisi tanılama ve veri toplayıcı üzerinde çalıştırıldığı makineler hakkında sistem bilgisi eklemek için bir test ayarı ayarlanabilir. Sistem bilgileri, bir test ayarı kullanarak test sonuçlarında belirtilir.|![Bilgi simgesi](../test/media/vc364f4.gif)<br /><br /> Yükleme aracılarını ve test sisteminde sistem bilgileri toplayabilir.|Yapılandırma, bu bilgileri toplamak için gereklidir.|
    |**Test Etkisi:** hakkında uygulama kodunuzun yöntemlerinin kullanıldığını bir test çalışması çalıştırdığınızda bilgi toplayabilirsiniz. Bu değişiklikleri ile hangi testlerin etkilendiğini belirlemek için geliştiriciler tarafından yapılan değişiklikleri uygulama koduna birlikte kullanılabilir.|Test etkisi verilerini Yük testleri ile toplanmaz.||
    |**Video Kaydedici:** bir otomatik test çalıştırdığınızda masaüstü oturumunuzun bir video kaydı oluşturabilirsiniz. Kodlanmış UI testi için kullanıcı eylemlerini görüntülemek için yararlı olabilir. Video diğer takım üyeleri yeniden oluşturması zor olan uygulama sorunlarını gidermeye yardımcı olabilir. **Not:** aracı etkileşimli işlem modunda çalışmadığı sürece testleri uzaktan çalıştırırken video kaydedici çalışmaz.|![Önemli simgesi](../test/media/vc364f3.gif) **Uyarı:** Video Kaydedici bağdaştırıcısı kullanımını yük testleri için önermiyoruz.|[Nasıl yapılır: Test ayarlarını kullanarak testler sırasında ekran ve ses kayıtlarını içerir](../test/how-to-include-recordings-of-the-screen-and-voice-during-tests.md)|

19. Seçin **dağıtım**.

     **Dağıtım** sayfası görüntülenir.

20. Dağıtım testlerinizi her zaman için ayrı bir dizin oluşturmak için seçin **dağıtımı etkinleştir**.

    > [!NOTE]
    > Bunu yaparsanız, testlerinizi çalıştırdığınızda uygulamanızı yapılandırmaya devam edebilirsiniz.

21. Testleri çalıştırmak için kullandığınız dizine bir dosya eklemek için **Dosya Ekle**ve ardından eklemek istediğiniz dosyayı seçin.

    > [!NOTE]
    > Bir yük testlerini çalıştırdığınızda, Eklenti derlemeleri ve veri dosyalarını karşıya yüklenen dosyaların otomatik olarak dağıtılır.

22. Testleri çalıştırmak için kullandığınız dizine bir dizin eklemek için **Dizin Ekle** ve ardından eklemek istediğiniz dizini seçin.

23. Önce ve sonra testlerinizi komut dosyaları çalıştırmak için tercih **Kurulum ve temizleme betikleri**.

     **Kurulum ve temizleme betikleri** sayfası görüntülenir.

    1.  Komut dosyası konumunu yazın **Kurulum komut dosyası** veya üç nokta seçin (**...** ) Kurulum komut dosyası bulunamadı.

    2.  Komut dosyası konumunu yazın **temizleme betiğini** veya üç nokta seçin (**...** ) temizleme betiğini bulmak için.

24. Farklı bir ana bilgisayar kullanarak testleri çalıştırmak için tercih **ana**.

    1.  İçinde **ana bilgisayar türü**, doğrulayın **varsayılan** seçilir.

        > [!NOTE]
        > **ASP.NET** içinde **ana bilgisayar türü** yük testlerinde desteklenmez.

    2.  Test çalıştırma 32 bit veya 64-bit işlemde açılan 32 bit veya 64 bit işlemleri olarak çalışacak şekilde yük testinde Web performansı ve birim testleri istediğinizi seçmek için kullanın.

        > [!NOTE]
        > Maksimum esneklik için Web performans derlemek ve test projeleri kullanarak yük **herhangi bir CPU** yapılandırma. Ardından, 32 bit ve 64-bit aracısında çalıştırabilirsiniz. Derleme Web performansı ve yük test projeleri kullanarak **64-bit** yapılandırma hiçbir avantajı sunar.

25. (İsteğe bağlı) Her bir test çalışması ve bireysel testler için süreyi sınırlamak için tercih **Test zaman aşımları.**

    1.  Bir süre sınırı aşıldığında testi durdurmayı seçin **toplam süreyi aşarsa testi iptal** ve bu sınır için bir değer yazın.

    2.  Bir süre sınırı aşıldığında, bir test başarısız olarak işaretleyin **bir test yürütme süresi aşarsa, başarısız olarak işaretle**ve bu sınır için bir değer yazın.

26. Atla **birim testi**. Yük testleri, bu ayarları kullanmayın.

27. Atla **Web testi**. Yük testleri, bu ayarları kullanmayın.

28. Test ayarlarını kaydetmek üzere seçim yapın **Kaydet**. İstediğiniz dosyanın adını yazın **nesne adı**.

    > [!NOTE]
    > Test ayarlarınızı değiştirmeniz gerekiyorsa seçin **Test** ve ardından **Test Ayarlarını Düzenle** ve oluşturduğunuz test ayarlarını'nın üzerine gelin.

### <a name="to-remove-a-test-settings-from-your-solution"></a>Test ayarları çözümünüzden kaldırmak için

Çözüm Gezgini'nde çözüm öğeleri klasörü altında kaldırın ve ardından istediğiniz test ayarlarını sağ **kaldırmak**.

Test ayarları dosyası çözümünüzden kaldırılır. Bu değişiklik için seçenekleri listesi olarak yansıtılır **Etkin Test ayarlarını seçin** ve **Test Ayarlarını Düzenle** seçeneklerinden **Test** menüsü.

## <a name="see-also"></a>Ayrıca bkz.

- [Test denetleyicileri ve test aracıları](configure-test-agents-and-controllers-for-load-tests.md)
- [Test ayarlarını kullanarak tanılama bilgileri Topla](../test/collect-diagnostic-information-using-test-settings.md)