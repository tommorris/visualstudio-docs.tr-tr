---
title: Mevcut bir SharePoint sitesinden öğeleri içeri aktarma | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.WSPImport.SelectionDependency
- VS.SharepointTools.WSPImport.SpecifyProjectSource
- VS.SharePointTools.WSPImport.SelectionItemsToImport
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, importing items
- SharePoint development in Visual Studio, importing .wsp files
- importing items [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 21ca61f29138aee5a4c22cbf872d6698d4180d50
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120444"
---
# <a name="import-items-from-an-existing-sharepoint-site"></a>Mevcut bir SharePoint sitesinden öğeleri içeri aktarma
  Yeni bir içerik türlerini ve alanların varolan SharePoint siteleri gibi öğeleri yeniden alma SharePoint çözüm paketi proje şablonu sağlar [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint çözüm. En alınan çözümler değişiklik yapmadan çalıştırabilirsiniz, ancak olup olmadığını bazı kısıtlamalar ve dikkate alınacak konular özellikle içeri aktardıktan sonra herhangi bir öğeyi değiştirin.  
  
> [!NOTE]  
>  Yeniden kullanılabilir iş akışlarını almak için yeniden kullanılabilir iş akışı içe proje şablonu kullanın. [!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)] [Yeniden kullanılabilir iş akışlarını içeri aktarma yönergeleri](../sharepoint/guidelines-for-importing-reusable-workflows.md).  
  
## <a name="supported-sharepoint-solutions"></a>Desteklenen SharePoint çözümleri
 [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)] tam olarak oluşturulan çözümleri alma destekleyen [!INCLUDE[wss_14_short](../sharepoint/includes/wss-14-short-md.md)] ve [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)].  
  
 [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)] Aşağıdaki uygulamalarda oluşturduğu çözümleri alma desteklemez:  
  
-   [!INCLUDE[winshare3](../sharepoint/includes/winshare3-md.md)]  
  
-   [!INCLUDE[offshare7](../sharepoint/includes/offshare7-md.md)]  
  
-   [!INCLUDE[vs_orcas_long](../sharepoint/includes/vs-orcas-long-md.md)]  
  
-   Microsoft SharePoint Designer 2007  
  
-   [!INCLUDE[vs_dev10_long](../sharepoint/includes/vs-dev10-long-md.md)]  
  
 Bu uygulamaları tarafından oluşturulan çözümler genellikle başarılı bir şekilde içeri aktarabilirsiniz olsa da bu işlevselliği test ve desteklenmiyor.  
  
## <a name="item-import-restrictions"></a>Öğe alma kısıtlamaları
 Mevcut bir SharePoint öğelerin çoğu alınabilir rağmen *.wsp* dosya, aşağıdaki öğeler desteklenmez ve düzgün çalışması için değişiklik gerektirebilir:  
  
-   BDC varlıklar  
  
-   İş akışı ilişkilendirme öğeleri kod  
  
-   Kod iş akışları  
  
-   Visual Web Bölümleri (.ascx)  
  
-   Web Hizmetleri (*.asmx*)  
  
-   İçerik türü bağlamaları  
  
-   Olay alıcıları  
  
-   Liste tanımları (Şablonları)  
  
-   Site tanımları  
  
 Bir çözümden aktardığınızda [!INCLUDE[wss_14_short](../sharepoint/includes/wss-14-short-md.md)] veya [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)], bu öğeler gelen otomatik olarak dışarıda bırakılır *.wsp* dosya. Ancak, diğer *.wsp* desteklenmeyen Araçları'ndan oluşturulan dosyaları, bu öğeler içerebilir. ("Desteklenen SharePoint çözümleri" bölümüne bakın.)  
  
## <a name="what-happens-when-you-import-a-solution"></a>Çözüm alma ne olur
 SharePoint çözüm paketi içe şablonu ile bir çözüm aldığınızda [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] tüm içeriğini kopyalar *.wsp* dosya ve mutabık kılmak ve sayıda ilişkileri ve başvurular arasında korumak için çalışır öğeleri ve mümkün olduğunca dosyalarla.  
  
 İçeri aktarılan öğelerin tümünü kopyalama karşılık gelen klasörlerde **Çözüm Gezgini**. Örneğin, içerik türleri klasörü altında görünür **içerik türlerine** ve liste örnekleri görünür altında **liste örnekleri**. İçeri aktarılan bir öğesiyle ilişkili dosyalar da öğesi'nin klasörüne kopyalanır. Örneğin, içeri aktarılan liste örneği modüller, formlar ve ASPX sayfalar içerir.  
  
### <a name="dependent-items"></a>Bağımlı öğeler
 SharePoint çözüm paketi İçeri Aktar Sihirbazı'nı, ancak bağımlı alt öğeleri öğenin seçerseniz, bir ileti kutusu bağımlı öğeler de almadan önce seçilmiş olması gerekir bildirir.  
  
### <a name="what-are-features"></a>Özellikler nelerdir?
 SharePoint Designer kullanıcıları adlı beklenmeyen dosya karşılaşabilirsiniz *özellikleri*, içeri aktarılan çözümleri görünür **Çözüm Gezgini.** SharePoint Designer çözümündeki özellikleri karşın, bunların görünümden gizlenmiş. Özellikleri görünür şimdi [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
 SharePoint öğeler için kapsayıcı özellikleridir. Her bir özelliğin içerik türleri ve içerdiği liste tanımları gibi her bir öğeyi başvuru tutar. Çözümünüz içeri aktardığınızda [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] tüm içeri aktarılan öğeleri için özellikleri ayarlar ve dosyalar için özellik öğesi ilişkileri korumak çalışır. Başvuruları çözümlenemedi herhangi bir dosya put **diğer içe aktarılan dosyaları** klasör.  
  
 Özellikleri hakkında daha fazla bilgi için bkz: [geliştirmek SharePoint çözümlerini](../sharepoint/developing-sharepoint-solutions.md) ve [özellikleriyle çalışma](http://go.microsoft.com/fwlink/?LinkID=147704).  
  
### <a name="handle-special-cases"></a>Özel durumları işleme
 Bazı durumlarda, Visual Studio öğe bağımlı dosyalarla hale getirilemiyor. Tüm dosyaları [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] çözümlenemedi klasörü altında görünür **diğer içe aktarılan dosyaları**. Ayrıca, kendi **DeploymentType** özelliklerinin **NoDeployment** böylece çözümüyle dağıtılmaz.  
  
 ExpenseForms listesi tanımını içe aktarırsanız, örneğin, bu adı taşıyan bir liste tanımı altında görünür **liste tanımları** klasöründe **Çözüm Gezgini** ile birlikte kendi  *Elements.xml* ve *Schema.xml* dosyaları. Ancak, ilişkili ASPX ve HTML formları adlı bir klasöre yerleştirilebilir **ExpenseForms** altında **diğer içe aktarılan dosyaları** klasör. Alma işlemini tamamlamak için bu dosyaları ExpenseForms listesi tanımı'nda altında taşıma **Çözüm Gezgini** değiştirip **DeploymentType** özelliği her bir dosyanın **NoDeployment** için **ElementFile**.  
  
 Olay alıcıları alırken *Elements.xml* dosyayı doğru konuma kopyalanır, ancak çözümüyle dağıtır, el ile derleme çözüm paketinde içermesi gerekir. [!INCLUDE[crabout](../sharepoint/includes/crabout-md.md)] Bunu yapmak için bkz: nasıl [nasıl yapılır: ek derlemeler ekleyip](../sharepoint/how-to-add-and-remove-additional-assemblies.md).  
  
 İş akışlarını içeri aktarırken formlara kopyalanır **diğer içe aktarılan dosyaları** klasör. Varsa *.wsp* dosyasını içeren bir Web şablonu, başlangıç sayfası olarak ayarla **Çözüm Gezgini**.  
  
## <a name="import-fields-and-property-bags"></a>İçeri aktarma alanları ve özellik paketleri
 Birden çok alan bulunduğu bir çözümü içe aktardığınızda, ayrı alan tanımlarını tümünün tek bir birleştirilmiş *Elements.xml* bir düğümü altındaki dosya **Çözüm Gezgini** adlı **alanları** . Benzer şekilde, tüm özellik paketi girişleri birleştirilir bir *Elements.xml* dosya olarak adlandırılan bir düğüm altında **PropertyBags**.  
  
 SharePoint alanlarında metin, Boole veya arama gibi belirtilen veri türünde sütunlar'dır. Daha fazla bilgi için bkz: [yapı taşı: sütunlar ve alan türleri](http://go.microsoft.com/fwlink/?LinkId=182304). Özellik paketleri, SharePoint, her şeyi bir gruba bir SharePoint sitesinde bir liste nesneleri için özellikler eklemenize olanak tanır. Özellik paketi özellik adları ve değerleri karma tablosu uygulanır. Daha fazla bilgi için bkz: [SharePoint yapılandırmasını yönetmek](http://go.microsoft.com/fwlink/?LinkId=182296) veya [SharePoint özellik paketi ayarları](http://go.microsoft.com/fwlink/?LinkId=182297).  
  
## <a name="delete-items-in-the-project"></a>Proje öğeleri silin
 SharePoint çözümlerini çoğu öğeler, bir veya daha fazla bağımlı öğeler içerir. Örneğin, liste örnekleri içerik türlerine bağlıdır ve alanları içerik türlerine bağlıdır. Bir SharePoint çözüm içeri aktardıktan sonra [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] çözümü dağıtma girişiminde kadar öğeyi çözümde, ancak kendi bağımlı öğeleri, silerseniz, tüm başvuru sorunları bilgilendirmez. Örneğin, bir içerik türüne bağlıdır bir liste örneği içeri aktarılan bir çözüm varsa ve bu içerik türünü silmek, dağıtımda bir hata oluşabilir. Bağımlı öğesi SharePoint sunucusu üzerinde mevcut değilse hata oluşur. Silinmiş bir öğeyi de ilgili özellik paketi varsa, benzer şekilde, bu özellik paketi girişleri silin **PropertyBags** *Elements.xml* dosya. Bu nedenle, içeri aktarılan bir çözümden öğeleri silin ve dağıtım hataları alırsanız bağımlı öğeler de silinecek gerekip gerekmediğini denetleyin.  
  
## <a name="restore-missing-feature-attributes"></a>Eksik özellik öznitelikleri geri yükleme
 Çözümler içe aktarırken, bazı isteğe bağlı özellik öznitelikleri içeri aktarılan özellik bildirimden göz ardı edilir. Yeni özellik dosyası içinde bu özniteliklerin geri yüklemek istiyorsanız, yeni bir özellik bildirimi özgün özellik dosyasına karşılaştırarak eksik öznitelikleri tanımlamak ve konu'ndaki yönergeleri izleyin [nasıl yapılır: bir SharePoint özelliğiniözelleştirme](../sharepoint/how-to-customize-a-sharepoint-feature.md).  
  
## <a name="deployment-conflict-detection-is-not-performed-on-built-in-list-instances"></a>Dağıtım çakışma algılaması yerleşik listesi örneklerinde gerçekleştirilmez
 [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)] Dağıtım çakışma algılaması (SharePoint ile gelen diğer bir deyişle, varsayılan liste örnekleri) yerleşik listesi örneklerinde gerçekleştirmez. Çakışma algılaması gerçekleştirme değil, SharePoint yerleşik listesi örneklerinde üzerine yazılmasını önlemek için yapılır. Hala örnekleridir yerleşik listesi dağıtılan veya güncelleştirildi, ancak hiçbir zaman silinmiş veya üzerine. [!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)] [SharePoint paketleme ve dağıtım sorunlarını giderme](../sharepoint/troubleshooting-sharepoint-packaging-and-deployment.md).  
  
## <a name="import-sharepoint-server-2010-workflows"></a>SharePoint Server 2010 iş akışlarını içeri aktarma
 İçinde oluşturulan bir iş akışını içeri aktarırsanız [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)], onu dağıttıktan sonra düzgün çalışmaz. Belirli derlemeleri eksik olduğu için iş akışı düzgün çalışmaz ve [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)] iş akışlarınızı içeren şu anda desteklenmez InfoPath formları [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] iş akışı çözümleri. Ancak, içeri aktarılan [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)] başvuruları ekleme gibi bazı öğeler düzelttikten sonra düzgün çalışması için iş akışları yapılabilir [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)] derlemeler ve formlara yeniden bağlanıyor. [!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)] [SharePoint Server 2010 iş akışlarını içeri aktarma](http://go.microsoft.com/fwlink/?LinkId=182226).  
  
## <a name="item-name-character-limit"></a>Öğe adı karakter sınırı
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Proje ve proje öğesi adları için yol dahil, toplam 260 karakterlik bir sınırı vardır. Bir öğe adı bu sınırı aşarsa, bir çözüm içe aktarırken, hata iletisi:  
  
 **Belirtilen yol, dosya adı veya her ikisini birden çok uzun. Tam dosya adı 260 karakterden az olmalıdır ve dizin adı 248 karakterden kısa olmalıdır.**  
  
 Bu hatayı alırsınız, öğe oluşturulmaz. Bu sorun, içe aktarılan modüllerle çoğunlukla oluşur. Bu sorunu önlemek için aşağıdakileri yapın:  
  
-   Onları girerken, projeniz için kısa adlar kullanmak **Yeni Proje Ekle** iletişim kutusu.  
  
-   Kök klasör yolu kısaltmak amacıyla mümkün olduğunca yakın bir yerde projesi oluşturun.  
  
## <a name="the-sharepointproductversion-attribute"></a>SharePointProductVersion özniteliği
 SharePoint daha önceki bir sürümünde oluşturulan gibi bir çözüm içe aktarırsanız [!INCLUDE[winshare3](../sharepoint/includes/winshare3-md.md)] veya [!INCLUDE[offshare7](../sharepoint/includes/offshare7-md.md)], paket bildirimi SharePointProductVersion öznitelik değeri için 12.0 değiştirin ya da tüm içeri aktarılan Web'e betik Yöneticisi denetim ekleme sayfalar ve bırakın SharePointProductVersion 14.0 için ayarlayın. Aksi takdirde, içeri aktarılan Web forms SharePoint'te görüntülenmez.  
  
### <a name="background"></a>Arka Plan  
 Çözümlerinde [!INCLUDE[wss_14_short](../sharepoint/includes/wss-14-short-md.md)] ve [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)] SharePointProductVersion adlı bir öznitelik içerir. SharePoint bu öznitelik, paket bildirimleri SharePoint çözüm için tasarlanmıştır sürümünü belirlemek için kullanır. İki 12.0 ve geçerli 14.0 değerlerdir. Öğe için tasarlanmıştır 12.0 değeri gösterir [!INCLUDE[winshare3](../sharepoint/includes/winshare3-md.md)] veya [!INCLUDE[offshare7](../sharepoint/includes/offshare7-md.md)]; öğesi için tasarlanmıştır 14.0 değerini gösteriyorsa [!INCLUDE[wss_14_short](../sharepoint/includes/wss-14-short-md.md)] veya [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)].  
  
 ASPX sayfaları işlenirken Gelişmiş güvenlik için [!INCLUDE[wss_14_short](../sharepoint/includes/wss-14-short-md.md)] ve [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)] tüm ASPX veya ana sayfa bir komut dosyası Yöneticisi denetimi içermesini gerektirir. Komut dosyası Yöneticisi hakkında daha fazla bilgi için bkz: [ScriptManager denetimine genel bakış](http://go.microsoft.com/fwlink/?LinkID=169399). Komut dosyası Yöneticisi denetimi içinde kullanılabilir olmadığından [!INCLUDE[winshare3](../sharepoint/includes/winshare3-md.md)] ve [!INCLUDE[offshare7](../sharepoint/includes/offshare7-md.md)], bir eklenmelidir herhangi [!INCLUDE[winshare3](../sharepoint/includes/winshare3-md.md)] veya [!INCLUDE[offshare7](../sharepoint/includes/offshare7-md.md)] sürümüne yükseltilir sayfa [!INCLUDE[wss_14_short](../sharepoint/includes/wss-14-short-md.md)] veya [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)]. Bir standart ana sayfaya zaten eklendiği standart bir ana sayfa kullanma ASPX sayfaları bir komut dosyası manager denetim gerektirmez. Bir ana sayfa kullanmayın veya özel bir ana sayfa kullanan ASPX sayfaları çalışmak için bir komut dosyası denetimi ancak eklemelisiniz [!INCLUDE[wss_14_short](../sharepoint/includes/wss-14-short-md.md)] veya [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)].  
  
 Alırken bir komut dosyası Yöneticisi denetimi yokluğu bir sorun olabilir bir [!INCLUDE[winshare3](../sharepoint/includes/winshare3-md.md)] veya [!INCLUDE[offshare7](../sharepoint/includes/offshare7-md.md)] içine proje [!INCLUDE[vs_dev10_long](../sharepoint/includes/vs-dev10-long-md.md)], tüm yeni projeler SharePointProductVersion özniteliğinin 14.0 için ayarlanır. Bir komut dosyası Yöneticisi olmadan Web formu olan yükseltilmiş projesini dağıtırsanız, formun SharePoint'te görüntülenmez.  
  
## <a name="see-also"></a>Ayrıca bkz.
 [İzlenecek yol: mevcut bir SharePoint sitesinden öğeleri içeri aktarma](../sharepoint/walkthrough-import-items-from-an-existing-sharepoint-site.md)   
 [Yeniden kullanılabilir iş akışlarını içeri aktarma yönergeleri](../sharepoint/guidelines-for-importing-reusable-workflows.md)   
 [İzlenecek yol: bir SharePoint Tasarımcısı yeniden kullanılabilir iş akışını Visual Studio'ya içeri aktarma](../sharepoint/walkthrough-import-a-sharepoint-designer-reusable-workflow-into-visual-studio.md)   
 [Nasıl yapılır: bir SharePoint projesine mevcut bir BDC modeli dosyası ekleme](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md)  
