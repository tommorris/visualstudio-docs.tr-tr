---
title: Ayarları sayfası, Proje Tasarımcısı
ms.date: 06/14/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- ApplicationSettingsOverview
helpviewer_keywords:
- Settings page in Project Designer
- Project Designer, Settings page
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5c0f7b47b56522f5c4aeef0054e6b7b52434ff87
ms.sourcegitcommit: 562867be91ee1aebbed4658c8de0949f422860fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/14/2018
ms.locfileid: "35609966"
---
# <a name="settings-page-project-designer"></a>Ayarları sayfası, Proje Tasarımcısı

Kullanım **ayarları** bir projenin uygulama ayarlarını belirlemek için Proje Tasarımcısı'nın sayfası. Uygulama ayarlarını depolamak ve özellik ayarları ve diğer bilgiler, uygulamanız için dinamik olarak almak etkinleştirin. Bunlar ayrıca özel uygulama ve bir istemci bilgisayarda kullanıcı tercihlerini korumak etkinleştirin. Daha fazla bilgi için bkz: [uygulama ayarlarını yönetme](../managing-application-settings-dotnet.md).

Erişim için **ayarları** sayfası, proje düğümü seçin **Çözüm Gezgini**ve ardından **proje** > **özellikleri**. Proje Tasarımcısı göründüğünde seçin **ayarları** sekmesi.

## <a name="header-bar"></a>Başlık çubuğu

Başlık çubuğu üstündeki **ayarları** sayfası birkaç denetimleri içerir:

**Eşitleme**

**Eşitleme** tasarım zamanında tanımlanan varsayılan değerlerine hata ayıklama sırasında veya çalışma zamanında uygulamanın kullandığı kullanıcı kapsamlı ayarlarını geri yükler. Uygulamaya özgü dosyaları verileri geri yüklemek için çalışma zamanı kaldırmak diskten, proje verilerden oluşturulur.

**Yük Web ayarları**

**Web ayarları yük** görüntüler bir **oturum açma** , anonim kullanıcılar için veya kimliği doğrulanmış bir kullanıcı için ayarları yüklemenizi sağlayan iletişim kutusu. Bu düğme yalnızca, istemci uygulama hizmetleri üzerinde etkinleştirdiğinizde etkindir **Hizmetleri** sayfasında ve belirtilen bir **hizmet konumu Web ayarları**.

**Görünümü Kodu**

C# projeleri için **görünümü kodu** düğmesini etkinleştirir kodda görüntülemenizi *Settings.cs* dosya. Bu dosyayı tanımlayan `Settings` üzerinde belirli olayları işlemek sağlayan sınıf `Settings` nesnesi. Visual Basic dışındaki dillerde açıkça çağırmalısınız `Save` kullanıcı ayarlarını sürdürmek için bu sarmalayıcı sınıfı yöntemi. Genellikle bunu **kapatma** ana formun olay işleyicisi. Aşağıdaki çağrı örneğidir `Save` yöntemi:

```csharp
Properties.Settings.Default.Save();
```

Visual Basic projeleri **görünümü kodu** düğmesini etkinleştirir kodda görüntülemenizi *Settings.vb* dosya. Bu dosyayı tanımlayan `MySettings` üzerinde belirli olayları işlemek sağlayan sınıf `My.Settings` nesnesi. Uygulama ayarları kullanarak erişim hakkında daha fazla bilgi için `My.Settings` nesne için bkz: [erişim uygulama ayarları](/dotnet/visual-basic/developing-apps/programming/app-settings/accessing-application-settings).

Uygulama ayarlarına erişme hakkında daha fazla bilgi için bkz: [Windows Forms için uygulama ayarları](/dotnet/framework/winforms/advanced/application-settings-for-windows-forms).

**Erişim değiştiricisi**

**Erişim değiştiricisi** düğmesi erişim düzeyini belirtir `Properties.Settings` (C# ' ta) veya `My.Settings` Yardımcısı (Visual Basic'te) sınıfları Visual Studio'nun oluşturduğu *Settings.Designer.cs* veya *Settings.Designer.vb*.

Visual C# projeleri için erişim değiştiricisi olabilir **dahili** veya **ortak**.

Visual Basic projeleri için erişim değiştiricisi olabilir **arkadaş** veya **ortak**.

Varsayılan olarak, ayardır **dahili** C# ve **arkadaş** Visual Basic'te. Visual Studio yardımcı sınıfları olarak oluşturduğunda **dahili** veya **arkadaş**, yürütülebilir (*.exe*) uygulamaları kaynakları ve eklemiş olduğunuz ayarları erişemiyor sınıf kitaplıkları (*.dll* dosyaları). Kaynakları ve ayarları bir sınıf kitaplığı paylaşmak varsa, erişim değiştiricisi kümesine **ortak**.

Ayarları yardımcı sınıfları hakkında daha fazla bilgi için bkz: [uygulama ayarlarını yönetme](../managing-application-settings-dotnet.md).

## <a name="settings-grid"></a>Kılavuz ayarları

**Ayarları kılavuz** uygulama ayarlarını yapılandırmak için kullanılır. Bu kılavuz şu sütunları içerir:

**Ad**

Uygulama ayarı adı bu alana girin.

**Türü**

Ayarı için bir tür seçmek için açılır listeyi kullanın. Örneğin, aşağı açılan listesinde en sık kullanılan türleri görünür **dize**, **(bağlantı dizesi)**, ve **System.Drawing.Font**. Başka bir türünü seçerek seçebilirsiniz **Gözat** listesi ve bir türden seçme işleminin sonunda **bir türü seçin** iletişim kutusu. Bir türü seçtikten sonra genel türleri (geçerli çözüm için yalnızca) aşağı açılan listesinde eklenir.

**Kapsam**

Şunlardan birini seçin **uygulama** veya **kullanıcı**.

Bağlantı dizeleri gibi uygulama kapsamlı ayarları uygulamayla ilişkilendirilir. Kullanıcılar çalışma zamanında uygulama kapsamlı ayarlarını değiştiremez.

Kullanıcı kapsamlı ayarları, yazı tipleri gibi ilgili kullanıcı tercihlerini kullanılmak üzere tasarlanmıştır. Kullanıcılar çalışma zamanında değiştirebilirsiniz.

**Değer**

Veri veya uygulama ayarı ile ilişkili değer. Örneğin, ayarı bir yazı tipi ise, değerini olabilir **Verdana, 9.75pt, stil kalın =**.

## <a name="see-also"></a>Ayrıca bkz.

- [Uygulama ayarlarını yönetme](../managing-application-settings-dotnet.md)
- [Erişim uygulama ayarları (Visual Basic)](/dotnet/visual-basic/developing-apps/programming/app-settings/accessing-application-settings)