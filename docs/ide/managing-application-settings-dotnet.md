---
title: "Uygulama ayarları (.NET) yönetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: msvse_settingsdesigner.err.nameblank
helpviewer_keywords: application settings [Visual Studio]
ms.assetid: 35254321-ad14-47d9-b8c6-39ab3203c5d9
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 924d62f31ae073f3b832507182aa511abc484011
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="managing-application-settings-net"></a>Uygulama Ayarlarını Yönetme
Uygulama ayarları, uygulama bilgilerini dinamik olarak depolamak etkinleştirin. Ayarlar, uygulama kodu (örneğin bir bağlantı dizesi), kullanıcı tercihleri ve çalışma zamanında gereken diğer bilgileri dahil edilmemesi gereken istemci bilgisayarda bilgileri depolamanıza olanak sağlar.  
  
 Uygulama ayarları, Visual Studio'nun önceki sürümlerinde kullanılan dinamik özelliklerini değiştirin.  
  
 Her uygulama ayarı benzersiz bir ad olmalıdır. Ad harf, sayı veya bir rakamla başlayamaz olmayan bir alt çizgi herhangi bir bileşimi olabilir ve boşluk içermemelidir. Ad aracılığıyla değiştirilebilir `Name` özelliği.  
  
 Uygulama ayarları, XML olarak serileştirilmiş veya olan herhangi bir veri türü depolanabilir bir `TypeConverter` uygulayan `ToString` / `FromString`. En yaygın türleri `String`, `Integer`, ve `Boolean`, ancak değerler olarak da depolayabilirsiniz <xref:System.Drawing.Color>, <xref:System.Object>, veya bir bağlantı dizesi olarak.  
  
 Uygulama ayarları de bir değer içeriyor. Değeri **değeri** özelliği ve ayarının veri türüyle eşleşmelidir.  
  
 Ayrıca, uygulama ayarları, tasarım zamanında bir form veya denetim özelliğine bağlanabilir.  
  
 Uygulama ayarları kapsamına göre iki tür vardır:  
  
-   Uygulama kapsamlı ayarları, bir Web hizmeti veya bir veritabanı bağlantı dizesi için bir URL gibi bilgileri için kullanılabilir. Bu değerleri uygulama ile ilişkilendirilmiş. Bu nedenle, kullanıcılar bunları çalışma zamanında değiştiremezsiniz.  
  
-   Kullanıcı kapsamlı ayarları, bir form veya bir yazı tipi tercihi son konumunu kalıcı yapma gibi bilgileri için kullanılabilir. Kullanıcılar çalışma zamanında bu değerleri değiştirebilirsiniz.  
  
 Kullanarak bir ayar türünü değiştirebilirsiniz **kapsam** özelliği.  
  
 Proje sistemi uygulama ayarları iki XML dosyasında depolar: ilk uygulama ayarı; oluşturduğunuzda tasarım zamanında oluşturulan bir app.config dosyası ve uygulama çalıştıran kullanıcının herhangi bir kullanıcı ayarı değeri değiştiğinde çalışma zamanında oluşturulan bir user.config dosyası. Kullanıcı ayarları değişikliklerini uygulama özellikle Bunu yapmak için bir yöntem çağırır sürece diske yazılan değil dikkat edin.  
  
## <a name="creating-application-settings-at-design-time"></a>Tasarım zamanında uygulama ayarları oluşturma  
 Tasarım zamanında uygulama ayarları iki yolla oluşturabilirsiniz: kullanarak **ayarları** sayfasında **Proje Tasarımcısı**, veya kullanarak **özellikleri** penceresi bir form veya denetimi, bir özellik için bir ayar bağlamanıza olanak sağlar.  
  
 Bir uygulama kapsamlı ayarı (örneğin, bir veritabanı bağlantı dizesi veya sunucu kaynaklarını başvuru), oluşturduğunuzda [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ile app.config kaydeder `<applicationSettings>` etiketi. (Bağlantı dizeleri altında kaydedilir `<connectionStrings>` etiketi.)  
  
 Kullanıcı kapsamlı (örneğin, varsayılan yazı tipi, giriş sayfası veya pencere boyutu), bir ayar oluşturduğunuzda [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ile app.config kaydeder `<userSettings>` etiketi.  
  
> [!IMPORTANT]
>  Bağlantı dizeleri app.config dosyasında depoladığınızda, parolalar veya bağlantı dizesinde sunucu yolları gibi hassas bilgileri ortaya önlemek için önlemler almanız gerekir.  
>   
>  Bağlantı dizesi bilgileri bir dış kaynaktan izlerseniz, bir kullanıcı kimliği ve parolası, dikkatli olmanız gerekir sağladığını bir kullanıcı gibi bağlantınızı oluşturmak için kullandığınız değerleri emin olmak için dize içeremez ek bağlantı dizesi parametreleri bağlantınızı davranışını değiştirebilirsiniz.  
>   
>  Yapılandırma dosyasındaki hassas bilgileri şifrelemek için korumalı yapılandırma özelliğini kullanmayı düşünün. Bkz: [koruma bağlantı bilgilerini](/dotnet/framework/data/adonet/protecting-connection-information) daha fazla bilgi için.  
  
> [!NOTE]
>  Sınıf kitaplıkları için hiçbir yapılandırma dosyası modeli olduğundan uygulama ayarlarının Sınıf Kitaplığı projelerinde geçerli değildir. Bir yapılandırma dosyasına sahip Office DLL projesi için Visual Studio araçlarını istisnadır.  
  
## <a name="using-customized-settings-files"></a>Özelleştirilmiş ayarları dosyalarını kullanma  
 Projeniz için uygun ayar gruplarını yönetimi için özelleştirilmiş ayarları dosyaları ekleyebilirsiniz. Tek bir dosyada bulunan ayarları yüklenen ve bir birim olarak kaydedilir. Bu nedenle, ayarları için ayrı dosyaları depolamak için sık kullanılan ve sık kullanılan grupları, yükleme ve ayarları kaydediliyor zamandan tasarruf edebilirsiniz.  
  
 Örneğin, projenize SpecialSettings.settings gibi bir dosya ekleyebilirsiniz. Ancak, `SpecialSettings` sınıfı açık değil `My` ad alanı, **görünümü kodu** içeren özel ayarları dosyayı okuyabilir `Partial Class SpecialSettings`.  
  
 Ayarları Tasarımcısı ilk proje sistemi oluşturan Settings.settings dosyayı arar; Bu, Proje Tasarımcısı görüntüler varsayılan dosyasıdır **ayarları** sekmesi. Settings.Settings My proje klasöründe bulunan [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projeleri ve Özellikler klasöründe [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] projeleri. Proje Tasarımcısı sonra projenin kök klasöründe diğer ayarları dosyaları arar. Bu nedenle, özel ayarları dosyanız var. moduna geçirmelisiniz. Bir .settings dosyayı projenize başka bir yerde eklerseniz, Proje Tasarımcısı bulması mümkün olmaz.  
  
## <a name="accessing-or-changing-application-settings-at-run-time-in-visual-basic"></a>Erişimi veya Visual Basic çalışma zamanında uygulama ayarlarını değiştirme  
 İçinde [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projeleri, kullanarak çalışma zamanında uygulama ayarları erişebilirsiniz `My.Settings` nesnesi. Üzerinde **ayarları** sayfasında, **görüntülemek kod** Settings.vb dosyasını görüntülemek için düğmeye. Settings.vb tanımlar `Settings` ayarları sınıfındaki bu olayları işlemek sağlar sınıfı: <xref:System.Configuration.ApplicationSettingsBase.SettingChanging>, <xref:System.Configuration.ApplicationSettingsBase.PropertyChanged>, <xref:System.Configuration.ApplicationSettingsBase.SettingsLoaded>, ve <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>. Dikkat `Settings` Settings.vb sınıfında değil yalnızca kullanıcı sahip olunan kodu değil tüm oluşturulan sınıf görüntüleyen bir parçalı sınıf. Uygulama ayarları kullanarak erişim hakkında daha fazla bilgi için `My.Settings` nesne için bkz: [uygulama ayarlarına erişme](/dotnet/visual-basic/developing-apps/programming/app-settings/accessing-application-settings).  
  
 (Örneğin, bir form konumunu) çalışma zamanında kullanıcı değişiklikleri kullanıcı kapsamlı ayarlarının değerleri user.config dosyasında depolanır. Varsayılan değerleri app.config dosyasında hala kaydedilir dikkat edin.  
  
 Tüm kullanıcı kapsamlı ayarları uygulama sınamada örneğin çalışma zamanı sırasında değiştirdiyseniz ve bu ayarları varsayılan değerlerine sıfırlamak istediğiniz tıklatın **Eşitle** düğmesi.  
  
 Kullanmanız önerilir `My.Settings` nesne ve erişim ayarlarını varsayılan .settings dosyasına. Bu özellikler ayarlarına atamak için ayarları tasarımcısını kullanabilirsiniz ve ayrıca, kullanıcı ayarlarını uygulama kapatma önce otomatik olarak kaydedilir, çünkü. Ancak, [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] uygulama erişim ayarlarını doğrudan. Bu durumda, zorunda erişim `MySettings` sınıfı ve proje kökündeki özel .settings dosyasında kullanın. Bir C# uygulaması için yaptığınız gibi Ayrıca kullanıcı ayarlarını uygulama sonlandırmadan önce kaydetmeniz gerekir; Bu aşağıdaki bölümde açıklanmıştır.  
  
## <a name="accessing-or-changing-application-settings-at-run-time-in-visual-c"></a>Erişimi veya Visual C# çalışma zamanında uygulama ayarlarını değiştirme #
 Dışındaki dillerde [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], gibi [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)], erişmesi gereken `Settings` aşağıda gösterildiği gibi doğrudan sınıf [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] örnek.  
  
```csharp  
Properties.Settings.Default.FirstUserSetting = "abc";  
```  
  
 Aynı zamanda açıkça çağırmalısınız `Save` kullanıcı ayarlarını sürdürmek için bu sarmalayıcı sınıfı yöntemi. Genellikle bunu `Closing` ana formun olay işleyicisi. Aşağıdaki [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] örnek gösterir yapılan bir çağrı `Save` yöntemi.  
  
```csharp  
Properties.Settings.Default.Save();  
```  
  
 Uygulama Ayarları'nda erişme hakkında genel bilgi için `Settings` sınıfı için bkz: [uygulama ayarlarına genel bakış](/dotnet/framework/winforms/advanced/application-settings-overview). Bu ayarları yineleme yapma hakkında daha fazla bilgi için bkz [forum gönderisi](http://social.msdn.microsoft.com/Forums/vstudio/40fbb470-f1e8-4a02-a4a0-9f62b54d0fc4/is-this-possible-propertiessettingsdefault?forum=csharpgeneral).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uygulama ayarlarına erişme](/dotnet/visual-basic/developing-apps/programming/app-settings/accessing-application-settings)
