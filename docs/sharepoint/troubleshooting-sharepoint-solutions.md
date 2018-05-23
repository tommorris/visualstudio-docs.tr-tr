---
title: SharePoint çözümlerinde sorun giderme | Microsoft Docs
ms.custom: ''
ms.date: 02/22/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- Microsoft.VisualStudio.Tools.SharePoint.Errors.Debugging
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, troubleshooting
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 12de0ea2e9638c7ab523bbda0e623c84d0182aad
ms.sourcegitcommit: cc88ccc6aacebe497899fab05d243a65053e194c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2018
---
# <a name="troubleshooting-sharepoint-solutions"></a>SharePoint Çözümlerinde Sorun Giderme
  Aşağıdaki sorunları veya uyarıları kullanarak SharePoint çözümlerini hata ayıklarken oluşabilecek [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] hata ayıklayıcı. Daha fazla bilgi için bkz: [hata ayıklama SharePoint 2007 iş akışı çözümleri](http://msdn.microsoft.com/en-us/3a5392f3-66f3-48be-956e-02de23fa6247).
  
## <a name="token-restrictions-in-sandboxed-visual-web-parts"></a>Korumalı Visual Web Bölümleri belirteci kısıtlamaları  
 Korumalı çözümler Visual web bölümleri SharePoint çalışma zamanı destekleyen $SPUrl gibi standart belirteçleri işleyemiyor. Sonuç olarak, URL çözülmüş değildir ve sizin için bir komut dosyası öğesinde doğrudan gibi aşağıdaki örnekte başvurursanız visual web bölümü tasarımcısının Tasarım görünümünde içeriği önizlemesini yapamazsınız:  
  
```xml  
<script src="<% $SPUrl:~site/SiteAssets/ListOperations.js %>"></script>  
```  
  
 Bu sınırlamaya geçici bir çözüm ve belirteç çözümlemek için kendisine değişmez değerleri kullanarak bakın:  
  
```xml  
<asp:literal ID="Literal1" runat="server" Text="<script src='" />  
<asp:literal ID="Literal2" runat="server" Text="<% $SPUrl:~site/SiteAssets/ListOperations.js %>" />  
<asp:literal ID="Literal3" runat="server" Text="' type='text/javascript' ></script>" />  
```  
  
## <a name="character-restrictions-in-names-of-projects-and-project-items"></a>Proje ve proje öğeleri adlarında karakter kısıtlamaları  
 Proje ve proje öğeleri adları, yalnızca SharePoint 2010 dağıtım yolunda geçerli karakterler içerebilir. Diğer bir karakterlere izin verilir.  
  
### <a name="error-message"></a>Hata İletisi  
 "Geçersiz karakterler" hata iletisi.  
  
### <a name="resolution"></a>Çözüm  
 SharePoint projeleri ve proje öğeleri adları yalnızca şu karakterleri kullanın:  
  
-   Alfasayısal ASCII karakterleri  
  
-   Alan  
  
-   Nokta (.)  
  
-   Virgül (,)  
  
-   Alt çizgi (_)  
  
-   Tire (-)  
  
-   Ters eğik çizgi (\\)  
  
 Bir proje paketlendiğinde bir doğrulama kuralı dağıtmakta her dosya için dağıtım yolu özelliği yalnızca bu geçerli karakterler içerdiğinden doğrular.  
  
## <a name="errors-when-creating-custom-fields"></a>Özel alanlar oluştururken hataları  
 İçinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], özel alanlar, XML'de tanımlanır. Bir alan tanımlı değil veya belirli bir biçimi kullanarak başvurulan hatalar oluşabilir.  
  
### <a name="error-message"></a>Hata İletisi  
 Paketleme zamanında "Geçersiz karakterler" hata iletisi.  
  
### <a name="resolution"></a>Çözüm  
 Bir alan tanımı kimliği, aşağıdaki örnekte gösterildiği gibi köşeli parantez ile çevrelenmiş bir GUID olması gerekir:  
  
```xml  
<Field ID="{5744d18c-305e-4632-8bd1-09d134f4830d}"   
    Type="Note"   
    Name="PatientName"   
    DisplayName="Patient Name"   
    Group="A Custom Group">  
</Field>.  
```  
  
 Aşağıdaki örnekte gösterildiği gibi bir içerik türünde bir alan başvurusu boş öğesini biçimi kullanarak tanımlanmış olması gerekir (\<FIELDREF / >), başlangıç/bitiş öğeleri kullanarak değil (\<FIELDREF >\</FieldRef >):  
  
```xml  
<FieldRef ID="{5744d18c-305e-4632-8bd1-09d134f4830d}"   
    Name="PatientName"   
    DisplayName="Patient Name"   
    Required="TRUE"/>  
```  
  
 Alan XML kaynağını yanlış biçimlendirilmiş, geçerli bir XML dosyası değil veya başka bir sorunun yaşandığı hata "dosyasını ayrıştıramıyor" oluşur.  
  
## <a name="new-non-english-site-definitions-do-not-appear-in-site-creation-page-after-deployment"></a>Yeni İngilizce olmayan Site tanımları dağıtımdan sonra Site Oluşturma sayfasında görünmez  
 İngilizce olmayan sürümünü kullanarak bir site tanımı oluşturup sonra [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] (diğer bir deyişle, bir yerel bir sürümle [!INCLUDE[TLA2#tla_id](../sharepoint/includes/tla2sharptla-id-md.md)] 1033 dışında), **SharePoint özelleştirmeleri** sekmesini görünmüyor**Şablon Seçimi** kutusu ve yeni site şablonu içinde görünmüyor **yeni SharePoint sitesi** sayfası.  
  
### <a name="error-message"></a>Hata İletisi  
 Yok.  
  
### <a name="resolution"></a>Çözüm  
 Bu sorun, yanlış bir değere nedeniyle oluşur **yolu** webtemp site tanımı yapılandırma dosyasını, webtemp_SiteDefinitionProject1.xml gibi özelliği. İçinde **yolu** özelliği altında bulunan webtemp dosyası için **dağıtım konumu**, uygun yerel 1033 değiştirmek [!INCLUDE[TLA2#tla_id](../sharepoint/includes/tla2sharptla-id-md.md)]. Örneğin, kullanmak için Japonca yerel ayarını değiştirme değeri için 1041. Daha fazla bilgi için bkz: [Microsoft tarafından atanan yerel kimlikler](http://go.microsoft.com/fwlink/?LinkID=165561) MSDN Web sitesinde.  
  
## <a name="error-appears-when-a-workflow-project-is-deployed-on-a-clean-system"></a>Bir iş akışı projesinde temiz bir sistemde dağıtıldığında hata görünür  
 Bir iş akışı projesinde dağıtırsanız, bu sorun oluşur [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] temiz sistemde. Yeni bir yüklemesini olan bir bilgisayarda temiz bir sistemdir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ve SharePoint ancak dağıtılmış iş akışı proje yok.  
  
### <a name="error-message"></a>Hata İletisi  
 SharePoint listesi bulunamıyor: İş Akışı Geçmişi.  
  
### <a name="resolution"></a>Çözüm  
 Bu hata, eksik bir iş akışı geçmişi listesi nedeniyle oluşur. Geliştirme ortamı temiz bir sistem olduğundan, iş akışı yok dağıtılır ve iş akışı geçmişi listesi henüz yok. Bu sorunu çözmek için oluşturulacak iş akışı geçmişi listesi neden olan iş akışı Sihirbazı ' nı yeniden açın.  
  
##### <a name="to-reenter-the-workflow-wizard"></a>İş akışı Sihirbazı'nı yeniden girmek için  
  
1.  İçinde **Çözüm Gezgini**, iş akışı düğümü seçin.  
  
2.  İçinde **özellikleri** penceresinde, bir üç nokta düğmesini sahip herhangi bir özellikte üç nokta (...) düğmesini seçin.  
  
## <a name="user-must-refresh-application-page-in-browser-while-debugging-to-view-updated-image"></a>Görüntü güncelleştirilmiş görünüme hata ayıklama sırasında kullanıcı uygulama sayfasını tarayıcıda yenilemeniz gerekir  
 Bir görüntü gibi görüntüleyen bir denetim ile uygulama sayfası içeren bir SharePoint çözüm ayıkladığınız varsa bir [!INCLUDE[TLA2#tla_html](../sharepoint/includes/tla2sharptla-html-md.md)] görüntü denetimi görüntüye yapılan değişiklikleri görüntülemek için tarayıcıda sayfayı yenileyin gerekir.  
  
## <a name="error-the-site-location-is-not-valid"></a>Hata: Site konumu geçerli değil  
 Bu sorun ortaya çıkabilir [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)] yüklü değil. Belirtilen SharePoint Web sitesine yönetici erişimi yoksa de oluşabilir **SharePoint Özelleştirme Sihirbazı'nı**.  
  
### <a name="error-message"></a>Hata İletisi  
  
-   SharePoint site konumu geçerli değil.  
  
### <a name="resolution"></a>Çözüm  
  
-   Yükleme [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)].  
  
-   SharePoint Web sitesine yönetici erişimi olduğundan emin olun. Daha fazla bilgi için bkz: [!INCLUDE[TLA2#tla_office](../sharepoint/includes/tla2sharptla-office-md.md)] çevrimiçi makale [atama veya SharePoint sunucusu yöneticileri, hizmet uygulamalarını kaldırma](https://docs.microsoft.com/en-us/sharepoint/administration/assign-or-remove-administrators-of-service-applications).  
  
## <a name="site-deletion-web-event-does-not-occur-in-event-receiver-project"></a>Site silme Web olayı olay alıcı projesinde oluşmaz  
 Bir olay alıcı projesi oluşturun ve "bir site siliniyor"gibi belirli Web olayları seçin, olay hiçbir zaman oluşur.  
  
### <a name="error-message"></a>Hata İletisi  
 Yok.  
  
### <a name="resolution"></a>Çözüm  
 Özellik kapsamı site düzeyinde olayları işlemek için "Site" olmalı, ancak "Web" olay alıcı projeleri için varsayılan özellik kapsamı olan bu sorun oluşur. Etkilenen Web olayları şunlardır:  
  
-   Bir site yüklenmekte olan (WebDeleting) silindi  
  
-   Bir site silindi (WebDeleted)  
  
-   Bir site yüklenmekte olan (WebMoving) taşındı  
  
-   Bir site taşındı (WebMoved)  
  
 Sorunu gidermek için olay alıcı özellik kapsamı aşağıdaki gibi değiştirin.  
  
##### <a name="to-change-the-feature-scope-of-the-event-receiver"></a>Olay alıcısı özelliği kapsamını değiştirmek için  
  
1.  İçinde **Çözüm Gezgini**, olay alıcının .feature dosyasında açma **özelliği Designer** dosyayı çift ya da kendi kısayol menüsünü ve sonra seçme açma tarafından **açın**.  
  
2.  Oku seçin **kapsam**ve ardından **Site** listesinde görünür.  
  
## <a name="deployment-error-appears-after-the-name-of-an-identifier-in-a-business-data-connectivity-model-project-is-changed"></a>İş verileri bağlantı modeli projesinde tanımlayıcı adı değiştirildikten sonra dağıtım hatası görüntülenir  
 İş verileri bağlantı (BDC) modelinde bir varlığın tanımlayıcı adı değiştirin ve ardından çözümü dağıtmak deneyin, bu sorun oluşur.  
  
### <a name="error-messages"></a>Hata İletileri  
  
-   \<*model adı*> aşağıdaki dış içerik türü etkinleştirme hataları içeriyor...  
  
-   Adlı IMetadataObject '\<*model adı*>', yineleniyor alan nda 'name' değerine sahip...  
  
### <a name="resolution"></a>Çözüm  
 Bu sorunu çözmek için model el ile silin ve çözümü yeniden dağıtmak.  Aşağıdaki araçlardan birini kullanarak model silebilirsiniz:  
  
-   SharePoint 2010 Yönetim Merkezi. Daha fazla bilgi için bkz: [BDC modeli Yönetim](http://go.microsoft.com/fwlink/?LinkID=181472) Microsoft TechNet Web sitesinde.  
  
-   Windows PowerShell. Komut isteminde aşağıdaki komutu yazarak model silebilirsiniz: **Kaldır SPBusinessDataCatalogModel**. Daha fazla bilgi için bkz: [genel cmdlet'leri (SharePoint Server 2010)](http://go.microsoft.com/fwlink/?LinkID=182375) Microsoft TechNet Web sitesinde.  
  
## <a name="an-error-appears-when-you-try-to-view-a-visual-web-part-in-sharepoint"></a>Visual Web Bölümü SharePoint görüntülemeye çalıştığınızda bir hata görünür  
 Bu sorun zaman **yolu** özelliği kullanıcı denetiminin dizesi ile başlayan değil "CONTROLTEMPLATES\\".  
  
### <a name="error-messages"></a>Hata İletileri  
  
-   Dosyanın ' /_CONTROLTEMPLATES/*\<proje adı >*/*\<Web Bölümü adı >*/*\<kullanıcı denetimi adı >*.ascx' yok.  
  
-   '/' Uygulamasında sunucu hatası.  
  
### <a name="resolution"></a>Çözüm  
  
##### <a name="to-resolve-this-issue"></a>Bu sorunu gidermek için  
  
1.  İçinde **Çözüm Gezgini**, dosya adı uzantısı olan .ascx kullanıcı Denetim dosyası seçin.  
  
2.  Menü çubuğunda seçin **Görünüm**, **Özellikler penceresini**.  
  
3.  İçinde **özellikleri** penceresinde genişletin **dağıtım konumu** düğümü.  
  
4.  Değerini emin **yolu** özelliği dizesi ile başlayan "CONTROLTEMPLATES\\".  
  
## <a name="error-appears-when-an-imported-reusable-workflow-that-contains-a-task-form-field-is-run"></a>Bir görev Form alanı içeren bir içe aktarılan yeniden kullanılabilir iş akışını çalıştırdığınızda hata görünür  
 Bir alana sahip bir görev formu içeren bir iş akışı alın ve ardından yeni bir iş akışı aldığınız sisteminde çalıştırırsanız bu sorun oluşur.  
  
### <a name="error-message"></a>Hata İletisi  
 Hata oluştu 'Özellikleri etkinleştir' dağıtım adımda: kimliği alanıyla [*GUID*] özelliği tanımlı [*GUID*] geçerli site koleksiyonu veya bir alt sitede bulundu.  
  
### <a name="resolution"></a>Çözüm  
 Bu hata içeri aktarma yeniden kullanılabilir iş akışı Proje nedeniyle oluşan alan kimliği çakışmaları sonucudur. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] görev form alanı kimlikleri değiştirmez. İçeri aktarılan bir iş akışı özgün iş akışı içeren aynı sunucuda dağıtırsanız, alan kimliği çakışmaları oluşur.  
  
 Bu sorunu çözmek için tüm içeri aktarılan iş akışı dosyalarını alan kodu özniteliğinin değeri değiştirmek için Bul ve Değiştir özelliğini kullanın.  
  
## <a name="error-appears-when-a-renamed-imported-list-instance-is-run"></a>Liste örneği çalıştırmak bir adlandırılmış olduğunda alınan hata görünür  
 İçeri aktarılan liste örneği yeniden adlandırın ve ardından çalışmasında Bu sorun oluşur [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
### <a name="error-message"></a>Hata İletisi  
 Yapı hatası: hata oluştu 'Özellikleri etkinleştir' dağıtım adımda: Template\Features dosya\\[*projeyi alın**özelliği**adı*] \Files\Lists\\[*eski ** listesi adı*] \Schema.xml mevcut değil.  
  
### <a name="resolution"></a>Çözüm  
 Bir liste örneği içe aktardığınızda, CustomSchema adlı bir öznitelik listesi örneği Elements.xml dosyasına eklenir. Elements.XML liste örneği için özel bir schema.xml yolunu içerir. Ne zaman yeniden adlandırmadan Listesi örneğinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]özel schema.xml dağıtım yol değiştirir, ancak CustomSchema özniteliğinin yol değeri güncelleştirilmez. Sonuç olarak, liste örneği özelliği etkinleştirildiğinde CustomSchema özniteliği tarafından belirtilen eski yolunda schema.xml dosyası bulunamıyor.  
  
 Bu sorunu çözmek için dağıtım konumu CustomSchema özniteliğinde schema.xml dosyasının yolunu güncelleştirin.  
  
## <a name="sharepoint-debugging-session-terminated-by-iis"></a>SharePoint hata ayıklama oturumunun IIS tarafından sonlandırıldı  
 Bir kesme noktası ayarlarsanız bu sorun bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint çözüm, çalıştırmak ve 90 saniyeden daha uzun bir kesme noktasında kalması için F5 tuşuna seçin.  
  
### <a name="error-message"></a>Hata İletisi  
 Ayıklanacak Web sunucusu işlemi Internet Information Services (IIS) tarafından sonlandırıldı. IIS uygulama havuzu ping ayarlarını yapılandırarak bu sorunu önleyebilirsiniz. Bkz. daha ayrıntılı bilgi için Yardım.  
  
### <a name="resolution"></a>Çözüm  
 Varsayılan olarak, IIS uygulama havuzu bir uygulamanın uygulama kapanmadan önce yanıt 90 saniye bekler. Bu işlem, "uygulama ping olarak" adı verilir. Bu sorunu çözmek için bekleme süresini artırın veya tamamen ping işlemi uygulamayı devre dışı.  
  
##### <a name="to-access-the-iis-app-pool-settings"></a>IIS uygulama havuzu ayarlarına erişmek için  
  
1.  IIS Yöneticisi'ni açın.  
  
2.  İçinde **bağlantıları** bölmesinde, SharePoint sunucu düğümünü genişletin ve ardından **uygulama havuzları** düğümü.  
  
3.  Üzerinde **uygulama havuzları** sayfasında, SharePoint uygulama havuzu (genellikle "SharePoint - 80"), seçin ve ardından **Eylemler** bölmesinde seçin **Gelişmiş ayarları** bağlantı.  
  
4.  IIS zaman aşımından önce bekleme süresini artırmak için değerini değiştirme **Ping en büyük yanıt süresi (saniye)** 90 saniyeden daha büyük bir değer.  
  
5.  Ping IIS devre dışı bırakmak için ayarlanmış **Ping etkinleştirilmiş** için **False**.  
  
## <a name="auto-retract-leaves-orphaned-list-instance-in-sharepoint"></a>SharePoint bırakır yalnız bırakılmış listesi örneği otomatik Ayıkla  
 Aşağıdaki adımlar bu sorun oluşur.  
  
1.  Bir liste örneği olan bir liste tanımı oluşturun [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Çözümü çalıştırmak için F5 tuşuna seçin.  
  
3.  Hata ayıklamayı durdurun veya SharePoint sitesi kapatın.  
  
4.  SharePoint sitesi yeniden açın ve liste örneği açın.  
  
### <a name="error-message"></a>Hata İletisi  
 '/' Uygulamasında sunucu hatası.  
  
### <a name="resolution"></a>Çözüm  
 Bir SharePoint çözüm bir hata ayıklama oturumu kapatın sonra bunun nedeni otomatik geri çekmek özelliği çözümü geri çeker. Geri çekme listesi tanımını SharePoint'ten siler, ancak liste örneği silmez. Temel alınan listesi tanımını listesi örneği tarafından gereklidir.  
  
 Bu sorunu çözmek için menü çubuğu seçme çözümü dağıtma **yapı**, **dağıtma**. (Çözüm F5 tuşuna seçerek hata ayıklama yoktur.) Ardından, SharePoint listesi örneğini silin.  
  
## <a name="original-sharepoint-solution-is-replaced-by-an-exported-version"></a>Özgün SharePoint çözüm dışa aktarılan bir sürüm ile değiştirilir  
 Bir SharePoint çözüm veriyorsanız, çözüme alma [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]ve ardından onu dışarı aynı sitede yeniden çözümü dağıtmak, özgün SharePoint çözüm değiştirilir. Özgün çözüm üzerinde etkin olmayan bir sunucuya çözümü dağıtırsanız, bu sorun gerçekleşmez.  
  
### <a name="error-message"></a>Hata İletisi  
 Yok.  
  
### <a name="resolution"></a>Çözüm  
 Bunu dışarı sitesinde bir çözüm üzerine yazılmasını önlemek için SolutionID GUID'lerini ve içe aktarılan tüm özelliklerin özellik kimlikleri değiştirmek [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] projesi.  
  
## <a name="error-appears-when-debugging-starts"></a>Başlatır hata ayıklarken hata görünür  
 Visual Studio'da SharePoint çözüm hata ayıklamak başlattığınızda, verilen anahtar sözlükte tamamlanmadığı için Visual Studio Web.config dosyası yüklenemedi bir hata gösterir.  
  
### <a name="error-message"></a>Hata İletisi  
 Web.config yapılandırma dosyası yüklenemedi. Tüm hatalı biçimlendirilmiş XML öğeleri için dosyayı denetleyin ve yeniden deneyin. Şu hata oluştu: verilen anahtar sözlükte değildi.  
  
### <a name="resolution"></a>Çözüm  
 Bu sorunu çözmek için Visual Studio'da SharePoint projesi Site URL'si özellik değeri için web uygulamasının diğer erişim eşleşmeleri varsayılan bölgeye atanan URL eşleştiğinden emin olun. Intranet gibi başka bir bölge için URL'yi kullanarak hata çözümlenemiyor. Site proje URL'sini ve varsayılan bölge URL'de eşleşmelidir. Diğer erişim eşleşmeleri erişmek için SharePoint 2010 Yönetim Merkezi yardımcı programını açın, **Uygulama Yönetimi** bağlantısını ve ardından, **Web uygulamaları**, seçin  **Diğer erişim eşleşmeleri yapılandırma** bağlantı. Daha fazla bilgi için bkz: [oluşturma bölgeleri Web uygulamaları için](http://go.microsoft.com/fwlink/?LinkId=192274).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint paketleme ve dağıtım sorunlarını giderme](../sharepoint/troubleshooting-sharepoint-packaging-and-deployment.md)   
 [Derleme ve SharePoint çözümlerini hata ayıklama](../sharepoint/building-and-debugging-sharepoint-solutions.md)   
 [Visual Studio’da hata ayıklama](/visualstudio/debugger/debugging-in-visual-studio)  
  
  
