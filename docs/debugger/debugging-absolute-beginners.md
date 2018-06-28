---
title: Yeni başlayanlar için hata ayıklama kodu
description: İlk olarak hata ayıklama, uygulamanızı Visual Studio ile hata ayıklama modunda çalışmasına yardımcı olmak için birkaç ilkeleri öğrenin
ms.custom: ''
ms.date: 06/18/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- debugger
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e2b9bcfecb8bae70852aebf7503641a8c2a3f6cf
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37057359"
---
# <a name="how-to-debug-for-absolute-beginners"></a>Başlayanlar için hata ayıklama

Başarısız, biz geliştiricilerine yazma kodu ne Bunu yapmak için beklenen her zaman yapmaz. Bazen tamamen farklı bir şey mevcut! Bu durumda, sonraki nedenini bulmak için bir görevdir ve biz yalnızca bizim kodu saat başlamanızı tutmak gerekebilir, çok daha kolay ve verimli bir hata ayıklama aracını kullanın ya da hata ayıklayıcısı olsa da.

Bir hata ayıklayıcısı ne yazık ki, ASP tüm sorunları veya "hataları" bizim kodda ortaya çıkarabilir bir şey yok. *Hata ayıklama* yapılan burada programlama hata tam noktasını bulmak için Visual Studio'yu, ister bir hata ayıklama aracı adım adım kodunuzu çalıştırmak için anlamına gelir. Sonra kodunuzda yapmanız hangi düzeltmeler anlayın ve hata ayıklama araçları genellikle programın çalıştırılması devam etmek için Geçici değişiklikler yapmanıza izin vermiyor.

Bir hata ayıklayıcısı verimli bir şekilde kullanmak da zaman ve öğrenmek için yöntem bir yetenek, ancak sonuçta bir temel için her yazılım geliştirici görevdir. Bu makalede, daha sonra hata ayıklama temel ilkeler tanıtır ve başlamanıza yardımcı olmak için ipuçları sağlar.

## <a name="clarify-the-problem-by-asking-yourself-the-right-questions"></a>Sorunu kendi başınıza sağ sorular sorarak açıklamak

Bunu düzeltmek denemeden önce içine çalıştırdığınız sorunu açıklamak için yardımcı olur. Bir sorunla zaten kodunuzda karşılaştık beklediğiniz, aksi takdirde, burada hata ayıklamak nasıl bağlayacağınızı çalışıyor olmayacaktır! Hata ayıklama başlamadan önce bu nedenle, çözmeye çalıştığınız sorun tanımladıktan emin olun:

* Ne yapmak için kodunuzu beklediğiniz neydi?

* Bunun yerine ne oldu?

    Uygulamanızı çalışırken bir hatayla (özel) çalıştırdıysanız, iyi bir şey olabilir! Bir özel durum kodu, genellikle bir tür hata çalıştırırken karşılaştı beklenmeyen bir olaydır. Hata ayıklama aracı kodunuzdaki özel durumun oluştuğu tam yere alabilir ve olası düzeltmeleri araştırmanıza yardımcı olabilir.

    Başka bir şey oluştuysa, sorunun belirtisi nedir? Bu sorun, kodunuzda oluştuğu şüpheleniyorsanız zaten? Örneğin, bazı metinleri kodunuzu görüntüler, ancak metin yanlıştır, verilerinizi bozuk veya hata çeşit görüntülenecek metni ayarlamak koduna sahip bildiğiniz. Bir hata ayıklayıcısı kodda doğruluk tarafından tam olarak ne zaman ve hatalı değerler atanır nasıl bulmak için değişkenlerinizi her değişiklik inceleyebilirsiniz.

## <a name="examine-your-assumptions"></a>Varsayımları inceleyin

Bir hata veya bir hata araştırmak önce belirli bir sonuç beklediğiniz yaptığınız özelliklerinin düşünün. Gizli veya bilinmeyen varsayımlar bile bir hata ayıklayıcıda sağ sorunun nedeni aradığınız olduğunda bir sorun tanımlayan in the way of elde edebilirsiniz. Olası varsayımlar uzun bir listesi olabilir! Burada, varsayımları sınama için kendinize sorun birkaç sorular vardır.

* Sağ API (diğer bir deyişle, doğru nesne, işlev, yöntemi veya özelliği) kullanıyor musunuz? Kullanmakta olduğunuz bir API mevcut düşüncelerinizi yapmak. (API çağrısı hata ayıklayıcısında inceledikten sonra düzeltme seyahat doğru API tanımlamaya yardımcı olmak için belgelerine gerektirebilir.)

* Bir API doğru kullanıyor musunuz? Belki de API sağ kullanılan ancak doğru şekilde kullanmadı.

* Kodunuzu herhangi yazım hatalarını içeriyor mu? Bir değişken adı, basit bir yazım hatası gibi bazı hatalarını, özellikle kullanıldıklarından önce bildirilmesi için değişkenleri gerektirmeyen dillerle çalışırken görmek zor olabilir.

* Kodunuzu değişiklik ve görmenizi sağlar sorun ilgisiz olduğunu varsayalım?

* Bir nesne veya belirli bir değere (veya belirli türde bir değer) içeren değişken beklediğiniz neydi farklı ne gerçekten oldu?

* Kod amacı biliyor musunuz? Genellikle daha yararlıdır kod başkası hata ayıklaması zor. Kodunuzu değilse, etkili bir şekilde debug önce tam olarak hangi kodu yapar zaman öğrenme harcamanız gerekebilir mümkündür.

    > [!TIP]
    > Kod yazarken küçük başlayın ve çalışan kod ile başlayın! (İyi örnek kod burada yararlı olur.) Bazı durumlarda, büyük veya karmaşık bir kod kümesi elde etmek için çalıştığınız çekirdek görev gösteren kod küçük bir parçasını başlatarak düzeltmek daha kolay olur. Ardından, değiştirin veya hatalar için her bir noktada sınama kodu artımlı olarak, ekleyin.

Varsayımları sormasını tarafından bir sorunu kodunuzda bulmak için geçen süreyi azaltabilir. Ayrıca, bir sorunu gidermek için geçen süreyi azaltabilir.

## <a name="step-through-your-code-in-debugging-mode-to-find-where-the-problem-occurred"></a>Hata ayıklama modu sorun oluştuğu bulmak için kodunuzu adım adım

Normalde bir uygulamayı çalıştırdığınızda, kod yalnızca çalıştırıldıktan sonra hataları ve yanlış sonuçları görürsünüz. Bir programı da beklenmedik bir şekilde neden söyleyen olmadan sonlandırabilir.

Bir hata ayıklayıcısı içinde bir uygulamayı çalıştıran olarak da bilinir *hata ayıklama modu*, hata ayıklayıcı etkin bir şekilde program çalışırken gerçekleştiği her şeyi izlediğini anlamına gelir. Ayrıca, herhangi bir noktada durumunu inceleyin ve kodunuzu olduğu sürece her ayrıntı izlemek için satır adım için uygulama duraklatmak sağlar.

Visual Studio'da hata ayıklama modunu kullanarak girdiğiniz **F5** (veya **hata ayıklama** > **hata ayıklamayı Başlat** menü komutu veya **hata ayıklamayı Başlat**  düğmesini ![hata ayıklamayı Başlat](../debugger/media/dbg-tour-start-debugging.png "hata ayıklamayı Başlat")) hata ayıklama araç. Özel durumlar oluşursa, Visual Studio'nun özel durum Yardımcısı burada özel durum oluştu ve başka yararlı bilgiler sağlayan tam noktasına alır.

Bir özel durum gelmedi büyük olasılıkla iyi bir fikir nerede sorun kodunuzda araması varsa. Bu kullandığınız *kesme noktaları* kendiniz kodunuzu daha dikkatlice inceleyin olanağı vermek için hata ayıklayıcısı ile. Kesme noktaları güvenilir hata ayıklama en temel ve temel özelliğidir. Bir kesme noktası göz atın, değişkenlerin değerleri veya bellek davranışını veya kod çalıştığı dizisi olabilmesi için Visual Studio çalışan kodunuzu nereye duraklatmak gösterir.

Visual Studio'da bir kod satırı yanındaki sol kenar boşluğunda tıklatarak hızlı bir şekilde bir kesme noktası ayarlayabilirsiniz. Veya bir satır ve tuşuna imleci yerleştirin **F9**.

Bu kavramları göstermeye yardımcı olmak için size çeşitli hatalar zaten olan bazı örnek kodda atmanız. Kullanıyoruz C#, ancak hata ayıklama özelliği için Visual Basic, C++, JavaScript, Python ve desteklenen diğer diller uygulanır.

### <a name="create-a-sample-app-with-some-bugs"></a>(Bazı hatalar ile) bir örnek uygulaması oluşturma

Ardından, birkaç hataları olan bir uygulama oluşturacağız.

1. Visual Studio yüklüyse ve ya da sahip olmalıdır. **NET masaüstü geliştirme** iş yükü veya. **Platformlar arası NET çekirdek** yüklü iş yükü, oluşturmak istediğiniz hangi uygulamanın türü üzerinde bağlı olarak.

    Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) ücretsiz yüklemek için sayfa.

    İş yükü yüklenir ancak tıklatın Visual Studio zaten gerektiğinde **Araçları** > **alma araçları ve özelliklerinin**. Visual Studio yükleyicisi başlatır. ' I seçin. **NET masaüstü geliştirme** (veya. **Platformlar arası NET çekirdek**) iş yükü, ardından **Değiştir**.

1. Visual Studio'yu açın ve ardından **dosya** > **yeni** > **proje**.

1. Uygulama kodunuz için bir şablon seçin.

    .NET Framework içinde **yeni proje** iletişim kutusunda, seçin **Visual C#**, **Windows Masaüstü** yüklenmiş şablonlar bölümünden, ardından Ortabölmesindeseçin **Konsol uygulaması (.NET Framework)**.

    .NET Core için de **yeni proje** iletişim kutusunda, seçin **Visual C#**, **.NET Core** yüklenmiş şablonlar bölümünden ve Orta bölmede seçin  **Konsol uygulaması (.NET Core)**.

    Bu şablon görmüyorsanız, uygun iş yükü yüklemeniz gerekir (önceki adımlara bakın).

1. İçinde **adı** alanında, yazın **ConsoleApp FirstApp** tıklatıp **Tamam**.

    Visual Studio Çözüm Gezgini'nde sağ bölmede görünür konsol projesi oluşturur.

1. İçinde *Program.cs*, tüm varsayılan kodu aşağıdaki kodla değiştirin:

    ```csharp
    using System;
    using System.Collections.Generic;
    
    namespace ConsoleApp_FirstApp
    {
        class Program
        {
            static void Main(string[] args)
            {
                Console.WriteLine("Welcome to Galaxy News!");
                IterateThroughList();
                Console.ReadKey();
            }
    
            private static void IterateThroughList()
            {
                var theGalaxies = new List<Galaxy>
            {
                new Galaxy() { Name="Tadpole", MegaLightYears=400, GalaxyType=new GType('S')},
                new Galaxy() { Name="Pinwheel", MegaLightYears=25, GalaxyType=new GType('S')},
                new Galaxy() { Name="Cartwheel", MegaLightYears=500, GalaxyType=new GType('L')},
                new Galaxy() { Name="Small Magellanic Cloud", MegaLightYears=.2, GalaxyType=new GType('I')},
                new Galaxy() { Name="Andromeda", MegaLightYears=3, GalaxyType=new GType('S')},
                new Galaxy() { Name="Maffei 1", MegaLightYears=11, GalaxyType=new GType('E')}
            };
    
                foreach (Galaxy theGalaxy in theGalaxies)
                {
                    Console.WriteLine(theGalaxy.Name + "  " + theGalaxy.MegaLightYears + ",  " + theGalaxy.GalaxyType);
                }
    
                // Expected Output:  
                //  Tadpole  400,  Spiral 
                //  Pinwheel  25,  Spiral 
                //  Cartwheel, 500,  Lenticular
                //  Small Magellanic Cloud .2,  Irregular
                //  Andromeda  3,  Spiral
                //  Maffei 1,  11,  Elliptical
            }
        }
    
        public class Galaxy
        {
            public string Name { get; set; }
    
            public double MegaLightYears { get; set; }
            public object GalaxyType { get; set; }
    
        }
    
        public class GType
        { 
            public GType(char type)
            {
                switch(type)
                {
                    case 'S':
                        MyGType = Type.Spiral;
                        break;
                    case 'E':
                        MyGType = Type.Elliptical;
                        break;
                    case 'l':
                        MyGType = Type.Irregular;
                        break;
                    case 'L':
                        MyGType = Type.Lenticular;
                        break;
                    default:
                        break;
                }
            }
            public object MyGType { get; set; }
            private enum Type { Spiral, Elliptical, Irregular, Lenticular}
        }
    }
    ```

    Bu kodun bizim amacı, bir listedeki tüm galaxy adı, galaxy ve galaxy türü uzaklık görüntülemektir. Hata ayıklamak için kod amacı anlamak önemlidir. Çıktıda göstermek istiyoruz listeden bir satır için biçimi şöyledir:

    *galaxy adı*, *uzaklığı*, *galaxy türü*.

### <a name="run-the-app"></a>Uygulama Çalıştırma

1. Tuşuna **F5** veya **hata ayıklamayı Başlat** düğmesini ![hata ayıklamayı Başlat](../debugger/media/dbg-tour-start-debugging.png "hata ayıklamayı Başlat") hata ayıklama araç çubuğunda bulunan Kod Düzenleyicisi.

    Uygulama başlar ve bize hata ayıklayıcı tarafından gösterilen hiçbir özel durum vardır. Ancak, konsol penceresinde göreceğiniz çıktıyı beklediğiniz olur. Beklenen çıktı şöyledir:

    ```
    Tadpole  400,  Spiral 
    Pinwheel  25,  Spiral 
    Cartwheel, 500,  Lenticular
    Small Magellanic Cloud .2,  Irregular
    Andromeda  3,  Spiral
    Maffei 1,  Elliptical
    ```

    Ancak biz bunu yerine bakın:

    ```
    Tadpole  400,  ConsoleApp_FirstApp.GType 
    Pinwheel  25,  ConsoleApp_FirstApp.GType 
    Cartwheel, 500,  ConsoleApp_FirstApp.GType
    Small Magellanic Cloud .2,  ConsoleApp_FirstApp.GType
    Andromeda  3,  ConsoleApp_FirstApp.GType
    Maffei 1, 11,  ConsoleApp_FirstApp.GType
    ```

    Çıkış ve kodumuza bakarak, biliyoruz `GType` galaxy türü depolar sınıfı adı. Numaralı (örneğin, "Spiral"), gerçek galaxy türü göstermek çalışıyoruz sınıf adını değil!

### <a name="debug-the-app"></a>Uygulama hata ayıklama

1. Sol kenar boşluğunda yanına tıklayarak uygulamayı hala çalıştıran bir kesme noktası belirleyerek `Console.WriteLine` Bu kod satırı yöntem çağrısında.

    ```csharp
    foreach (Galaxy theGalaxy in theGalaxies)
        {
            Console.WriteLine(theGalaxy.Name + "  " + theGalaxy.MegaLightYears + ",  " + theGalaxy.GalaxyType);
    }    
    ```

    Kesme noktası ayarladığınızda, kırmızı bir nokta sol kenar boşluğunda görüntülenir.

    Biz bir sorun çıktı görmek için biz Hata Ayıklayıcısı'ndaki çıkış ayarlar önceki kod bakarak hata ayıklama başlar.

1. Tıklatın **yeniden** ![yeniden uygulama](../debugger/media/dbg-tour-restart.png "RestartApp") hata ayıklama araç çubuğu düğmesini (**Ctrl** + **kaydırma**   +  **F5**).

    Uygulamanın ayarladığınız kesme noktasında duraklatır. Hata ayıklayıcı burada duraklatıldı sarı hightlighting gösterir (sarı kod satırı ile henüz çalıştırılmadı).

1. Üzerine gelerek `GalaxyType` değişkeni sağdaki, ardından sol tarafındaki İngiliz anahtarı simgesi genişletin `theGalaxy.GalaxyType`. Gördüğünüz `GalaxyType` bir özellik içeriyor `MyGType`, ve özellik değerini ayarlamak `Spiral`.

    ![Bir değişken inceleyin.](../debugger/media/beginners-inspect-variable.png)

    "Spiral" konsola yazdırma görmeyi beklediğiniz gerçekten doğru değeridir! Bu nedenle, uygulama çalıştırırken bu değer bu kodda erişebilirsiniz iyi bir başlangıç noktasıdır. Bu senaryoda, yanlış API kullanıyoruz. Biz bu kod hata ayıklayıcısı'ndaki çalıştırılırken düzeltebilirsiniz varsa göreceğiz.

1. Kodu aynı hala hata ayıklama sırasında imlecinizi sonunda yerleştirin `theGalaxy.GalaxyType` ve şekilde değiştirin `theGalaxy.GalaxyType.MyGType`. Bu değişiklik yapabilmenize rağmen kod düzenleyicisini, bu kod derlenemiyor belirten bir hata gösterir.

    ![Sözdizimi hatası](../debugger/media/beginners-edit.png)

1. Tıklatın **Düzenle** içinde **Düzenle ve devam et** ileti kutusu. Bir hata iletisi şimdi gördüğünüz **hata listesi** penceresi. Hata gösteren `'object'` için tanım içermiyor `MyGType`.

    ![Sözdizimi hatası](../debugger/media/beginners-no-definition.png)

    Bir nesne türü ile her galaxy ayarlarız olsa bile `GType` (olan `MGType` özelliği), hata ayıklayıcı tanımaz `theGalaxy` nesne türünde bir nesne olarak `GType`. Ne var ne yok? Galaxy türünü ayarlar herhangi bir kod aramak istediğiniz. Bunu yaptığınızda, gördüğünüz `GType` sınıfı kesinlikle bir özelliği olan `MyGType`, ancak bir şey doğru değil. İlgili hata iletisi `object` ; ipucu olarak öyle dil yorumlayıcısı türü türünde bir nesne görünüyor `object` türünde bir nesne yerine `GType`.

1. Bulduğunuz galaxy türü ayarlamakla ilgili kodunuzu aramak, `GalaxyType` özelliği `Galaxy` sınıfı olarak belirtildiğinde `object` yerine `GType`.

    ```csharp
    public object GalaxyType { get; set; }     
    ```

1. Önceki kod için değiştirin:

    ```csharp
    public GType GalaxyType { get; set; }     
    ```

1. Tıklatın **yeniden** ![yeniden uygulama](../debugger/media/dbg-tour-restart.png "RestartApp") hata ayıklama araç çubuğu düğmesini (**Ctrl** + **kaydırma**   +  **F5**) kod derlenir ve yeniden başlatın.

    Şimdi, ne zaman hata ayıklayıcı duraklatır üzerinde `Console.WriteLine`, üzerine getirin `theGalaxy.GalaxyType.MyGType`, değer düzgün ayarlandığından görebilirsiniz.

1. Sol kenar boşluğunda kesme noktası daire tıklayarak kesme noktası kaldırma (veya sağ tıklatın ve seçin **kesme noktası** > **silmek kesme noktası**) ve tuşuna basarak **F5** devam etmek için.

    Uygulama çalıştırır ve çıktısını görüntüler. Şimdi oldukça iyi görünür, ancak bir şey fark; Konsol çıkışı düzensiz galaxy olarak göstermek için küçük Magellanic bulut galaxy bekleniyordu ancak hiç hiçbir galaxy türünü gösterir.

    ```
    Tadpole  400,  Spiral 
    Pinwheel  25,  Spiral 
    Cartwheel, 500,  Lenticular
    Small Magellanic Cloud .2,
    Andromeda  3,  Spiral
    Maffei 1,  Elliptical
    ```

1. Bu kod satırında bir kesme noktası ayarlayın.

    ```csharp
    public GType(char type)
    ```

    Bu daha yakın bir göz atalım istiyoruz şekilde bu galaxy türü ayarlandığı kodudur.

1. Tıklatın **yeniden** ![yeniden uygulama](../debugger/media/dbg-tour-restart.png "RestartApp") hata ayıklama araç çubuğu düğmesini (**Ctrl** + **kaydırma**   +  **F5**) yeniden başlatmak için.

    Hata ayıklayıcı kesme ayarladığınız kod satırında duraklatır.  

1. Üzerine gelerek `type` değişkeni. Değerini gördüğünüz `S` (karakter kodu izleyerek). Bir değerinde ilgilendiğiniz `I`, bir düzensiz galaxy türü olduğunu bildiğiniz beri.

1. Tuşuna **F5** ve üzerine gelerek `type` yeniden değişkeni. Değerini görene kadar bu adımı yineleyin `I` içinde `type` değişkeni.

    ![Bir değişken inceleyin.](../debugger/media/beginners-inspecting-data.png)

1. Şimdi, basın **F11** (**hata ayıklama** > **Step Into** veya **Step Into** hata ayıklama araç çubuğu düğmesini).

    **F11** aynı anda bir deyim hata ayıklayıcı ilerler (ve kodu yürütür). **F10** (**Step Over**) benzer bir komuttur ve her ikisi de hata ayıklayıcı kullanmayı öğrenme, son derece yararlıdır.

1. Tuşuna **F11** kod satırı üzerinde durduruncaya kadar `switch` 'I' için bir değer ifadesi. Burada, bir yazım hatasından kaynaklanan sorununu Temizle bakın. Burada ayarlar ilerletmek için kod beklenen `MyGType` bir düzensiz olarak galaxy türü, ancak hata ayıklayıcı bunun yerine bu kod tamamen atlar ve üzerinde duraklatır `default` bölümünü `switch` deyimi.

    ![Bir yazım hatasından Bul](../debugger/media/beginners-typo.png)

    Koda bakmak, bir yazım hatasından bkz `case 'l'` deyimi. Olmalıdır `case 'I'`.

1. Tıklatın kodunda `case 'l'`ve bunların yerine ' örneği 'ı'.

1. İsabetini kaldırın ve ardından **yeniden** düğmesi uygulamayı yeniden başlatın.

    Şimdi düzeltilen hatalar ve beklediğiniz çıkış bakın!

    Uygulama tamamlamak için herhangi bir tuşa basın.

## <a name="summary"></a>Özet

Bir sorun gördüğünüzde, hata ayıklayıcı kullanın ve [adım komutları](../debugger/navigating-through-code-with-the-debugger.md) gibi **F10** ve **F11** bölge kodu sorunlu bulunamıyor.

> [!NOTE]
> Sorunun nerede oluştuğunu bölge kodu belirlenmesi zordur ise, sorun oluşmadan önce çalıştırılan kodda bir kesme noktası ayarlama ve sorunu görene kadar adım komutlarını kullanmak bildirimi. Aynı zamanda [tracepoints](../debugger/using-breakpoints.md#BKMK_Print_to_the_Output_window_with_tracepoints) oturum iletileri için **çıkış** penceresi. Tarafından günlüğe kaydedilen iletilere göz arayan (ve hangi iletilerin henüz günlüğe haberiniz bile!), bölge kodu sorunlu genellikle ayırabilirsiniz. Bu işlemin Dar Aşağı için birkaç kez yineleyin gerekebilir.

Bölge kodu sorunlu bulduğunuzda, hata ayıklayıcı araştırmak için kullanın. Bir sorunun nedenini bulmak için hata ayıklayıcıda uygulamanızı çalıştırırken sorun kodu inceleyin:

* [Değişkenleri incelemek](../debugger/view-data-values-in-data-tips-in-the-code-editor.md) ve içermesi gereken değerlerin türü içerdikleri olup olmadığını denetleyin. Hatalı bir değer bulursanız, hatalı değer nerede ayarlandı Bul (değer belirlendiği bulmak için gerekebilir hata ayıklayıcı yeniden başlatın, bakmak [çağrı yığını](../debugger/how-to-use-the-call-stack-window.md), veya her ikisini de).

* Uygulamanızı beklediğiniz kodu yürütme olup olmadığını denetleyin. (Örneğin, örnek uygulamasında düzensiz için galaxy türünü ayarlamak anahtar deyim için kod bekliyorduk ancak uygulama kodu yazım hatası nedeniyle atlandı.)

> [!TIP]
> Hata ayıklayıcı hataları bulmanıza yardımcı olmak için kullanın. Hata ayıklama aracı hatalar bulabilirsiniz *,* yalnızca kodunuzu amacı biliyorsa. Geliştirici olarak size, bu amacı express, bir aracı yalnızca kodunuzu amacı bilemez. Yazma [birim testleri](../test/improve-code-quality.md) bunu nasıl olduğu.

## <a name="next-steps"></a>Sonraki adımlar

Bu makalede, birkaç genel hata ayıklama kavramlarını öğrendiniz. Ardından, Visual Studio ile hata ayıklamak öğrenme başlatabilirsiniz.

> [!div class="nextstepaction"]
> [Hata ayıklayıcısı özellik turu](../debugger/debugger-feature-tour.md)
