---
title: "Etki alanına özgü dil ile çalışmaya başlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 92db1c4d27eec5a9ac18d51644dfb0141c2fef34
ms.sourcegitcommit: 69b898d8d825c1a2d04777abf6d03e03fefcd6da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="getting-started-with-domain-specific-languages"></a>Etki Alanına Özgü Dillerle Çalışmaya Başlama
Bu konuda tanımlama ve modelleme SDK ile Visual Studio için oluşturulmuş bir etki alanına özgü dil (DSL) kullanarak temel kavramlar açıklanmaktadır.

> [!NOTE]
> Visual Studio 2017 içinde metin şablonu dönüştürme SDK'sı ve modelleme Visual Studio SDK, Visual Studio'nun belirli özellikleri yüklediğinizde otomatik olarak yüklenir. Daha fazla ayrıntı için bkz: [bu blog gönderisine](https://blogs.msdn.microsoft.com/visualstudioalm/2016/12/12/the-visual-studio-modeling-sdk-is-now-available-with-visual-studio-2017/).

İçin DSL'ler yeniyseniz, aracılığıyla çalışmanızı öneririz **DSL araçları Laboratuvar**, bu sitede bulabilirsiniz: [Visualizaton ve SDK Modelleme](http://go.microsoft.com/fwlink/?LinkID=186128)  
  
## <a name="what-can-you-do-with-a-domain-specific-language"></a>Bir etki alanına özgü dil ile neler yapabileceğiniz?  
 Bir etki alanına özgü dil belirli bir amaç için kullanılmak üzere tasarlanmış bir, genellikle grafik gösterimidir. Bunun aksine, UML gibi dilleri genel amaçlı. Bir DSL, model öğesi ve ilişkilerini ve ekranda nasıl sunulan türlerini tanımlayabilirsiniz.  
  
 DSL tasarlarken, Visual Studio Tümleştirme Uzantısı (VSIX) paketinin bir parçası olarak dağıtabilirsiniz. Visual Studio'da DSL ile kullanıcılar çalışır:  
  
 ![Aile ağacı diyagramı, araç ve Gezgini](../modeling/media/familyt_instance.png "FamilyT_Instance")  
  
 Gösterimi DSL yalnızca bir parçası olur. Gösterimi birlikte VSIX paketi kullanıcılar bunları düzenleyin ve bunların modellerinden malzemesi oluşturmak amacıyla uygulayabilir araçlarını içerir.  
  
 DSL'ler asıl uygulamalardan birini program kodu, yapılandırma dosyalarını ve diğer yapıları oluşturmaktır. Özellikle büyük projeler ve ürün satırlarını, bir ürünün çeşitli türevleri oluşturulacağı, birden çok değişken DSL'ler oluşturma büyük miktarda bir artış güvenilirlik ve çok hızlı bir gereksinim değişikliklerine yanıt sağlayabilir.  
  
 Bu genel bakışta kalan oluşturma ve bir etki alanına özgü dil Visual Studio kullanarak temel işlemleri sunar bir kılavuz ' dir.  
  
## <a name="prerequisites"></a>Önkoşullar  
 DSL tanımlamak için aşağıdaki bileşenler yüklü olmalıdır:  
  
|||  
|-|-|  
|Visual Studio|[http://go.microsoft.com/fwlink/?LinkId=185579](http://go.microsoft.com/fwlink/?LinkId=185579)|  
|[!INCLUDE[vssdk_current_short](../modeling/includes/vssdk_current_short_md.md)]|[http://go.microsoft.com/fwlink/?LinkId=185580](http://go.microsoft.com/fwlink/?LinkId=185580)|  
|Visual Studio SDK Modelleme||  


[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

  
## <a name="creating-a-dsl-solution"></a>DSL çözümü oluşturma  
 Yeni bir etki alanına özgü dil oluşturmak için etki alanına özgü dil proje şablonunu kullanarak yeni bir Visual Studio çözümü oluşturun.  
  
#### <a name="to-create-a-dsl-solution"></a>Bir DSL çözüm oluşturmak için  
  
1.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**.  
  
2.  Altında **proje türleri**, genişletin **diğer proje türleri** düğümü ve tıklatın **genişletilebilirlik**.  
  
3.  Tıklatın **etki alanına özgü dil Tasarımcısı**.  
  
     ![Oluştur iletişim kutusu DSL](../modeling/media/create_dsldialog.png "Create_DSLDialog")  
  
4.  İçinde **adı** kutusuna **FamilyTree**. **Tamam**'ı tıklatın.  
  
     **Etki alanına özgü dil Sihirbazı** açar ve şablon DSL çözümlerinin listesini görüntüler.  
  
     Her bir şablon açıklamasını görmek için tıklatın  
  
     Şablonları yararlı başlangıç noktaları. Bunların her biri tam çalışma gereksinimlerinize uyacak şekilde düzenleyerek DSL sağlar. Normalde, oluşturmak istediğiniz en yakın şablonu seçmelisiniz.  
  
5.  Bu kılavuzda seçin **en az bir dil** şablonu.  
  
6.  Bir dosya adı uzantısı, DSL uygun Sihirbazı sayfasında girin. Bu, DSL örneklerini içeren dosyaları kullanacağı uzantısıdır.  
  
    -   Herhangi bir uygulama, bilgisayarınızın veya DSL yüklemek istediğiniz herhangi bir bilgisayar ile ilişkilendirilmemiş bir uzantı seçin. Örneğin, **docx** ve **htm** kabul edilebilir dosya adı uzantılarını olacaktır.  
  
    -   Girdiğiniz uzantısı DSL kullanılmakta olup olmadığını, sihirbaz sizi uyarır. Farklı bir dosya adı uzantısı kullanmayı düşünün. Eski Deneysel tasarımcıları temizlemek için Visual Studio SDK deneysel örneği sıfırlayabilir. Tıklatın **Başlat**, tıklatın **tüm programlar**, **Microsoft Visual Studio 2010 SDK**, **Araçları**ve ardından **Microsoft Sıfırla Visual Studio 2010 Experimental örneği**.  
  
7.  Sihirbazın diğer sayfalarını inceleyin ve ardından **son**.  
  
     Bir çözüm iki proje içeren oluşturulur. Bunlar Dsl ve DslPackage olarak adlandırılır. Bir diyagram dosyası başka bir deyişle adlandırılmış DslDefinition.dsl açar.  
  
    > [!NOTE]
    >  İki proje klasörlerdeki görebilirsiniz kod çoğunu DslDefinition.dsl oluşturulur. Bu nedenle, bu dosyada, DSL için en son değişiklikleri yapılmıştır.  
  
 Kullanıcı arabirimi şimdi aşağıdaki resimde benzer.  
  
 ![DSL Tasarımcısı](../modeling/media/dsl_designer.png "dsl_designer")  
  
 Bu çözüm, etki alanı belirli bir dil tanımlar. Daha fazla bilgi için bkz: [etki alanına özgü dil araçları kullanıcı arabirimi genel bakış](../modeling/overview-of-the-domain-specific-language-tools-user-interface.md).  
  
## <a name="the-important-parts-of-the-dsl-solution"></a>DSL çözümünün önemli bölümleri  
 Yeni bir çözüm şu yönlerini dikkat edin.  
  
-   **Dsl\DslDefinition.DSL** bu DSL çözüm oluşturduğunuzda gördüğünüz dosyasıdır. Çözümdeki neredeyse tüm kod bu dosyadan oluşturulur ve çoğu DSL tanımına yaptığınız değişiklikler, burada yapılır. Daha fazla bilgi için bkz. Working with [ile DSL tanımı diyagramı çalışma](../modeling/working-with-the-dsl-definition-diagram.md).  
  
-   **DSL proje** bu proje etki alanına özgü dil tanımlayan kodu içerir.  
  
-   **DslPackage proje** bu proje açılabilir ve Visual Studio'da düzenlenebilir için DSL örneklerini verir kodunu içerir.  
  
##  <a name="Debugging"></a>DSL çalıştırma  
 Oluşturduğunuz hemen DSL çözüm çalıştırabilirsiniz. Daha sonra çözümü yeniden her bir değişiklikten sonra çalışan DSL tanımını yavaş yavaş değiştirebilirsiniz.  
  
#### <a name="to-experiment-with-the-dsl"></a>İle DSL denemek için  
  
1.  Tıklatın **tüm şablonları dönüştürme** Çözüm Gezgini araç çubuğunda. Bu DslDefinition.dsl kaynak kodundan çoğunu yeniden oluşturur.  
  
    > [!NOTE]
    >  DslDefinition.dsl değiştirdiğinizde tıklatmalısınız **tüm şablonları dönüştürme** önce çözümü yeniden derleyin. Bu adım otomatik hale getirebilirsiniz. Daha fazla bilgi için bkz: [otomatikleştirmek tüm şablonları dönüştürme nasıl](http://msdn.microsoft.com/b63cfe20-fe5e-47cc-9506-59b29bca768a).
  
2.  F5 tuşuna basın veya **hata ayıklama** menüsünde tıklatın **hata ayıklamayı Başlat**.  
  
     DSL oluşturur ve olan Visual Studio deneysel örneğinde yüklü.
  
     Visual Studio Deneysel bir örneğini başlatır. Deneysel örneği ayrı bir alt ağacı, Visual Studio uzantıları hata ayıklama amacıyla kayıtlı kayıt defteri, kendi ayarları alır. Visual Studio normal örneklerini var. kaydedilen uzantılar erişimi.  
  
3.  Visual Studio deneysel örneğinde adlı model dosyasını açın **Test** gelen **Çözüm Gezgini**.  
  
     \-veya -  
  
     Hata ayıklama projesine sağ tıklayın, fareyle **Ekle**ve ardından **öğesi**. İçinde **Öğe Ekle** dosya türü, DSL iletişim kutusunda, seçin.  
  
     Model dosyası boş bir diyagramı açılır.  
  
     Araç kutusu açılır ve şema türü için uygun araçları görüntüler.  
  
4.  Şekiller ve bağlayıcılar diyagramı oluşturmak için araçlarını kullanın.  
  
    1.  Şekiller oluşturmak için örnek şekil aracı diyagram üzerine sürükleyin.  
  
    2.  İki şekil bağlanmak için örnek bağlayıcı Aracı'nı tıklatın, ilk şekli tıklatın ve ikinci şekli'ye tıklayın.  
  
5.  Bunları değiştirmek için şekilleri etiketler'ı tıklatın.  
  
 Aşağıdaki örnek, Deneysel Visual Studio benzeyecektir:  
  
 ![](../modeling/media/dsl_min.png "DSL_min")  
  
### <a name="the-content-of-a-model"></a>Bir Model içeriği  
 DSL örneği bir dosyanın içeriğini adlı bir *modeli*. Modeli içeren *modeli ** öğeleri* ve *bağlantılar* olan öğeler arasında. Model öğelerini ne tür DSL tanımı belirtir ve bağlantıları modelde bulunabilir. Örneğin, en az bir dil şablondan oluşturulan bir DSL içinde var. bir model öğesi türünü ve bir bağlantı türü  
  
 Modelin diyagram üzerinde görünme DSL tanımı belirtebilirsiniz. Stilleri şekilleri ve bağlayıcıların çeşitli arasından seçim yapabilirsiniz. Bazı şekiller içindeki diğer şekiller görünmesini belirtebilirsiniz.  
  
 İçinde bir ağaç olarak bir modeli görüntüleyebilirsiniz **Explorer** bir model düzenlerken görüntüleyin. Şekilleri diyagrama eklemek gibi model öğelerini explorer'ın da görünür. Diyagram yok olsa bile explorer kullanılabilir.  
  
 Visual Studio hata ayıklama örneğini Explorer'da göremiyorsanız **Görünüm** menüsünde **diğer pencereler**ve ardından  *\<bilgisayarınızı dil >* **Explorer**.  
  
### <a name="the-api-of-your-dsl"></a>DSL API  
 DSL okuyun ve DSL örnekleridir modelleri güncelleştirmenize olanak veren bir API oluşturur. Bir API modelden metin dosyaları oluşturmak için uygulamasıdır. Daha fazla bilgi için bkz: [T4 metin şablonları kullanarak tasarım zamanı kodu oluşturma](../modeling/design-time-code-generation-by-using-t4-text-templates.md).  
  
 Hata ayıklama çözümde şablon dosyalarını ".tt" uzantısı ile açın. Bu örnekler nasıl metin modellerinden oluşturabilir ve, DSL API test etmenize izin göstermektedir. Örneklerden birini yazılmış [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], içinde başka [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)].  
  
 Altında her bir şablon dosyası, oluşturduğu dosyasıdır. Çözüm Gezgini'nde şablon dosyasını genişletin ve oluşturulan dosyasını açın.  
  
 Şablon dosyası, kısa bir modeldeki tüm öğeleri listeler kod parçası içeriyor.  
  
 Oluşturulan dosyanın sonucunu içerir.  
  
 Bir model dosyası değiştirdiğinizde, dosyaları yeniden oluşturduktan sonra oluşturulan dosyalarda karşılık gelen değişiklikleri görürsünüz.  
  
##### <a name="to-regenerate-text-files-after-you-change-the-model-file"></a>Model dosyası değiştirdikten sonra metin dosyaları yeniden oluşturmak için  
  
1.  Visual Studio deneysel örneğinde model dosyasını kaydedin.  
  
2.  Dosya adı parametresi her .tt dosyasındaki denemeleri için kullanmakta olduğunuz modeli dosyasına başvurduğundan emin olun. .Tt dosyasını kaydedin.  
  
3.  Tıklatın **tüm şablonları dönüştürme** araç çubuğundaki **Çözüm Gezgini**.  
  
     \-veya -  
  
     Sağ tıklatın, yeniden oluşturun ve ardından istediğiniz şablonları **çalıştırmak özel araç**.  
  
 Metin şablonu dosyalarını herhangi bir sayıda projeye ekleyebilirsiniz. Her şablon bir sonuç dosyası oluşturur.  
  
> [!NOTE]
>  DSL tanımı değiştirdiğinizde, bu güncelleştirme sürece örnek metin şablonu kodu çalışmaz.  
  
 Daha fazla bilgi için bkz: [bir etki alanına özgü dil oluşturma koddan](../modeling/generating-code-from-a-domain-specific-language.md) ve [bir etki alanına özgü dil kişiselleştirmek için kod yazma](../modeling/writing-code-to-customise-a-domain-specific-language.md).  
  
## <a name="customizing-the-dsl"></a>DSL özelleştirme  
 DSL tanımı değiştirmek istediğinizde, deneysel örneği kapatın ve ana Visual Studio örneği tanımında güncelleştirin.  
  
> [!NOTE]
>  DSL tanımı değiştirdikten sonra önceki sürümlerini kullanarak oluşturduğunuz test modelleri bilgileri kaybedebilirsiniz.  Örneğin, hata ayıklama çözüm bazı şekilleri ve bağlayıcıları içeren örnek adlı bir dosya içeriyor. DSL tanımınızı geliştirmek başlattıktan sonra bunların görünür olmaz ve dosyayı kaydettiğinizde, bunlar kaybolur.  
  
 Çok çeşitli uzantıları, DSL yapabilirsiniz. Aşağıdaki örnekler bir izlenim olanaklar sunar.  
  
 DSL tanımına kaydetme her bir değişiklikten sonra tıklatın **tüm şablonları dönüştürme** içinde **Çözüm Gezgini**ve tuşuna basarak **F5** ile değiştirilen DSL denemek için.  
  
### <a name="rename-the-types-and-tools"></a>Araçlar ve türleri yeniden adlandırma  
 Var olan etki alanı sınıflar ve ilişkiler yeniden adlandırın. Örneğin, en az bir dil şablondan oluşturulan Dsl tanımından başlayarak, aile ağaçlarını temsil DSL yapmak için aşağıdaki yeniden adlandırma işlemleri gerçekleştirebilir.  
  
##### <a name="to-rename-domain-classes-relationships-and-tools"></a>Etki alanı sınıfları, ilişkileri ve araçları yeniden adlandırmak için  
  
1.  DslDefinition şemada yeniden adlandırma **ExampleModel** için **FamilyTreeModel**, **ExampleElement** için **kişi**,  **Hedefleri** için **üst**, ve **kaynakları** için **alt**. Değiştirmek için her etiket tıklatabilirsiniz.  
  
     ![DSL tanımı diyagramı &#45; Aile Ağacı Modeli](../modeling/media/familyt_person.png "FamilyT_Person")  
  
2.  Öğe ve bağlayıcı Araçlar yeniden adlandırın.  
  
    1.  Çözüm Gezgini altında sekmesini tıklatarak DSL Explorer penceresi açın. Üzerinde göremiyorsanız, **Görünüm** menüsünde **diğer pencereler** ve ardından **DSL Explorer**. Yalnızca DSL tanımı diyagramı etkin pencereyi DSL Explorer görünür olur.  
  
    2.  Özellikler penceresini açın ve aynı anda DSL Gezgini ve özellikleri görmenize olanak tanıyan getirin.  
  
    3.  DSL Explorer'da genişletin **Düzenleyicisi**, **araç kutusu sekmeleri**,  *\<, DSL >*ve ardından **Araçları**.  
  
    4.  Tıklatın **ExampleElement**. Öğeleri oluşturmak için kullanılan araç kutusu öğesi budur.  
  
    5.  Özellikler penceresinde değiştirin **adı** özelliğine **kişi**.  
  
         Dikkat **resim yazısı** özelliğini de değiştirir.  
  
    6.  Aynı şekilde, adını değiştirmek **ExampleConnector** aracı **ParentLink**. ALTER **resim yazısı** özelliğini, BT'nin bir kopyasını Name özelliği değil. Örneğin **üst bağlantı**.  
  
3.  DSL yeniden oluşturun.  
  
    1.  DSL tanım dosyasını kaydedin.  
  
    2.  Tıklatın **tüm şablonları dönüştürme** araç çubuğundaki Çözüm Gezgini  
  
    3.  F5 tuşuna basın. Visual Studio'nun deneysel örneği görünene kadar bekleyin.  
  
4.  Visual Studio'nun deneysel örneği hata ayıklama çözümde test model dosyasını açın. Öğeleri sürüklediğinizde araç Kutusu'ndan sürükleyin. Aracı resim yazıları ve tür adları DSL Explorer'da değiştirilmiştir dikkat edin.  
  
5.  Model dosyasını kaydedin.  
  
6.  .Tt dosyasını açın ve yeni bir isimle eski türünü ve özellik adları tekrarı değiştirin.  
  
7.  .Tt dosyasında belirtilen dosya adı test modelinizi belirttiğinden emin olun.  
  
8.  .Tt dosyasını kaydedin. .Tt dosyasında kodu çalıştırmanın sonuçlarını görmek için oluşturulan dosyasını açın. Doğru olduğundan emin olun.  
  
### <a name="add-domain-properties-to-classes"></a>Etki alanı özellikleri sınıflara ekleme  
 Örneğin Doğum yıl ve tarayıcının bir kişi sonu temsil etmek bir etki alanı sınıfına özellikleri ekleyin.  
  
 Yeni özellikleri diyagramda görünür yapmak için eklemelisiniz *dekoratörler* şekle model öğesi görüntüler. Ayrıca dekoratörler özellikleri eşlemeniz gerekir.  
  
##### <a name="to-add-properties-and-display-them"></a>Özellikleri ekleyin ve bunları görüntülemek için  
  
1.  Özellikleri ekleyin.  
  
    1.  DSL tanımı Diyagramı sağ **kişi** etki alanı sınıfı, noktasına **Ekle**ve ardından **etki alanı özelliği**.  
  
    2.  Yeni özellik adlarının bir listesini yazın **Doğum** ve **ölüm**. Tuşuna **Enter** her biri sonra.  
  
2.  Özellikler şeklinde görüntülenir dekoratörler ekleyin.  
  
    1.  Kişinin etki alanı diyagramı diğer tarafını sınıftan gri çizgi izleyin. Bir diyagram öğesi harita budur. Bu etki alanı sınıfı bir şekli sınıfına bağlar.  
  
    2.  Bu şeklin sınıf sağ tıklayın, fareyle **Ekle**ve ardından **metin oluşturma öğesi**.  
  
    3.  Adları olan iki dekoratörler gibi eklemek **BirthDecorator** ve **DeathDecorator**.  
  
    4.  Her yeni oluşturma öğesi seçin ve Özellikler penceresinde ayarlayın **konumu** alan. Bu, etki alanı özellik değeri şeklin üzerinde nerede görüntüleneceğini belirler. Örneğin, **InnerBottomLeft** ve **InnerBottomRight**.  
  
         ![Şekil tanımı compartment](../modeling/media/familyt_compartment.png "FamilyT_Compartment")  
  
3.  Dekoratörler özelliklerine eşlenir.  
  
    1.  DSL ayrıntıları penceresini açın. Çıktı penceresi yanında bir sekmede genellikle olur. Üzerinde göremiyorsanız, **Görünüm** menüsündeki **diğer pencereler**ve ardından **DSL ayrıntıları**.  
  
    2.  DSL tanımı diyagramda bağlayan çizgi **kişi** shape sınıfı için etki alanı sınıfı.  
  
    3.  İçinde **DSL ayrıntıları**, **oluşturma öğesi eşlemeleri** sekmesinde, eşlenmemiş oluşturma öğesi üzerinde onay kutusuna tıklayın. İçinde **görüntü özelliği**, istediğiniz bu eşlenen etki alanı özelliği seçin. Örneğin, eşleme **BirthDecorator** için **Doğum**.  
  
4.  DSL kaydedin, tüm Şablonları Dönüştür'e tıklayın ve F5 tuşuna basın.  
  
5.  Örnek modeli diyagramda seçtiğiniz konumlar tıklayın şimdi ve bunların içine değerleri yazın doğrulayın. Ayrıca, seçtiğinizde, bir **kişi** şekli, Özellikler penceresini Doğum ve ölümleri yeni özellikleri görüntüler.  
  
6.  .Tt dosyasında her birinin özelliklerini alır kodu ekleyebilirsiniz.  
  
 ![Aile ağacı diyagramı, araç ve Gezgini](../modeling/media/familyt_instance.png "FamilyT_Instance")  
  
### <a name="define-new-classes"></a>Yeni sınıflar tanımlayın  
 Bir model için etki alanı sınıflar ve ilişkiler ekleyebilirsiniz. Örneğin, şehir ve bir kişi bir piyasada yaşamakta temsil etmek için yeni bir ilişki temsil etmek için yeni bir sınıf oluşturabilirsiniz.  
  
 Farklı bir model diyagramda ayrı yapmak için etki alanı sınıflarını şekli farklı türde veya farklı geometri ve renkleri eşleyebilirsiniz.  
  
##### <a name="to-add-and-display-a-new-domain-class"></a>Eklemek ve yeni bir etki alanı sınıf görüntülemek için  
  
1.  Bir etki alanı sınıf ekleyin ve bir alt model kökü yapın.  
  
    1.  DSL tanımı diyagramına tıklayabilir **katıştırma ilişki** aracı, kök sınıfı tıklatın **FamilyTreeModel**ve ardından diyagramı boş bir bölümüne tıklayın.  
  
         Yeni bir etki alanı sınıf, bir katıştırma ilişkisi FamilyTreeModel bağlı görüntülenir.  
  
         Adını, örneğin ayarlayın **Şehir**.  
  
        > [!NOTE]
        >  Modelin kökü dışında her etki alanı sınıf en az bir katıştırma ilişki hedefi olmalıdır veya bir katıştırma hedefi bir sınıftan devralın gerekir. Bu nedenle, bu ilişki katıştırma aracını kullanarak bir etki alanı sınıfı oluşturmak üzere sık uygundur.  
  
    2.  Bir etki alanı özelliği yeni sınıfa, örneğin eklemek **adı**.  
  
2.  Kişi ve şehir arasındaki başvuru ilişkisi ekleyin.  
  
    1.  Tıklatın **başvuru ilişkisi** aracı, kişi'yi tıklatın ve sonra Şehir'ı tıklatın.  
  
         ![DSL tanımı parça: Aile ağacı kök](../modeling/media/familyt_root.png "FamilyT_Root")  
  
        > [!NOTE]
        >  Başvuru ilişkileri çapraz bir model ağacına bölümünden diğerine temsil eder.  
  
3.  Model diyagramlarındaki Şehir temsil etmek için bir şekli ekleyin.  
  
    1.  Sürükleme bir **geometri şekli** diyagrama araç ve örneğin, yeniden adlandırma **TownShape**.  
  
    2.  Özellikler penceresinde yeni şeklin dolgu rengi ve Geometry gibi görünüm alanları ayarlayın.  
  
    3.  Şehir adını görüntülemek için bir oluşturma öğesi ekleyin ve NameDecorator yeniden adlandırın. Konum özelliğini ayarlayın.  
  
4.  Şehir etki alanı sınıfı TownShape eşleyin.  
  
    1.  Tıklatın **diyagram öğesi harita** aracı ve şehir etki alanı ve ardından TownShape şekli sınıf'i tıklatın.  
  
    2.  İçinde **oluşturma öğesi eşlemeleri** sekmesinde **DSL ayrıntıları** map bağlayıcı penceresiyle seçili ve NameDecorator denetleyin **görüntü özelliği** adı.  
  
5.  Kişi ve şehir arasındaki ilişkiyi görüntülemek için bir bağlayıcı oluşturun.  
  
    1.  Bir bağlayıcı araç Kutusu'ndan diyagrama sürükleyin. Yeniden adlandırın ve görünüm özelliklerini ayarlayın.  
  
    2.  Kullanım **diyagram öğesi harita** kişi ve şehir arasındaki ilişkiyi yeni bağlayıcı bağlamak için aracı.  
  
         ![Şekil eklendi harita Aile ağacı tanımıyla](../modeling/media/familyt_shapemap.png "FamilyT_ShapeMap")  
  
6.  Yeni Şehir yapmak için bir öğe aracı oluşturun.  
  
    1.  İçinde **DSL Explorer**, genişletin **Düzenleyicisi** sonra **araç kutusu sekmeleri**.  
  
    2.  Sağ  *\<, DSL >* ve ardından **ekleme yeni öğe aracı**.  
  
    3.  Ayarlama **adı** yeni araç ve kümesi özelliği kendi **sınıfı** Şehir özelliğine.  
  
    4.  Ayarlama **araç kutusu simgesi** özelliği. Tıklatın **[...]**  ve **dosya adı** alanında, bir simge dosyası seçin.  
  
7.  Şehir ve kişiler arasında bir bağlantı yapmak için bir bağlayıcı aracını oluşturun.  
  
    1.  Sağ  *\<, DSL >* ve ardından **ekleme yeni bağlayıcı aracını**.  
  
    2.  Yeni aracı adını ayarlayın.  
  
    3.  İçinde **ConnectionBuilder** özelliği, kişi Şehir ilişki adını içeren Oluşturucusu'nu seçin.  
  
    4.  Ayarlama **araç kutusu simgesi**.  
  
8.  DSL tanımını kaydet, tıklatın **tüm şablonları dönüştürme**ve tuşuna basarak **F5**.  
  
9. Visual Studio Deneysel kopyasında bir test model dosyasını açın. Şehir ve şehir ve kişiler arasında bağlantılar oluşturmak için yeni araçları kullanın. Öğe doğru türleri arasındaki bağlantıları yalnızca oluşturabilirsiniz dikkat edin.  
  
10. Listeler, her kişinin yaşadığı şehir kodu oluşturun. Metin şablonları böyle kodu çalıştırdığı yerler biridir. Örneğin, aşağıdaki kodu içeren hata ayıklama çözümde varolan Sample.tt dosyayı değiştirebileceği:  
  
    ```  
    <#@ template inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation" debug="true" #>  
    <#@ output extension=".txt" #>  
    <#@ FamilyTree processor="FamilyTreeDirectiveProcessor" requires="fileName='Sample.ftree'" #>  
  
    <#  
      foreach (Person person in this.FamilyTreeModel.People)  
      {  
    #>  
        <#= person.Name #><#if (person.Town != null) {#> of <#= person.Town.Name #> <#}#>  
  
    <#  
          foreach (Person child in person.Children)  
      {  
    #>  
                <#= child.Name #>  
    <#  
      }  
      }  
    #>  
  
    ```  
  
     *.Tt dosyasını kaydettiğinizde, kişiler ve bunların residences listesini içeren bir dosyası oluşturur. Daha fazla bilgi için bkz: [bir etki alanına özgü dil oluşturma koddan](../modeling/generating-code-from-a-domain-specific-language.md).  
  
## <a name="validation-and-commands"></a>Doğrulama ve komutlar  
 Doğrulama kısıtlamaları ekleyerek bu DSL daha fazla geliştirebilir. Bu kısıtlamaların model doğru durumda olduğundan emin olun, tanımlayabilirsiniz, yöntemler şunlardır. Örneğin, bir alt doğum tarihi, üst öğelerinden sonraki olan emin olmak için bir kısıtlama tanımlayabilirsiniz. Doğrulama özelliği DSL kullanıcı kısıtlamaları hiçbirini keser bir model kaydetmeyi denediğinde bir uyarı görüntüler. Daha fazla bilgi için bkz: [bir etki alanına özgü dil doğrulama](../modeling/validation-in-a-domain-specific-language.md).  
  
 Ayrıca kullanıcının çağırabileceği menü komutlarını tanımlayabilirsiniz. Komutlar model değiştirebilirsiniz. Visual Studio'da diğer modellerle ve dış kaynaklara etkileşime de. Daha fazla bilgi için bkz: [nasıl yapılır: standart menü komutu değiştirme](../modeling/how-to-modify-a-standard-menu-command-in-a-domain-specific-language.md).  
  
## <a name="deploying-the-dsl"></a>DSL dağıtma  
 Diğer kullanıcıların etki alanına özgü dil kullanmasına izin vermek için Visual Studio Uzantısı (VSIX) dosyasını dağıtın. DSL çözümü yapılandırdığınızda bu oluşturulur.  
  
 Çözümünüzü depo klasörde .vsix dosyasını bulun. Yüklemek istediğiniz bilgisayara kopyalayın. Bu bilgisayar üzerinde VSIX dosyasını çift tıklatın. DSL, Visual Studio'nun bu bilgisayardaki tüm durumlarda kullanılabilir.  
  
 Böylece Visual Studio Deneysel örneğini kullanması gerekmez DSL kendi bilgisayara yüklemek için aynı yordamı kullanabilirsiniz.  
  
 Daha fazla bilgi için bkz: [etki alanına özgü dil çözümleri dağıtma](../modeling/deploying-domain-specific-language-solutions.md).  
  
##  <a name="Reset"></a>Eski Deneysel DSL'ler kaldırma  
 Artık istediğiniz Deneysel DSL'ler oluşturduysanız, Visual Studio deneysel örneği sıfırlayarak bunları bilgisayarınızdan kaldırabilirsiniz.  
  
 Tüm Deneysel DSL'ler ve diğer Deneysel Visual Studio uzantılarını bu bilgisayardan kaldırır. Bu hata ayıklama modu yürütülen uzantılarıdır.  
  
 Bu yordam, DSL'ler veya tam olarak VSIX yürüterek yüklenmiş diğer Visual Studio uzantıları kaldırmaz.  
  
#### <a name="to-reset-the-visual-studio-experimental-instance"></a>Visual Studio deneysel örneği sıfırlamak için  
  
1.  Tıklatın **Başlat**, tıklatın **tüm programlar**, **Microsoft Visual Studio 2010 SDK**, **Araçları**ve ardından **Microsoft Sıfırla Visual Studio 2010 Experimental örneği**.  
  
2.  Deneysel herhangi DSL'ler veya hala kullanmak istediğiniz diğer Deneysel Visual Studio uzantılarını yeniden oluşturun.  
  
## <a name="see-also"></a>Ayrıca bkz.

[Anlama modelleri, sınıflar ve ilişkiler](../modeling/understanding-models-classes-and-relationships.md)   
[Nasıl yapılır: Etki Alanına Özgü bir Dili Tanımlama](../modeling/how-to-define-a-domain-specific-language.md)

