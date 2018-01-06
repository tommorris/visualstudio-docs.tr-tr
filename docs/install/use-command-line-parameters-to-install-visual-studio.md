---
title: "Visual Studio'yu yüklemek için komut satırı parametreleri kullanın | Microsoft Docs"
ms.custom: 
ms.date: 09/22/2017
ms.reviewer: tims
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- command-line parameters
- switches
- command prompt
ms.assetid: 480f3cb4-d873-434e-a8bf-82cff7401cf2
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: bfdce6484661354315a4f6b8b4a219f119ec8742
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="use-command-line-parameters-to-install-visual-studio-2017"></a>Visual Studio 2017 yüklemek için komut satırı parametreleri kullanın
Visual Studio 2017 bir komut isteminden yüklediğinizde, denetim veya yüklemeyi özelleştirmek için çeşitli komut satırı parametreleri kullanabilirsiniz. Komut satırından aşağıdaki eylemleri gerçekleştirebilirsiniz:

- Yükleme önceden belirli seçenekler ile başlatır.
- Yükleme işlemini otomatikleştirir.
- Daha sonra kullanmak için yükleme dosyaları önbelleği (Düzen) oluşturun.

Komut satırı seçeneklerini indirme işlemi başlatan bir küçük (yaklaşık 1 MB) dosyadır Kurulum önyükleyici ile birlikte kullanılır. Önyükleyici Visual Studio sitesinden yüklediğinizde başlatılır ilk çalıştırılabilir ' dir. Doğrudan bağlantı için en son sürüm önyükleyici yüklemekte olduğunuz ürün sürümü almak için aşağıdaki bağlantıları kullanın:

* [Visual Studio 2017 Enterprise](https://aka.ms/vs/15/release/vs_enterprise.exe)
* [Visual Studio 2017 Professional](https://aka.ms/vs/15/release/vs_professional.exe)
* [Visual Studio 2017 topluluk](https://aka.ms/vs/15/release/vs_community.exe)

## <a name="list-of-command-line-parameters"></a>Komut satırı parametreleri listesi  
 Visual Studio komut satırı parametreleri büyük/küçük harfe duyarsızdır.

> Sözdizimi:`vs_enterprise.exe [command] <options>...`

(Değiştir `vs_enterprise.exe` ürün sürümü için uygun şekilde yüklemekte. Örnekler için bkz: [komut satırı parametresi örnekler](command-line-parameter-examples.md) sayfası.)

| **Komutu** | **Açıklama** |
| ----------------------- | --------------- |
| (boş) | Ürünü yükler. |
| `modify` | Yüklü ürün değiştirir. |
| `update` | Yüklü ürün güncelleştirir. |
| `repair` | Yüklü ürün onarır. |
| `uninstall` | Yüklü ürün kaldırır. |

| **Seçeneği yükleyin** | **Açıklama** |
| ----------------------- | --------------- |
| `--installPath <dir>` | Yükleme dizini için görev örneği. Yükleme için bu komuttur **isteğe bağlı** ve örnek yükleneceği. Diğer komutlar için budur **gerekli** ve önceden yüklenmiş örneği yüklendiği. |
| `--addProductLang <language-locale>` | **İsteğe bağlı**: bir yükleme sırasında veya değiştirme işlemi, bu ürünü yüklü UI dil paketlerini belirler. Birden çok dil paketlerini eklemek için komut satırında birden çok kez yer alabilir. Yoksa, yükleme makine yerel ayar kullanır. Daha fazla bilgi için bkz: [dil yerel ayarları listesi](#list-of-language-locales) bu sayfadaki bölümü.|
| `--removeProductLang <language-locale>` | **İsteğe bağlı**: bir yükleme sırasında veya değiştirme işlemi, bu ürün kaldırılacak UI dil paketlerini belirler. Birden çok dil paketlerini eklemek için komut satırında birden çok kez yer alabilir. Daha fazla bilgi için bkz: [dil yerel ayarları listesi](#list-of-language-locales) bu sayfadaki bölümü.|
| `--add <one or more workload or component IDs>` | **İsteğe bağlı**: bir veya daha fazla iş yükü ya da bileşen kimlikleri ekleyin. Yapı gerekli bileşenlerini, önerilen veya isteğe bağlı bileşenlerini değil yüklenir. Genel olarak kullanarak ek bileşenleri denetleyebilirsiniz `--includeRecommended` ve/veya `--includeOptional`. Geçirmiş denetimi için ekleyebilirsiniz `;includeRecommended` veya `;includeOptional` kimliği (örneğin, `--add Workload1;includeRecommended` veya `--add Workload2;includeRecommended;includeOptional`). Daha fazla bilgi için bizim [iş yükü ve Bileşen kimlikleri](workload-and-component-ids.md) sayfası. Bu seçenek gerektiği gibi yineleyebilirsiniz.|
| `--remove <one or more workload or component IDs>` | **İsteğe bağlı**: bir veya daha fazla iş yükü veya kaldırmak için Bileşen kimlikleri. Daha fazla bilgi için bizim [iş yükü ve Bileşen kimlikleri](workload-and-component-ids.md) sayfası. Bu seçenek gerektiği gibi yineleyebilirsiniz.|
| `--in <path>` | **İsteğe bağlı**: URI veya bir yanıt dosyasının yolu.  |
| `--all` | **İsteğe bağlı**: tüm iş yükleri ve bir ürün için bileşenleri yüklemeyi. |
| `--allWorkloads` | **İsteğe bağlı**: tüm iş yükleri ve bileşenleri, hiçbir önerilen veya isteğe bağlı bileşenleri yükler. |
| `--includeRecommended` | **İsteğe bağlı**: yüklü olan tüm iş yükleri için önerilen bileşenleri, ancak isteğe bağlı bileşenlerini içerir. İş yükleri belirtilen biriyle `--allWorkloads` veya `--add`. |
| `--includeOptional` | **İsteğe bağlı**: isteğe bağlı bileşenler yüklü olan tüm iş yükleri için ancak önerilen bileşenlerini içerir. İş yükleri belirtilen biriyle `--allWorkloads` veya `--add`.  |
| `--quiet, -q` | **İsteğe bağlı**: yüklemesi yapılırken herhangi bir kullanıcı arabirimi gösterme. |
| `--passive, -p` | **İsteğe bağlı**: kullanıcı arabirimini görüntüler, ancak herhangi bir etkileşim kullanıcıdan isteme. |
| `--norestart` | **İsteğe bağlı**: ile varsa, komutları `--passive` veya `--quiet` otomatik olarak makine (gerekiyorsa) yeniden başlatılmaz.  Bu durumların yoksayılır `--passive` ya da `--quiet` belirtilir.  |
| `--nickname <name>` | **İsteğe bağlı**: Bu yüklü bir ürüne atamak için takma ad tanımlar. Takma ad 10 karakterden uzun olamaz.  |
| `--productKey` | **İsteğe bağlı**: Bu yüklü olan bir ürün için kullanılacak ürün anahtarını tanımlar. Oluşur 25 alfasayısal karakter biçimde `xxxxx-xxxxx-xxxxx-xxxxx-xxxxx` veya `xxxxxxxxxxxxxxxxxxxxxxxxx`. |
| `--help, --?, -h, -?` | Bu sayfayı çevrimdışı bir sürümünü görüntüler. |

> Not: birden çok iş yükleri ve bileşenleri belirtirken, yinelemelisiniz `--add` veya `--remove` her öğe için komut satırı anahtarı.

| **Düzen Seçenekleri** | **Açıklama** |
| ----------------------- | --------------- |
| `--layout <dir>` | Önbellek yükleme çevrimdışı oluşturmak için bir dizini belirtir. Daha fazla bilgi için bkz: [Visual Studio ağ tabanlı yüklemesini oluşturma](create-a-network-installation-of-visual-studio.md).|
| `--lang <one or more language-locales>` | **İsteğe bağlı**: ile kullanılan `--layout` hazırlamak için bir çevrimdışı yükleme önbellek belirtilen güncelleştirmelerin ile kaynak paketleriyle. Daha fazla bilgi için bkz: [dil yerel ayarları listesi](#list-of-language-locales) bu sayfadaki bölümü.|
| `--add <one or more workload or component IDs>` | **İsteğe bağlı**: bir veya daha fazla iş yükü ya da bileşen kimlikleri ekleyin. Yapı gerekli bileşenlerini, önerilen veya isteğe bağlı bileşenlerini değil yüklenir. Genel olarak kullanarak ek bileşenleri denetleyebilirsiniz `--includeRecommended` ve/veya `--includeOptional`. Geçirmiş denetimi için ekleyebilirsiniz `;includeRecommended` veya `;includeOptional` kimliği (örneğin, `--add Workload1;includeRecommended` veya `--add Workload2;includeOptional`). Daha fazla bilgi için bizim [iş yükü ve Bileşen kimlikleri](workload-and-component-ids.md) sayfası. <br/>**Not**: varsa `--add` olan kullanıldığında, yalnızca belirtilen iş yükleri ve bileşenleri ve bunların bağımlılıklarını karşıdan yüklenir. Varsa `--add` belirtilmezse, tüm iş yükleri ve bileşenleri düzene indirilir.|
| `--includeRecommended` | **İsteğe bağlı**: yüklü olan tüm iş yükleri için önerilen bileşenleri, ancak isteğe bağlı bileşenlerini içerir. İş yükleri belirtilen biriyle `--allWorkloads` veya `--add`. |
| `--includeOptional` | **İsteğe bağlı**: önerilen içeren *ve* düzende tüm iş yükleri için isteğe bağlı bileşenler. İş yükleri ile belirtilen `--add`.  |
| `--keepLayoutVersion` | **15.3, isteğe bağlı olarak yeni**: düzeni sürümünü güncelleştirmeden düzene değişiklikleri uygulayın. |
| `--verify` | **15.3, isteğe bağlı olarak yeni**: bir düzen içeriğini doğrulayın.  Eksik veya bozuk dosyalar listelenir. |
| `--fix` | **15.3, isteğe bağlı olarak yeni**: bir düzen içeriğini doğrulayın.  Herhangi bir dosya bozuk veya eksik olması bulunursa, yeniden yüklenen.  Bir düzen düzeltmek için Internet erişimi gerekir. |
| `--clean <one or more paths to catalogs>` | **15.3, isteğe bağlı olarak yeni**: yeni bir sürüme güncelleştirilip güncelleştirilmediğini düzeninden bileşenleri eski sürümlerini kaldırır. |

| **Gelişmiş yükleme seçenekleri** | **Açıklama** |
| ----------------------- | --------------- |
| `--channelId <id>` | **İsteğe bağlı**: yüklenecek kimliği örneği kanalı. Diğer komutlar için gözardı yükleme komut için bu gereklidir `--installPath` belirtilir. |
| `--channelUri <uri>` | **İsteğe bağlı**: kanal bildiriminin URI. Güncelleştirmeleri değil isteniyorsa, `--channelUri` mevcut olmayan bir dosyaya işaret edebilir. (örneğin,--channelUri C:\doesntExist.chman) Bu yükleme komutu için kullanılabilir; diğer komutlar için yoksayılır. |
| `--installChannelUri <uri>` | **İsteğe bağlı**: kanal bildiriminin yükleme için kullanılacak URI. URI tarafından belirtilen `--channelUri` (olması gerekir belirtilen `--installChannelUri` belirtilir) güncelleştirmeleri algılamak için kullanılır. Bu yükleme komutu için kullanılabilir; diğer komutlar için yoksayılır. |
| `--installCatalogUri <uri>` | **İsteğe bağlı**: Katalog bildiriminin yükleme için kullanılacak URI. Belirtilmişse, kanal Yöneticisi'ni yükleme kanal bildiriminde URI kullanmadan önce bu URI'den katalog bildirimi yüklemeye çalışır. Bu parametre, önceden indirilen ürün kataloğu ile düzeni önbellek oluşturulacağı çevrimdışı yükleme desteklemek için kullanılır. Bu yükleme komutu için kullanılabilir; diğer komutlar için yoksayılır. |
| `--productId <id>` | **İsteğe bağlı** yüklenecek örnek için ürün kimliği. Normal yükleme koşullarında bu önceden doldurulmaz. |
| `--wait` | **İsteğe bağlı**: İşlem çıkış kodu döndürmeden önce yükleme tamamlanana kadar bekler. Bu, burada bir gruptan dönüş kodu işlemek için tamamlamak bir yükleme için beklemesi gerekir otomatik otomatikleştirme yüklemelerine durumunda faydalı olur. |
| `--locale <language-locale>` | **İsteğe bağlı**: yükleyici için kullanıcı arabirimi görüntüleme dilini değiştirmek. Ayar kalıcı. Daha fazla bilgi için bkz: [dil yerel ayarları listesi](#list-of-language-locales) bu sayfadaki bölümü.|
| `--cache` | **15.2, isteğe bağlı olarak yeni**: varsa, paketler için sonraki onarım yüklendikten sonra tutulacak. Bu, sonraki yükler, onarır veya değişiklikler için kullanılacak genel ilkesini geçersiz kılar. Varsayılan İlke önbellek paketler içindir. Bu kaldırma komutu için göz ardı edilir. Nasıl okumak için [devre dışı bırakmak veya paket önbellek taşıma](disable-or-move-the-package-cache.md) daha fazla bilgi için. |
| `--nocache` | **15.2, isteğe bağlı olarak yeni**: varsa, paketleri kaldıktan sonra yüklü ya da onarılması silinir. Bunlar, yalnızca gerekli ve yeniden kullandıktan sonra silinen yeniden yüklenir. Bu, sonraki yükler, onarır veya değişiklikler için kullanılacak genel ilkesini geçersiz kılar. Varsayılan İlke önbellek paketler içindir. Bu kaldırma komutu için göz ardı edilir. Nasıl okumak için [devre dışı bırakmak veya paket önbellek taşıma](disable-or-move-the-package-cache.md) daha fazla bilgi için. |
| `--noUpdateInstaller` | **15.2, isteğe bağlı olarak yeni**: varsa, yükleyici sessiz belirtildiğinde kendini güncelleştirmesini engeller. Yükleyici komut başarısız ve yükleyici güncelleştirme gerekli olduğunda noUpdateInstaller ile sessiz belirtilmişse sıfır olmayan çıkış kodu döndürür. |
| `--noWeb` | **15.3, isteğe bağlı olarak yeni**: Kurulum şimdi Internet'ten yükleme herhangi bir içerik indirir.  Yüklenmekte olan tüm içeriği çevrimdışı bir düzende kullanılabilir olması gerekir.  Düzen içeriği eksik kurulum başarısız olur.  Daha fazla bilgi için bkz: [bir ağ yüklemesinden dağıtma](create-a-network-installation-of-visual-studio.md). |

## <a name="list-of-workload-ids-and-component-ids"></a>İş yükü kimlikleri ve bileşen listesi
İş yükü ve Visual Studio ürün tarafından sıralanan Bileşen kimlikleri listesi için bkz: [Visual Studio 2017 iş yükü ve Bileşen kimlikleri](workload-and-component-ids.md) sayfası.

## <a name="list-of-language-locales"></a>Dil yerel ayarları listesi
| **Dil yerel ayar** | **Dil** |
| ----------------------- | --------------- |
| cs-CZ | Çekçe |
| de-DE | Almanca |
| en-US | İngilizce |
| es-ES | İspanyolca |
| fr-FR | Fransızca |
| it-IT | İtalyanca |
| ja-JP | Japonca |
| ko-KR | Kore Dili |
| PL-PL | Lehçe |
| pt-BR | Portekizce - Brezilya |
| RU-RU | Rusça |
| tr-TR | Türkçe |
| zh-CN | Çince - Basitleştirilmiş |
| zh-TW | Geleneksel Çince- |

## <a name="error-codes"></a>Hata kodları
İşlemin sonucunu bağlı olarak `%ERRORLEVEL%` ortam değişkeni aşağıdaki değerlerden birine ayarlanır:

| **Değer** | **Sonuç** |
| --------- | ---------- |
| 0 | İşlem başarıyla tamamlandı |
| 1602 | İşlem iptal edildi |
| 3010 | İşlem başarıyla tamamlandı ancak kullanmadan önce yükleme yeniden başlatma gerekiyor |
| 5004 | İşlem iptal edildi |
| 5007 | İşlem engellendi - bilgisayar gereksinimleri karşılamıyor |
| Diğer | Hata koşulu oluştu - daha fazla bilgi için günlükleri denetleyin |

Her bir işlemin birkaç günlük dosyalarında oluşturur `%TEMP%` yüklemenin ilerleme durumunu gösteren dizin. Klasör tarihe göre sıralayın ve ile başlayan dosyalarını aramaya `dd_bootstrapper`, `dd_client`, ve `dd_setup` önyükleyici için yükleyici uygulama ve Kurulum altyapısı, sırasıyla.

## <a name="get-support"></a>Destek alma
Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sayfası. Sorun giderme adımlarını hiçbiri yardımcı, bize yükleme Yardımı (yalnızca İngilizce) için canlı sohbet tarafından başvurabilirsiniz. Ayrıntılar için bkz [Visual Studio destek sayfası](https://www.visualstudio.com/vs/support/#talktous).

Birkaç diğer destek seçenekleri şunlardır:
* Ürün sorunları bize bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem Visual Studio Yükleyicisi ve Visual Studio IDE görünür aracı.
* Üzerinde bir ürün önerisi bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunları izleyebilir [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/), soru sorun ve yanıtlarını bulun.
* ABD ve diğer Visual Studio geliştiriciler aracılığıyla devreye bizim [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio).  (Bu seçenek gerektiren bir [GitHub](https://github.com/) hesabı.)

## <a name="see-also"></a>Ayrıca bkz.

 * [Visual Studio 2017 yükleyin](install-visual-studio.md)
 * [Visual Studio 2017 çevrimdışı yüklemesini oluşturma](create-an-offline-installation-of-visual-studio.md)
 * [Visual Studio 2017 yükleme için komut satırı parametresi örnekleri](command-line-parameter-examples.md)
 * [Yanıt dosyası ile Visual Studio yüklemesini otomatikleştirme](automated-installation-with-response-file.md)
