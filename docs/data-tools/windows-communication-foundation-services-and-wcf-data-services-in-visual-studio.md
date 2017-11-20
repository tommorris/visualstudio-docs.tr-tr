---
title: Windows Communication Foundation Hizmetleri ve Visual Studio'da WCF Veri Hizmetleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- services, WCF Data
- WCF services, binding to
- WCF services, asynchronous service methods
- service references [Visual Studio]
- WCF Data Services
- asynchronous calls
- service references [Visual Studio], type sharing
- endpoints [WCF]
- asynchronous service methods
- service references [Visual Studio] endpoints
- WCF services, type sharing
- Windows Communication Foundation, in Visual Studio
- services, WCF
- WCF service, Visual Studio
- data services, WCF
- services, in Visual Studio
- data binding [Visual Studio], WCF
- service endpoints [Visual Studio]
- service references [Visual Studio], asynchronous calls
- services, Windows Communication Foundation
- type sharing in WCF services
- WCF services, endpoints
- service method, called asynchronously[Visual Studio]
ms.assetid: d56f12cb-e139-4fec-b3e4-488383356642
caps.latest.revision: "26"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 39c9ac7b1cbed8c64ee3b87fde4c990f998157a4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="windows-communication-foundation-services-and-wcf-data-services-in-visual-studio"></a>Visual Studio'da Windows Communication Foundation Hizmetleri ve WCF Veri Hizmetleri
Windows Communication Foundation (WCF) ile çalışmak için Visual Studio araçları sağlar ve [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)], oluşturmak için Microsoft teknolojilerini dağıtılmış uygulamalar. Bu konuda Hizmetleri'nden tanıtılmaktadır bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] perspektif. Tam belgeler için bkz: [WCF Veri Hizmetleri 4.5](/dotnet/framework/data/wcf/index).  
  
## <a name="what-is-wcf"></a>WCF nedir?  
 [!INCLUDE[vsindigo](../data-tools/includes/vsindigo_md.md)]güvenli, güvenilir, işlenen ve birlikte çalışabilir dağıtılmış uygulamaları oluşturmak için birleştirilmiş bir çerçevedir. ASMX Web Hizmetleri, .NET uzaktan iletişim, Kurumsal Hizmetleri (DCOM) ve MSMQ gibi eski işlemler arası iletişimi teknolojileri değiştirir. WCF bu teknolojiler birleşik bir programlama modeli altında işlevselliğini bir araya getirir. Bu, dağıtılmış uygulamaları geliştirme deneyimi kolaylaştırır.  
  
#### <a name="what-are-wcf-data-services"></a>WCF Veri Hizmetleri nelerdir  
 [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)]Açık veri (OData) protokolü standart uygulamasıdır.  Tablo verisi REST API'leri gibi standart HTTP fiillerini kullanarak veri GET, POST, PUT veya silme döndürülecek sağlayarak, bir dizi kullanıma WCF veri hizmetleri sağlar. Sunucu tarafında WCF Veri Hizmetleri tarafından değiştirilen [ASP.NET Web API](http://www.asp.net/web-api) yeni OData hizmetleri oluşturmak için. WCF Veri Hizmetleri İstemci Kitaplığı Visual Studio .NET uygulamasından OData Hizmetleri'nde tüketimi için iyi bir seçimdir olmaya devam (**proje &#124; Hizmet Başvurusu Ekle**). Daha fazla bilgi için bkz: [WCF Veri Hizmetleri 4.5](http://go.microsoft.com/fwlink/?LinkID=119952).  
  
### <a name="wcf-programming-model"></a>WCF programlama modeli  
 WCF programlama modeli iki varlık arasındaki iletişimi temel alır: bir WCF hizmeti ve bir WCF istemcisi. Programlama modeli içinde kapsüllenir <xref:System.ServiceModel> ad alanında [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].  
  
#### <a name="wcf-service"></a>WCF Hizmeti  
 Bir WCF hizmeti, hizmet ve istemci arasındaki sözleşmesini tanımlayan bir arabirim dayanır. İle işaretlenen bir <xref:System.ServiceModel.ServiceContractAttribute> aşağıdaki kodda gösterildiği gibi öznitelik:  
  
 [!code-csharp[WCFWalkthrough#6](../data-tools/codesnippet/CSharp/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio_1.cs)]
 [!code-vb[WCFWalkthrough#6](../data-tools/codesnippet/VisualBasic/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio_1.vb)]  
  
 [!code-csharp[WCFWalkthrough#1](../data-tools/codesnippet/CSharp/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio_2.cs)]
 [!code-vb[WCFWalkthrough#1](../data-tools/codesnippet/VisualBasic/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio_2.vb)]  
  
 İşlevler veya bunlarla işaretleyerek bir WCF hizmeti tarafından sunulan yöntemler tanımladığınız bir <xref:System.ServiceModel.OperationContractAttribute> özniteliği. Bileşik türüyle işaretleyerek serileştirilmiş veriler Ayrıca, getirebilir bir <xref:System.Runtime.Serialization.DataContractAttribute> özniteliği. Bu bir istemcisinde veri bağlama sağlar.  
  
 Bir arabirim ve yöntemlerinden tanımlandıktan sonra bunların arabirimini uygulayan bir sınıf içinde kapsüllenir. Tek bir WCF Hizmeti sınıf birden çok hizmet sözleşmeleri uygulayabilirsiniz.  
  
 Tüketim ne aracılığıyla olarak bilinen için bir WCF Hizmeti kullanıma sunulan bir *endpoint*. Uç nokta hizmetiyle iletişim kurmak için tek yolu sağlar; diğer sınıflarıyla gibi doğrudan bir başvuru hizmetine erişilemiyor.  
  
 Bir uç nokta bir adresi, bağlama ve bir sözleşme oluşur. Hizmet bulunduğu adresi tanımlar; Bu, bir URL, bir FTP adresi veya bir ağ veya yerel yol olabilir. Bir bağlama hizmetiyle iletişim biçimini tanımlar. WCF bağlamaları, HTTP veya FTP, Windows kimlik doğrulaması veya kullanıcı adları ve parolalar gibi bir güvenlik mekanizması gibi bir protokolü belirtmek için çok yönlü modeli sağlar ve çok daha fazlası. Bir sözleşme WCF hizmet sınıfı tarafından sunulan işlemlerini içerir.  
  
 Birden çok uç nokta için tek bir WCF Hizmeti gösterilebilir. Bu, farklı şekillerde aynı hizmetiyle iletişim kurmak farklı istemcilerin sağlar. Örneğin, bir bankacılık hizmet bir uç nokta çalışanlar ve başka bir dış müşterileri için her bağlama, farklı bir adresi kullanarak sağlayın ve/veya sözleşme.  
  
#### <a name="wcf-client"></a>WCF istemcisi  
 Bir WCF istemcisi oluşan bir *proxy* bir WCF Hizmeti ile iletişim kurmak bir uygulama sağlar ve bir uç noktayla eşleşen bir uç nokta hizmet için tanımlanmış. Proxy app.config dosyasında istemci tarafında oluşturulur ve türleri ve hizmet tarafından sunulan yöntemleri hakkında bilgi içerir. Birden çok uç nokta kullanıma hizmetler için istemci HTTP üzerinden iletişim kurar ve Windows kimlik doğrulaması kullanmak için bu gibi bir durumda gereksinimlerine en uygun birini seçebilirsiniz.  
  
 Bir WCF istemcisi oluşturulduktan sonra başka bir nesneyi gibi kodunuzda hizmeti başvuru. Örneğin, arama için `GetData` yazma aşağıdakine benzer bir kod daha önce gösterilen yöntemi:  
  
 [!code-csharp[WCFWalkthrough#3](../data-tools/codesnippet/CSharp/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio_3.cs)]
 [!code-vb[WCFWalkthrough#3](../data-tools/codesnippet/VisualBasic/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio_3.vb)]  
  
## <a name="wcf-tools-in-visual-studio"></a>Visual Studio'da WCF araçları  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]WCF hizmetleri ve WCF istemcileri oluşturmanıza yardımcı olacak araçlar sağlar. Araçlar izlenecek yol için bkz: [izlenecek yol: Windows Forms'ta basit bir WCF hizmeti oluşturma](../data-tools/walkthrough-creating-a-simple-wcf-service-in-windows-forms.md).  
  
### <a name="creating-and-testing-wcf-services"></a>Oluşturma ve sınama WCF hizmetleri  
 WCF kullanabilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] şablonlar hızlı bir şekilde kendi hizmet oluşturmak için bir temel olarak. Hata ayıklama ve hizmet sınamak için WCF hizmeti otomatik ana bilgisayarı ve WCF Test İstemcisi ardından kullanabilirsiniz. Bu araçları birlikte hızlı ve kolay hata ayıklama ve test döngüsü sağlar ve barındırma modeli için erken bir aşamada yürütme gerekliliğini ortadan kaldırmak.  
  
#### <a name="wcf-templates"></a>WCF şablonları  
 WCF [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] şablonları, hizmet geliştirme için bir temel sınıf yapısı sağlar. Çeşitli WCF şablonlar kullanılabilir **Yeni Proje Ekle** iletişim kutusu. Bunlar, WCF Hizmeti kitaplık projeleri, WCF Hizmeti Web siteleri ve WCF Hizmeti öğe şablonları içerir.  
  
 Bir şablon seçtiğinizde, dosyaları bir hizmet sözleşmesini, bir hizmet uygulaması ve hizmeti bir yapılandırma için eklenir. Hizmet, basit bir "Hello World" türü oluşturma, tüm gerekli öznitelikler zaten eklenir ve herhangi bir kod yazmak zorunda kalmadığımıza. Elbette, İşlevler ve gerçek dünya hizmetiniz için yöntemler sağlamak üzere kod eklemek istediğiniz ancak temel foundation şablonları sağlar.  
  
 WCF şablonları hakkında daha fazla bilgi için bkz: [WCF Visual Studio şablonları](/dotnet/framework/wcf/wcf-vs-templates).  
  
#### <a name="wcf-service-host"></a>WCF hizmet konağı  
 Başlattığınızda [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] hata ayıklayıcı (F5 tuşuna basarak) bir WCF Hizmeti projesi için WCF hizmet ana bilgisayarı Aracı hizmeti yerel olarak barındırmak için otomatik olarak başlatılır. WCF hizmet konağı bir WCF Hizmeti projesini Hizmetleri'nde numaralandırır, projenin yapılandırmayı yükler ve bulduğu her hizmet için bir konak başlatır.  
  
 WCF hizmet ana bilgisayarı kullanarak ek kod yazma veya belirli bir ana bilgisayara geliştirme sırasında gerçekleştirmeden olmadan bir WCF Hizmeti sınayabilirsiniz.  
  
 WCF hizmet ana bilgisayarı hakkında daha fazla bilgi için bkz: [WCF hizmet Konağı (WcfSvcHost.exe)](/dotnet/framework/wcf/wcf-service-host-wcfsvchost-exe).  
  
#### <a name="wcf-test-client"></a>WCF Test İstemcisi  
 WCF Test İstemcisi aracı, giriş test parametreleri, bir WCF hizmetine giriş gönderme imkan sağlar ve hizmet geri gönderdiği yanıt görüntüleyin. WCF hizmet ana bilgisayarı ile birleştirdiğinizde deneyimi sınama kullanışlı bir hizmet sağlar. Aracı olan sürücüde yüklü Visual Studio 2015 için C: Burada \Common7\IDE klasöründe bulunabilir: **C:\Program Files (x86) \Microsoft Visual Studio 14.0\Common7\IDE\\**.  
  
 Bir WCF Hizmeti projesini hata ayıklamak için F5 tuşuna bastığınızda, WCF Test İstemcisi açar ve yapılandırma dosyasında tanımlanmış hizmet uç noktaları listesini görüntüler. Parametreleri test ve hizmeti başlatın ve sürekli test ve hizmetinizi doğrulamak için bu işlemi yineleyin.  
  
 WCF Test İstemcisi hakkında daha fazla bilgi için bkz: [WCF Test İstemcisi (WcfTestClient.exe)](/dotnet/framework/wcf/wcf-test-client-wcftestclient-exe).  
  
### <a name="accessing-wcf-services-in-visual-studio"></a>Visual Studio'da WCF hizmetlerine erişme  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]WCF istemcileri, otomatik olarak bir proxy ve Hizmetleri kullanarak eklemek için bir uç nokta oluşturma oluşturma görevini basitleştirir **hizmet Başvurusu Ekle** iletişim kutusu. Tüm gerekli yapılandırma bilgilerini app.config dosyasına eklenir. Çoğu süresini tüm yapmanız gereken olan örneği hizmet bunu kullanmak için.  
  
 **Hizmet Başvurusu Ekle** iletişim kutusu için bir hizmet adresini girin ya da çözümünüz içinde tanımlı bir hizmet için aranacak sağlar. İletişim kutusu, hizmetleri ve bu hizmetleri tarafından sağlanan işlemleri listesini döndürür. Ayrıca kod Hizmetleri'nde başvurur ad alanı tanımlamanızı sağlar.  
  
 **Yapılandırma hizmeti başvuruları** iletişim kutusu, bir hizmet yapılandırmasını özelleştirmenizi sağlar. Bir hizmet için adresini değiştirmek, erişim düzeyi, zaman uyumsuz davranışı ve ileti sözleşme türlerini belirtin ve türü yeniden yapılandırın.  
  
## <a name="how-to-select-a-service-endpoint"></a>Nasıl yapılır: hizmet uç noktası seçin  
Bazı Windows Communication Foundation (WCF) hizmetlerini istemci hizmetiyle iletişim kurabilir birden çok uç noktalarını kullanıma sunar. Örneğin, bir hizmeti bir HTTP bağlama ve kullanıcı adı kullanan bir uç nokta doğurabilir / parola güvenlik ve FTP ve Windows kimlik doğrulaması kullanır ikinci bir uç nokta. İkinci bir intranet üzerinde kullanılabilir ancak ilk uç hizmetinden bir güvenlik duvarı dışındaki erişim uygulamalar tarafından kullanılıyor olabilir.  
  
Böyle bir durumda, belirttiğiniz `endpointConfigurationName` bir parametre olarak bir hizmet başvurusu Oluşturucusu.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
#### <a name="to-select-a-service-endpoint"></a>Hizmet uç noktası seçmek için  
  
1.  Çözüm Gezgini'nde proje düğümüne sağ tıklayıp seçerek bir WCF hizmeti bir başvuru ekleyin **hizmet Başvurusu Ekle**.
  
2.  Kod Düzenleyicisi'nde hizmet başvurusu için bir oluşturucu ekleyin:  
  
    ```vb  
    Dim proxy As New ServiceReference.Service1Client(  
    ```  
  
    ```csharp  
    ServiceReference.Service1Client proxy = new ServiceReference.Service1Client(  
    ```  
  
    > [!NOTE]
    >  Değiştir *ServiceReference* değiştirin ve hizmet başvurusu için ad alanı ile *Service1Client* hizmet adı.  
  
3.  Oluşturucu aşırı ile bir IntelliSense listesi görüntülenir. Seçin `endpointConfigurationName As String` aşırı yükleme.  
  
4.  Aşırı yazın `=` *ConfigurationName*, burada *ConfigurationName* kullanmak istediğiniz uç nokta adı.  
  
    > [!NOTE]
    >  Kullanılabilir uç nokta adlarını bilmiyorsanız, app.config dosyasında bulabilirsiniz.  
  
#### <a name="to-find-the-available-endpoints-for-a-wcf-service"></a>Bir WCF hizmeti için kullanılabilir uç noktalarını bulmak için  
  
1.  İçinde **Çözüm Gezgini**, hizmet başvurusu içeren projeye app.config dosyasını sağ tıklatın ve ardından **açık**. Dosya Kod Düzenleyicisi'nde görüntülenir.  
  
2.  Arama `<Client>` dosyasındaki etiketi.  
  
3.  Altındaki arama `<Client>` ile başlayan bir etiket için etiket `<Endpoint>`.  
  
     Hizmet başvurusu birden çok uç nokta sağlıyorsa, olacaktır iki veya daha fazla `<Endpoint` etiketler.  
  
4.  İçinde `<EndPoint>` bulacaksınız etiketi bir `name="` *SomeService* `"` parametre (burada *SomeService* bir uç nokta adı temsil eder). Bu uç nokta için geçirilen addır `endpointConfigurationName As String` aşırı yüklemesini hizmet başvurusu için bir oluşturucu.  
  
## <a name="how-to-call-a-service-method-asynchronously"></a>Nasıl yapılır: bir hizmet yöntemini zaman uyumsuz olarak çağırma  
Windows Communication Foundation (WCF) hizmetlerini çoğu yöntemleri zaman uyumlu veya zaman uyumsuz olarak çağrılabilir. Zaman uyumsuz olarak bir yöntemi çağırma yavaş bir bağlantı üzerinden çalıştığında yöntemi çağrıldığından sırasında çalışmaya devam etmek, uygulamanızı sağlar.  
  
Hizmet başvurusu projeye eklendiğinde, varsayılan olarak, zaman uyumlu yöntemleri çağırmak için yapılandırılır. Bir ayarı değiştirerek zaman uyumsuz yöntemleri çağırma davranışını değiştirebilirsiniz **hizmet başvurusu Yapılandır** iletişim kutusu.  
  
> [!NOTE]
>  Bu seçenek, bir hizmet başına temelinde ayarlanır. Bir hizmet için bir yöntem zaman uyumsuz olarak çağrılırsa, tüm yöntemleri zaman uyumsuz olarak çağrılmalıdır.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
#### <a name="to-call-a-service-method-asynchronously"></a>Zaman uyumsuz olarak bir hizmet yöntemini çağırmak için  
  
1.  İçinde **Çözüm Gezgini**, hizmet başvurusu seçin.  
  
2.  Üzerinde **proje** menüsünde tıklatın **hizmet başvurusu yapılandırma**.  
  
3.  İçinde **hizmet başvurusu Yapılandır** iletişim kutusunda **zaman uyumsuz işlemler oluşturmak** onay kutusu.  
  
## <a name="how-to-bind-data-returned-by-a-service"></a>Nasıl yapılır: bir hizmet tarafından döndürülen veri bağlama  
Yalnızca bir denetim için başka bir veri kaynağını bağlayabilirsiniz gibi bir denetim için bir Windows Communication Foundation (WCF) hizmet tarafından döndürülen veri bağlayabilirsiniz. Hizmet verileri döndürmek bileşik türler içeriyorsa bir WCF hizmetine başvuru eklediğinizde, bunlar otomatik olarak eklenir **veri kaynakları** penceresi.  
  
#### <a name="to-bind-a-control-to-single-data-field-returned-by-a-wcf-service"></a>Bir WCF hizmeti tarafından döndürülen tek veri alan bir denetim bağlamak için  
  
1.  Üzerinde **veri** menüsünde tıklatın **veri kaynaklarını Göster**. **Veri kaynakları** penceresi görünür.  
  
2.  İçinde **veri kaynakları** penceresinde, hizmet başvurusu düğümünü genişletin. Hizmet tarafından döndürülen tüm bileşik türler görüntülenir.  
  
3.  Bir tür için bir düğümünü genişletin. Bu tür veri alanlarında görüntülenir.  
  
4.  Bir alan seçin ve veri türü için kullanılabilir olan denetimlerin bir listesini görüntülemek için açılan oku tıklatın.  
  
5.  Bağlamak istediğiniz denetim türünü tıklatın.  
  
6.  Alan bir form üzerine sürükleyin. İle birlikte form denetimi eklenecek bir <xref:System.Windows.Forms.BindingSource> bileşeni ve bir <xref:System.Windows.Forms.BindingNavigator> bileşeni.  
  
7.  Diğer için 6 alanları olsa 4 arasındaki adımları yineleyin bağlamak istediğiniz.  
  
#### <a name="to-bind-a-control-to-composite-type-returned-by-a-wcf-service"></a>Bileşik türü WCF hizmet tarafından döndürülen bir denetim bağlamak için  
  
1.  Üzerinde **veri** menüsünde, select **veri kaynaklarını Göster**. **Veri kaynakları** penceresi görünür.  
  
2.  İçinde **veri kaynakları** penceresinde, hizmet başvurusu düğümünü genişletin. Hizmet tarafından döndürülen tüm bileşik türler görüntülenir.  
  
3.  Bir tür için bir düğüm seçin ve kullanılabilir seçeneklerin bir listesini görüntülemek için açılan oku tıklatın.  
  
4.  Ya da tıklatın **DataGridView** kılavuzda verileri görüntülemek için veya **ayrıntıları** tek tek denetimlerinde verileri görüntülemek için.  
  
5.  Düğüm form üzerine sürükleyin. Denetimleri form ile birlikte eklenir bir <xref:System.Windows.Forms.BindingSource> bileşeni ve bir <xref:System.Windows.Forms.BindingNavigator> bileşeni.  
  
## <a name="how-to-configure-a-service-to-reuse-existing-types"></a>Nasıl yapılır: Varolan türleri yeniden kullanmak için bir hizmeti yapılandırmak  
Hizmet başvurusu projeye eklendiğinde, hizmette tanımlanan tüm türleri yerel projede üretilir. Bir hizmet kullanırken çoğu durumda, bu yinelenen türleri ortak oluşturur [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] türü veya türleri paylaşılan bir kitaplık içinde ne zaman tanımlanır.  
  
Bu sorunu önlemek için başvurulan derlemelerin türlerinde varsayılan olarak paylaşılır. Tür için bir veya daha fazla derlemeleri paylaşımı devre dışı bırakmak istiyorsanız, bu nedenle de yapabileceğiniz **Yapılandırma hizmeti başvuruları** iletişim kutusu.  
  
#### <a name="to-disable-type-sharing-in-a-single-assembly"></a>Tek bir bütünleştirilmiş kod paylaşımı türü devre dışı bırakmak için  
  
1.  İçinde **Çözüm Gezgini**, hizmet başvurusu seçin.  
  
2.  Üzerinde **proje** menüsünde tıklatın **hizmet başvurusu yapılandırma**.  
  
3.  İçinde **Yapılandırma hizmeti başvuruları** iletişim kutusunda **yeniden belirtilen başvurulan derlemelerin türlerinde**.  
  
4.  Türü paylaşımı etkinleştirmek istediğiniz her derlemesi için onay kutusunu seçin. Tür için derlemeyi paylaşımı devre dışı bırakmak için onay kutusunu temizleyin.  
  
#### <a name="to-disable-type-sharing-in-all-assemblies"></a>Tüm derlemelerde paylaşımı türü devre dışı bırakmak için  
  
1.  İçinde **Çözüm Gezgini**, hizmet başvurusu seçin.  
  
2.  Üzerinde **proje** menüsünde tıklatın **hizmet başvurusu yapılandırma**.  
  
3.  İçinde **Yapılandırma hizmeti başvuruları** iletişim kutusu, Temizle **yeniden başvurulan derlemelerin türlerinde** onay kutusu.  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[İzlenecek yol: Windows Forms'ta basit bir WCF hizmeti oluşturma](../data-tools/walkthrough-creating-a-simple-wcf-service-in-windows-forms.md)|Oluşturma ve WCF hizmetlerini kullanarak adım adım bir gösterim sağlar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|  
|[İzlenecek yol: bir WCF veri hizmetine WPF ve Entity Framework ile oluşturma](../data-tools/walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework.md)|Adım adım bir gösterim oluşturmak ve kullanmak nasıl sağlar [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] içinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|  
|[WCF geliştirme araçlarını kullanarak](/dotnet/framework/wcf/using-the-wcf-development-tools)|Oluşturma ve WCF hizmetlerinde test anlatılmaktadır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|  
||[Nasıl yapılır: ekleme, güncelleştirme veya bir WCF veri hizmeti başvurusunu kaldırma](../data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference.md)|Başvuru ve nasıl kullanılacağını anlatır [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] içinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|  
|[Hizmet başvurularında sorun giderme](../data-tools/troubleshooting-service-references.md)|Hizmet başvuruları ve bunları engelleme ile ortaya çıkabilecek bazı yaygın hatalar gösterir.|  
|[WCF hizmetlerinde hata ayıklama](../debugger/debugging-wcf-services.md)|Genel hata ayıklama sorunları ve WCF hizmetleri hata ayıklama sırasında karşılaşabileceğiniz teknikleri açıklar.|  
|[Windows Communication Foundation kimlik doğrulama hizmeti genel bakış](http://msdn.microsoft.com/Library/6e121a28-89e8-4974-88a8-70aaa6a7d52b)|WCF Web sitesi için bir rol hizmeti sağlamak için nasıl kullanılacağını açıklar.|  
|[İzlenecek yol: N katmanlı veri uygulaması oluşturma](../data-tools/walkthrough-creating-an-n-tier-data-application.md)|Türü belirtilmiş veri kümesi oluşturma ve birden çok projeye TableAdapter ve veri kümesi kodu ayırmak için adım adım yönergeler sağlar.|  
|[Hizmet başvurusu Yapılandır iletişim kutusu](../data-tools/configure-service-reference-dialog-box.md)|Kullanıcı arabirimi öğelerini açıklar **hizmet başvurusu Yapılandır** iletişim kutusu.|  
  
## <a name="reference"></a>Başvuru  
 <xref:System.ServiceModel>  
  
 <xref:System.Data.Services>  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [.NET için Visual Studio veri araçları](../data-tools/visual-studio-data-tools-for-dotnet.md)