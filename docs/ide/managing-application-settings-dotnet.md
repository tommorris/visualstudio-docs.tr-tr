---
title: Uygulama ayarları (.NET) yönetme
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- msvse_settingsdesigner.err.nameblank
helpviewer_keywords:
- application settings [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 04d2c31db4c117f3bc902218a61656e5eca49e27
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="manage-application-settings-net"></a>Uygulama ayarları (.NET) yönetme

Uygulama ayarları, uygulama bilgilerini dinamik olarak depolamak etkinleştirin. Ayarlar, uygulama kodu (örneğin bir bağlantı dizesi), kullanıcı tercihleri ve çalışma zamanında gereken diğer bilgileri dahil edilmemesi gereken istemci bilgisayarda bilgileri depolamanıza olanak sağlar.

Uygulama ayarları, Visual Studio'nun önceki sürümlerinde kullanılan dinamik özelliklerini değiştirin.

Her uygulama ayarı benzersiz bir ad olmalıdır. Ad harf, sayı veya bir rakamla başlayamaz olmayan bir alt çizgi herhangi bir bileşimi olabilir ve boşluk içermemelidir. Adı aracılığıyla değiştirilir `Name` özelliği.

Uygulama ayarları, XML olarak serileştirilmiş veya olan herhangi bir veri türü depolanabilir bir `TypeConverter` uygulayan `ToString` / `FromString`. En yaygın türleri `String`, `Integer`, ve `Boolean`, ancak değerler olarak da depolayabilirsiniz <xref:System.Drawing.Color>, <xref:System.Object>, veya bir bağlantı dizesi olarak.

Uygulama ayarları da bir değer basılı tutun. Değeri **değeri** özelliği ve ayarının veri türüyle eşleşmelidir.

Ayrıca, uygulama ayarları, tasarım zamanında bir form veya denetim özelliğine bağlanabilir.

Uygulama ayarları kapsamına göre iki tür vardır:

- Uygulama kapsamlı ayarları, bir Web hizmeti veya bir veritabanı bağlantı dizesi için bir URL gibi bilgileri için kullanılabilir. Bu değerleri uygulama ile ilişkilendirilmiş. Bu nedenle, kullanıcılar bunları çalışma zamanında değiştiremezsiniz.

- Kullanıcı kapsamlı ayarları, bir form veya bir yazı tipi tercihi son konumunu kalıcı yapma gibi bilgileri için kullanılabilir. Kullanıcılar çalışma zamanında bu değerleri değiştirebilirsiniz.

Kullanarak bir ayar türünü değiştirebilirsiniz **kapsam** özelliği.

Proje sistemi uygulama ayarları iki XML dosyasında depolar:

- bir *app.config* ilk uygulama ayarı oluşturduğunuzda tasarım zamanında oluşturulan dosya

- bir *user.config* uygulamayı çalıştıran kullanıcının herhangi bir kullanıcı ayarı değeri değiştiğinde çalışma zamanında oluşturulan dosya.

Kullanıcı ayarları değişikliklerini uygulama özellikle Bunu yapmak için bir yöntem çağırır sürece diske yazılan değil dikkat edin.

## <a name="create-application-settings-at-design-time"></a>Tasarım zamanında uygulama ayarları oluştur

Tasarım zamanında uygulama ayarları iki yolla oluşturabilirsiniz: kullanarak **ayarları** sayfasında **Proje Tasarımcısı**, veya kullanarak **özellikleri** penceresi bir form veya denetimi, bir özellik için bir ayar bağlamanıza olanak sağlar.

Bir uygulama kapsamlı ayarı (örneğin, bir veritabanı bağlantı dizesi veya sunucu kaynaklarını başvuru), oluşturduğunuzda [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] içinde kaydeder *app.config* ile `<applicationSettings>` etiketi. (Bağlantı dizeleri altında kaydedilir `<connectionStrings>` etiketi.)

Kullanıcı kapsamlı (örneğin, varsayılan yazı tipi, giriş sayfası veya pencere boyutu), bir ayar oluşturduğunuzda [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] içinde kaydeder *app.config* ile `<userSettings>` etiketi.

> [!IMPORTANT]
> Bağlantı dizeleri depoladığınız zaman *app.config*, parolalar veya bağlantı dizesinde sunucu yolları gibi hassas bilgileri ortaya önlemek için önlem almalısınız.
>
> Bağlantı dizesi bilgileri bir dış kaynaktan izlerseniz, bir kullanıcı kimliği ve parolası, dikkatli olmanız gerekir sağladığını bir kullanıcı gibi bağlantınızı oluşturmak için kullandığınız değerleri emin olmak için dize içeremez ek bağlantı dizesi parametreleri bağlantınızı davranışını değiştirebilirsiniz.
>
> Yapılandırma dosyasındaki hassas bilgileri şifrelemek için korumalı yapılandırma özelliğini kullanmayı düşünün. Daha fazla bilgi için bkz: [bağlantı bilgilerini korumak](/dotnet/framework/data/adonet/protecting-connection-information).

> [!NOTE]
> Sınıf kitaplıkları için hiçbir yapılandırma dosyası modeli olduğundan uygulama ayarlarının Sınıf Kitaplığı projelerinde geçerli değildir. Bir yapılandırma dosyasına sahip Office DLL projesi için Visual Studio araçlarını istisnadır.

## <a name="use-customized-settings-files"></a>Özelleştirilmiş ayarları dosyasını kullanma

Projeniz için uygun ayar gruplarını yönetimi için özelleştirilmiş ayarları dosyaları ekleyebilirsiniz. Tek bir dosyada bulunan ayarları yüklenen ve bir birim olarak kaydedilir. Ayarları ayrı dosyalarında sık saklama kullanılan ve kullanılmayan gruplarını zaman yükleme ve ayarları kaydediliyor kaydedebilirsiniz.

Örneğin, bir dosya gibi ekleyebileceğiniz *SpecialSettings.settings* projenize. Ancak, `SpecialSettings` sınıfı açık değil `My` ad alanı, **görünümü kodu** içeren özel ayarları dosyayı okuyabilir `Partial Class SpecialSettings`.

**Ayarları Tasarımcısı** ilk arar *Settings.settings* dosya proje sistemi oluşturur; bu dosya varsayılan dosya **Proje Tasarımcısı** görüntüler **ayarları** sekmesi. *Settings.Settings* bulunan *My proje* için klasör [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projeleri ve *özellikleri* için klasör [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] projeleri. **Proje Tasarımcısı** projenin kök klasöründe diğer ayarları dosyaları arar. Bu nedenle, özel ayarları dosyanız var. moduna geçirmelisiniz. Eklerseniz bir *.settings* projenize, başka bir yerde dosyasında **Proje Tasarımcısı** bulmak mümkün olmaz.

## <a name="access-or-change-application-settings-at-run-time-in-visual-basic"></a>Visual Basic çalışma zamanında erişim ya da değişiklik uygulama ayarları

Visual Basic projelerinde, uygulama ayarları çalışma zamanında kullanarak erişebilirsiniz `My.Settings` nesnesi. Üzerinde **ayarları** sayfasında, **görüntülemek kod** görüntülemek için düğmesini *Settings.vb* dosya. *Settings.vb* tanımlar `Settings` ayarları sınıfındaki bu olayları işlemek sağlar sınıfı: <xref:System.Configuration.ApplicationSettingsBase.SettingChanging>, <xref:System.Configuration.ApplicationSettingsBase.PropertyChanged>, <xref:System.Configuration.ApplicationSettingsBase.SettingsLoaded>, ve <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>. Dikkat `Settings` sınıfını *Settings.vb* yalnızca kullanıcı sahip olunan kodu değil tüm oluşturulan sınıf görüntüler kısmi bir sınıftır. Uygulama ayarları kullanarak erişim hakkında daha fazla bilgi için `My.Settings` nesne için bkz: [erişim uygulama ayarları (.NET Framework)](/dotnet/visual-basic/developing-apps/programming/app-settings/accessing-application-settings).

Kullanıcı değişiklikleri (örneğin, bir form konumunu) çalışma zamanında depolanan kullanıcı kapsamlı ayarlarının değerleri bir *user.config* dosya. Varsayılan değerleri hala kaydedilir bildirimi *app.config*.

Kullanıcı kapsamlı ayarları uygulama sınamada örneğin çalışma zamanı sırasında değiştirilir ve bu ayarları varsayılan değerlerine Sıfırla, tıklatın istiyorsanız **Eşitle** düğmesi.

Kullanmanız önerilir `My.Settings` nesne ve varsayılan *.settings* erişim ayarları dosyasına. Kullanabileceğiniz olmasıdır **ayarları Tasarımcısı** ayarları ve kullanıcı, ayrıca, özellikler atamak için ayarları uygulama kapatma önce otomatik olarak kaydedilir. Ancak, Visual Basic uygulamanızın ayarlarını doğrudan erişebilirsiniz. Bu durumda, zorunda erişim `MySettings` sınıfı ve özel bir kullanmak *.settings* proje kökündeki dosyasında. Bir C# uygulaması için yaptığınız gibi uygulama sonlandırmadan önce kullanıcı ayarlarını kaydetmeniz gerekir; Bu aşağıdaki bölümde açıklanmıştır.

## <a name="access-or-change-application-settings-at-run-time-in-c"></a>Çalışma zamanında C# erişim ya da değişiklik uygulama ayarları #

Visual Basic, C# gibi dışındaki dillerde, erişmelisiniz `Settings` aşağıda gösterildiği gibi doğrudan sınıf [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] örnek.

```csharp
Properties.Settings.Default.FirstUserSetting = "abc";
```

Açıkça çağırmalısınız `Save` kullanıcı ayarlarını sürdürmek için bu sarmalayıcı sınıfı yöntemi. Genellikle bunu `Closing` ana formun olay işleyicisi. Aşağıdaki C# örnek bir çağrı gösterilmektedir `Save` yöntemi.

```csharp
Properties.Settings.Default.Save();
```

Uygulama Ayarları'nda erişme hakkında genel bilgi için `Settings` sınıfı için bkz: [uygulama ayarlarına genel bakış (.NET Framework)](/dotnet/framework/winforms/advanced/application-settings-overview). Bu ayarları yineleme yapma hakkında daha fazla bilgi için bkz [forum gönderisi](http://social.msdn.microsoft.com/Forums/vstudio/40fbb470-f1e8-4a02-a4a0-9f62b54d0fc4/is-this-possible-propertiessettingsdefault?forum=csharpgeneral).

## <a name="see-also"></a>Ayrıca bkz.

- [Erişim uygulama ayarları (.NET Framework)](/dotnet/visual-basic/developing-apps/programming/app-settings/accessing-application-settings)
