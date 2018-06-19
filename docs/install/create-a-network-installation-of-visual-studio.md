---
title: Visual Studio ağ tabanlı yüklemesini oluşturma
description: Visual Studio içinde bir kuruluş dağıtmak için bir ağ yükleme noktası oluşturmayı öğrenin.
ms.date: 10/17/2017
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 4CABFD20-962E-482C-8A76-E4012052F701
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6fdecc141affcb88d0a04346767469ef5296557d
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
ms.locfileid: "31622893"
---
# <a name="create-a-network-installation-of-visual-studio-2017"></a>Visual Studio 2017 bir ağ yüklemesi oluşturma

Genellikle, bir kuruluş yöneticisi istemci iş istasyonlarına dağıtım için bir ağ yükleme noktası oluşturur. Biz, tek bir klasör için tüm ürün güncelleştirmeleri ile birlikte ilk yükleme dosyaları önbelleğe sağlamak için Visual Studio 2017 tasarladık. (Bu işlem, aynı zamanda olarak adlandırılır _bir düzen oluşturma_.) İstemci iş istasyonlarına aynı ağ konumu için en son hizmet verme güncelleştirme güncelleştirilmemiş olmasanız bile, kendi yüklemesini yönetmek için kullanabilmesi için Biz bu yaptık.

 > [!NOTE]
 > (Örneğin, Visual Studio Professional ve Visual Studio Enterprise), kuruluşunuzda kullanımda Visual Studio'nun birden çok sürüm varsa, her sürüm için ayrı bir ağ yükleme paylaşımı oluşturmanız gerekir.

## <a name="download-the-visual-studio-bootstrapper"></a>Visual Studio önyükleyici indirin

**Karşıdan** istediğiniz Visual Studio sürümü. Tıklattığınızdan emin olun **kaydetmek**ve ardından **Klasör Aç**.

Kurulumunuzu yürütülebilir&mdash;veya daha fazla belirli bir önyükleyici dosya&mdash;aşağıdakilerden birini eşleşmesi gerekir.

|Sürüm | İndir|
|-------------|-----------------------|
|Visual Studio Enterprise | [**vs_enterprise.exe**](https://aka.ms/vs/15/release/vs_enterprise.exe) |
|Visual Studio Professional | [**vs_professional.exe**](https://aka.ms/vs/15/release/vs_professional.exe) |
|Visual Studio Community | [**vs_community.exe**](https://aka.ms/vs/15/release/vs_community.exe) |

Desteklenen diğer önyükleyiciler dahil [vs_buildtools.exe](https://aka.ms/vs/15/release/vs_buildtools.exe), [vs_feedbackclient.exe](https://aka.ms/vs/15/release/vs_feedbackclient.exe), [vs_teamexplorer.exe](https://aka.ms/vs/15/release/vs_teamexplorer.exe), [vs_testagent.exe](https://aka.ms/vs/15/release/vs_testagent.exe), [vs_testcontroller.exe](https://aka.ms/vs/15/release/vs_testcontroller.exe), ve [vs_testprofessional.exe](https://aka.ms/vs/15/release/vs_testprofessional.exe).

## <a name="create-an-offline-installation-folder"></a>Bir çevrimdışı yükleme klasörü oluşturun

Bu adımı tamamlamak için bir Internet bağlantısına sahip olmalıdır. Çevrimdışı yükleme tüm diller ve tüm özellikleri ile oluşturmak için aşağıdaki örneklerde komutlarından birini kullanın.

   > [!IMPORTANT]
   > Tam bir Visual Studio 2017 düzeni en az 35 GB disk alanı gerektirir ve indirmek için biraz zaman alabilir.  Bkz: [ağ düzeni özelleştirme](#customizing-the-network-layout) yüklemek istediğiniz bileşenleri ile bir düzen oluşturma hakkında ayrıntılar için bölüm.
   >
   > [!TIP]
   > İndirme dizininizden komutu çalıştırdığınızdan emin olun. Genellikle, bu `C:\Users\<username>\Downloads` Windows 10 çalıştıran bir bilgisayarda.

- Visual Studio Enterprise çalıştırın:

  ```vs_enterprise.exe --layout c:\vs2017offline```

- Visual Studio Professional çalıştırın:

  ```vs_professional.exe --layout c:\vs2017offline```

- Visual Studio Community'yi çalıştırın:

  ```vs_community.exe --layout c:\vs2017offline```

## <a name="modify-the-responsejson-file"></a>Response.json dosyasını değiştirme

Kurulum'u çalıştırdığınızda, kullanılan varsayılan değerleri ayarlamak için response.json değiştirebilirsiniz.  Örneğin, yapılandırabileceğiniz `response.json` dosyası otomatik olarak seçilen iş yükleri için belirli bir grup seçin.
Bkz: [bir yanıt dosyasıyla otomatikleştirmek Visual Studio yükleme](automated-installation-with-response-file.md) Ayrıntılar için.

## <a name="copy-the-layout-to-a-network-share"></a>Düzen bir ağ paylaşımına kopyalayın

Diğer makinelerden çalıştırılabilir için bir ağ paylaşımında düzeni barındırır.
* Örnek:<br>
```xcopy /e c:\vs2017offline \\server\products\VS2017```

## <a name="customizing-the-network-layout"></a>Ağ düzeni özelleştirme

Ağ düzeninizi özelleştirmek için kullanabileceğiniz birkaç seçenek vardır. Yalnızca belirli bir kümesini içeren bir kısmi düzeni oluşturabilirsiniz [dil yerel ayarları](use-command-line-parameters-to-install-visual-studio.md#list-of-language-locales), [iş yükleri, bileşenleri ve önerilen veya isteğe bağlı bağımlılıklarını](workload-and-component-ids.md). Bu, yalnızca bir alt iş yüklerinin istemci iş istasyonlarına dağıtmak zorunda kalacaklarını bilmek durumlarda yararlı olabilir. Düzen özelleştirmek için tipik komut satırı parametreleri içerir:

* ```--add``` belirtmek için [iş yükü ya da bileşen kimlikleri](workload-and-component-ids.md).  Varsa `--add` kullanılır, yalnızca iş yükleri ve bileşenleri ile belirtilen `--add` indirilir.  Varsa `--add` olan kullanılmaz, tüm iş yükü ve bileşenler indirilir.
* ```--includeRecommended``` Belirtilen iş yükü kimlikleri için önerilen tüm bileşenleri eklemek için
* ```--includeOptional``` Belirtilen iş yükü kimlikleri için tüm önerilen ve isteğe bağlı bileşenleri eklemek için.
* ```--lang``` belirtmek için [dil yerel ayarları](use-command-line-parameters-to-install-visual-studio.md#list-of-language-locales).

Özel bir kısmi düzen oluşturmak bazı örnekleri aşağıda verilmiştir.

* Tüm iş yükleri ve yalnızca bir dil için bileşenleri indirmek için çalıştırın: <br>```vs_enterprise.exe --layout C:\vs2017offline --lang en-US```
* Tüm iş yükleri ve birden çok dil için bileşenleri indirmek için çalıştırın: <br>```vs_enterprise.exe --layout C:\vs2017offline --lang en-US de-DE ja-JP```
* Tüm diller için bir iş yükü indirmek için çalıştırın <br> ```vs_enterprise.exe --layout C:\vs2017offline --add Microsoft.VisualStudio.Workload.Azure --includeRecommended```
* İki iş yükleri ve üç diller için bir isteğe bağlı bileşen indirmek için çalıştırın: <br>```vs_enterprise.exe --layout C:\vs2017offline --add Microsoft.VisualStudio.Workload.Azure --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Component.GitHub.VisualStudio --includeRecommended --lang en-US de-DE ja-JP ```
* İki iş yükleri ve tüm önerilen bileşenleri indirmek için çalıştırın: <br>```vs_enterprise.exe --layout C:\vs2017offline --add Microsoft.VisualStudio.Workload.Azure --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Component.GitHub.VisualStudio --includeRecommended ```
* İki iş yükleri ve tüm önerilen ve isteğe bağlı bileşenleri indirmek için çalıştırın: <br>```vs_enterprise.exe --layout C:\vs2017offline --add Microsoft.VisualStudio.Workload.Azure --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Component.GitHub.VisualStudio --includeOptional ```

### <a name="new-in-153"></a>15.3 yenilikler

Bir düzen komutu çalıştırdığınızda, belirttiğiniz seçenekleri (iş yükleri ve diller gibi) kaydedilir. Sonraki düzeni komutları tüm önceki seçenekleri içerir.  Bir iş yükü için İngilizce yalnızca bir düzen bir örneği burada verilmiştir:

```vs_enterprise.exe --layout c:\VS2017Layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --lang en-US```

Düzenini daha yeni bir sürüme güncelleştirmek istediğinizde, ek komut satırı parametreleri belirtmek zorunda değilsiniz. Önceki ayarları kaydedilir ve bu düzen klasörde herhangi bir sonraki düzeni komut tarafından kullanılır.  Aşağıdaki komutu, var olan kısmi düzeni güncelleştirir.

```vs_enterprise.exe --layout c:\VS2017Layout```

Bunu yapmak nasıl bir örnek bir ek iş yükü, burada eklemek istediğinizde. Bu durumda, Azure iş yükü ve yerelleştirilmiş bir dil ekleyeceğiz.  Şimdi, yönetilen Masaüstü ve Azure Bu düzende dahil edilir.  İngilizce ve Almanca dil kaynakları için bu iş yükleri içerir. Düzen kullanılabilir en son sürüme güncelleştirilir.

```vs_enterprise.exe --layout c:\VS2017Layout --add Microsoft.VisualStudio.Workload.Azure --lang de-DE```

Varolan bir düzen tam bir düzene güncelleştirmek istiyorsanız, kullanmak--tümü, aşağıdaki örnekte gösterildiği gibi seçeneği.

```vs_enterprise.exe --layout c:\VS2017Layout --all```

## <a name="deploying-from-a-network-installation"></a>Bir ağ yüklemesinden dağıtma

Yöneticiler, Visual Studio istemci iş istasyonlarında bir yükleme komut dosyası bir parçası olarak dağıtabilirsiniz. Veya yönetici haklarına sahip kullanıcılar kendi makinede Visual Studio'yu yüklemek için doğrudan paylaşımından Kurulumu çalıştırın.

- Kullanıcıların çalıştırarak yükleyebilirsiniz: <br>```\\server\products\VS2017\vs_enterprise.exe```
- Yöneticiler, katılımsız modda çalıştırarak yükleyebilirsiniz: <br>```\\server\products\VS2017\vs_enterprise.exe --quiet --wait --norestart```

> [!TIP]
> Bir toplu iş dosyası bir parçası olarak çalıştırıldığında `--wait` seçeneği sağlar `vs_enterprise.exe` işlem çıkış kodu döndürmeden önce yükleme işlemi tamamlanana kadar bekler. Başka bir yüklemesi tamamlandı eylemleri gerçekleştirmek bir kuruluş yöneticisi istiyorsa, kullanışlıdır (örneğin, [yüklemenin başarılı olabilmesi için bir ürün anahtarı geçerli](automatically-apply-product-keys-when-deploying-visual-studio.md)), ancak yükleme işlemek için tamamlanıncaya kadar beklemeniz gerekir Bu yükleme dönüş kodu.  Kullanmıyorsanız, `--wait`, `vs_enterprise.exe` yükleme tamamlandıktan ve yükleme işleminin durumunu temsil etmez bir yanlış çıkış kodu döndürür önce çıkılıyor.

Bir düzeninden yüklediğinizde, yüklü içerik düzeninden alınır. Düzende değil bir bileşen seçerseniz, ancak onu Internet'ten kazanılması.  Visual Studio Kurulumu, düzeni, kullanım eksik herhangi bir içerik indirmesini önlemek istiyorsanız `--noWeb` seçeneği.  Varsa `--noWeb` kullanılır ve düzeni seçili yüklenmesi, başarısız kurulumu için herhangi bir içerik eksik.  

### <a name="error-codes"></a>Hata kodları

Kullandıysanız `--wait` parametresi, sonra işlemi sonucuna bağlı olarak `%ERRORLEVEL%` ortam değişkeni aşağıdaki değerlerden birine ayarlanır:

  | **Değer** | **Sonuç** |
  | --------- | ---------- |
  | 0 | İşlem başarıyla tamamlandı |
  | 3010 | İşlem başarıyla tamamlandı ancak kullanmadan önce yükleme yeniden başlatma gerekiyor |
  | Diğer | Hata koşulu oluştu - daha fazla bilgi için günlükleri denetleyin |

## <a name="updating-a-network-install-layout"></a>Ağ yükleme düzeni güncelleştiriliyor

Ürün güncelleştirmeleri kullanılabilir duruma geldiğinde isteyebilirsiniz [ağ yükleme düzeni güncelleştirme](update-a-network-installation-of-visual-studio.md) güncelleştirilmiş paketleri içerecek şekilde.

## <a name="how-to-create-a-layout-for-a-previous-visual-studio-2017-release"></a>Bir önceki Visual Studio 2017 yayın için bir düzen oluşturma

> [!NOTE]
> Kullanılabilir Visual Studio 2017 Önyükleyiciler ile [VisualStudio.com](http://www.visualstudio.com) indirin ve çalıştıkları her koşulda kullanılabilir en son Visual Studio 2017 sürümü yükleyin. Visual Studio önyükleyici hemen indirin ve şu andan itibaren altı ay çalıştırırsanız, bu daha sonra kullanılabilir Visual Studio 2017 yayın yükler. Bir düzen oluşturursanız, o düzeninden Visual Studio'yu yükleme düzeninde mevcut Visual Studio belirli sürümünü yükler. Yeni bir sürümünü çevrimiçi mevcut olabilecek olsa bile, Düzen Visual Studio sürümünü alır.

Visual Studio 2017 daha eski bir sürümü için bir düzen oluşturmanız gerekiyorsa, gidebilirsiniz https://my.visualstudio.com "sabit" Visual Studio 2017 Önyükleyiciler ile sürümleri karşıdan yüklemek için.

### <a name="how-to-get-support-for-your-offline-installer"></a>Çevrimdışı yükleyici için destek alma

Çevrimdışı yükleme ile ilgili bir sorun yaşıyorsanız, bunları hakkında bilmek isteriz. Bize iletmek için en iyi yolu kullanmaktır [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) aracı. Bu Aracı'nı kullanırken, bize telemetri ve tanılamak ve sorunu çözmeye yardımcı olmak için ihtiyacımız günlüklerini gönderebilirsiniz.

Diğer destek seçenekleri, çok sahibiz. Bir listesi için bkz: bizim [konuşun bize](../ide/how-to-report-a-problem-with-visual-studio-2017.md) sayfası.

## <a name="get-support"></a>Destek alma

Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sayfası. Sorun giderme adımlarını hiçbiri yardımcı, bize yükleme Yardımı (yalnızca İngilizce) için canlı sohbet tarafından başvurabilirsiniz. Ayrıntılar için bkz [Visual Studio destek sayfası](https://www.visualstudio.com/vs/support/#talktous).

Birkaç diğer destek seçenekleri şunlardır:

* Ürün sorunları bize bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem Visual Studio Yükleyicisi ve Visual Studio IDE görünür aracı.
* Üzerinde bir ürün önerisi bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunlarını izlemek ve yanıtlar bulmak [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/).
* ABD ve diğer Visual Studio geliştiriciler aracılığıyla devreye [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio). (Bu seçenek gerektiren bir [GitHub](https://github.com/) hesabı.)

## <a name="see-also"></a>Ayrıca bkz.

* [Visual Studio'yu yükleyin](install-visual-studio.md)
* [Visual Studio Yönetici Kılavuzu](visual-studio-administrator-guide.md)
* [Komut satırı parametrelerini kullanarak Visual Studio'yu yükleme](use-command-line-parameters-to-install-visual-studio.md)
* [Visual Studio iş yükü ve bileşen kimlikleri](workload-and-component-ids.md)
