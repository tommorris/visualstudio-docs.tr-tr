---
title: Visual Studio’nun ağ tabanlı yüklemesini güncelleştirme
description: Kullanarak ağ tabanlı bir Visual Studio yükleme güncelleştirme öğrenin düzeni komutu
ms.date: 08/14/2017
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 1AF69C0E-0AC9-451B-845D-AE4EDBCEA65C
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 64a8fbd599667c7c28a48f80ff97932161c9e2f7
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/20/2018
ms.locfileid: "36282567"
---
# <a name="update-a-network-based-installation-of-visual-studio"></a>Visual Studio’nun ağ tabanlı yüklemesini güncelleştirme

Bu mümkün olması için en son ürün güncelleştirmelerini ile Visual Studio'nun bir ağ yüklemesi düzenini güncelleştirmek için bir yükleme noktası olarak her ikisi de Visual Studio ve aynı zamanda istemciye zaten dağıtılmış olan yüklemeleri korumak için en son güncelleştirmesini kullandı iş istasyonları.

## <a name="how-to-update-a-network-layout"></a>Bir ağ düzeni güncelleştirme

Böylece en son güncelleştirmeleri içeren ağ yükleme paylaşımınıza yenilemek için çalıştırın artımlı olarak güncelleştirilmiş paketlerini indirmek için düzeni komutu.

İlk ağ düzeni oluşturduğunuz sırada kısmi bir düzen seçtiyseniz, bu ayarları kaydedilir.  Tüm gelecekteki düzeni komutları, önceki seçenekleri artı belirttiğiniz yeni seçenekleri kullanın.  (15.3 içinde yeni budur.)  Bir düzen eski bir sürüm kullanıyorsanız, içeriği güncelleştirmek için ağ yükleme düzeni (diğer bir deyişle, aynı iş yükleri ve dilleri) ilk oluştururken kullandığınız aynı komut satırı parametreleri kullanmanız gerekir.

Bir dosya paylaşımında bir düzen barındırıyorsanız, Düzen (örneğin, c:\vs2017offline) özel bir kopyasını güncelleştirin ve sonra tüm güncelleştirilmiş içerik karşıdan sonra dosya paylaşımına kopyalayın gerekir (örneğin, \\server\products\VS2017). Bunu yapmazsanız, düzeni güncelleştirdiğiniz sırada Kur'u çalıştırın tüm kullanıcılar, henüz tamamen güncelleştirilmez çünkü tüm içeriğin düzenden almak mümkün olmayabilir büyük bir fırsat yok.

Şimdi aracılığıyla nasıl oluşturulacağı ve bir düzen güncelleştirme yol:

* İlk olarak, yalnızca İngilizce için bir düzen ile bir iş yükü oluşturma örneği şöyledir:

  ```cmd
  vs_enterprise.exe --layout c:\VS2017Layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --lang en-US
  ```

* Bu aynı düzeni daha yeni bir sürüme güncelleştirmek bırakılır. Ek komut satırı parametreleri belirtmek zorunda değilsiniz. Önceki ayarları kaydedildi ve bu düzen klasörde herhangi bir sonraki düzeni komut tarafından kullanılır.

  ```cmd
  vs_enterprise.exe --layout c:\VS2017Layout
  ```

* Katılımsız bir şekilde daha yeni bir sürüme düzeninizi güncelleştirmek bırakılır. Düzen işlemi yeni bir konsol penceresi Kurulum işlemi çalıştırır. Böylece kullanıcılar nihai sonucu ve oluşmuş hataları özetini görebilirsiniz penceresi açık kalır. Katılımsız bir şekilde çalıştığını yerleşimi işleminin (örneğin, en son sürüme düzeninizi güncelleştirmek için düzenli olarak çalıştırılan bir komut dosyası varsa), ardından `--passive` parametre ve işlem otomatik olarak kapatılacak penceresi.

  ```cmd
  vs_enterprise.exe --layout c:\VS2017Layout --passive
  ```

* Bir ek iş yükü ve yerelleştirilmiş dil eklemek bırakılır.  (Bu komut Azure iş yükü ekler.)  Şimdi yönetilen Masaüstü ve Azure Bu düzende dahil edilir.  İngilizce ve Almanca dil kaynakları da tüm bu iş yükleri için dahil edilmiştir.  Ve düzeni kullanılabilir en son sürüme güncelleştirilir.

  ```cmd
  vs_enterprise.exe --layout c:\VS2017Layout --add Microsoft.VisualStudio.Workload.Azure --lang de-DE
  ```

* Son olarak, burada da bir ek iş yükü ve yerelleştirilmiş dil sürümü güncelleştirmeden ekleme. (Bu komut, ASP.NET ve Web iş yükü ekler.)  Şimdi yönetilen Masaüstü, Azure ve ASP.NET ve Web iş yüklerini Bu düzende dahil edilir.  İngilizce, Almanca ve Fransızca için Türkçe kaynaklar için bu iş yükleri de dahildir.  Ancak, bu komutu çalıştırdığınızda düzeni kullanılabilir en son sürüme güncelleştirilmedi.  Varolan sürümünde kalır.

  ```cmd
  vs_enterprise.exe --layout c:\VS2017Layout --add Microsoft.VisualStudio.Workload.NetWeb --lang fr-FR --keepLayoutVersion
  ```

## <a name="how-to-deploy-an-update-to-client-machines"></a>İstemci makineler için bir güncelleştirme dağıtma

Ağ ortamınızı nasıl yapılandırıldığına bağlı olarak, bir güncelleştirme Kurumsal yönetici tarafından dağıtılan ya da bir istemci makinesinden başlattı.

* Kullanıcılar bir çevrimdışı yükleme klasöründen yüklü olduğu bir Visual Studio örneği güncelleştirebilirsiniz:
  * Visual Studio yükleyiciyi çalıştırın.
  * Ardından **güncelleştirme**.

* Yöneticiler, Visual Studio istemci dağıtımları iki ayrı komutların herhangi bir kullanıcı etkileşimi olmadan güncelleştirebilirsiniz:
  * İlk olarak, Visual Studio Yükleyicisi güncelleştirmesi: <br>```vs_enterprise.exe --quiet --update```
  * Ardından, Visual Studio uygulama güncelleştirin: <br>```vs_enterprise.exe update --installPath "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise" --quiet --wait --norestart```

> [!NOTE]
> Kullanım [vswhere.exe komutu](tools-for-managing-visual-studio-instances.md) Visual Studio mevcut bir örneğini bir istemci makine üzerinde yükleme yolunu tanımlamak için.
>
> [!TIP]
> Güncelleştirme bildirimlerini kullanıcılara ne zaman sunulduğundan denetleme hakkında daha fazla bilgi için bkz: [ağ tabanlı Visual Studio dağıtımlar için güncelleştirmeleri kontrol](controlling-updates-to-visual-studio-deployments.md).

## <a name="how-to-verify-a-layout"></a>Bir düzen doğrulama hakkında

Kullanım `--verify` sağlanan Çevrimdışı Önbellek üzerinde doğrulama gerçekleştirmek için. Bu paketleri dosyaları eksik veya hatalı olup olmadığını denetler. Doğrulama sonunda, dosyaları ve geçersiz dosyaları eksik listesini yazdırır.

```cmd
vs_enterprise.exe --layout <layoutDir> --verify
```

Vs_enterprise.exe içinde layoutDir çağrılabilir.

> [!NOTE]
> Tarafından gereken bazı önemli meta veri dosyaları `--verify` seçeneği düzeni çevrimdışı önbellekte olması gerekir. Bu meta veri dosyaları eksikse, "--doğrulayın" çalıştıramaz ve Kurulum, bir hata verir. Bu hata ile karşılaşırsanız, yeni bir çevrimdışı düzenini farklı bir klasör (veya aynı Çevrimdışı Önbellek klasörü. yeniden oluşturma Bu nedenle yapmak için ilk çevrimdışı düzeni oluşturmak için kullanılan aynı düzeni komutunu çalıştırın. Örneğin, `Vs_enterprise.exe --layout <layoutDir>`.

Oluşturduğunuz yeni düzene ilk düzeni aynı sürüme olmayabilir için Microsoft Visual Studio güncelleştirmeleri düzenli olarak gelir.

## <a name="how-to-fix-a-layout"></a>Bir düzen gidermeye yönelik

Kullanım `--fix` olarak aynı doğrulamayı gerçekleştirmek için `--verify` ve bilinen sorunları gidermek için de deneyin. `--fix` İşlemi Internet bağlantısı gerekir, böylece makinenizi çağırmayı önce Internet'e bağlı olduğundan emin olun `--fix`.

```cmd
vs_enterprise.exe --layout <layoutDir> --fix
```

Vs_enterprise.exe içinde layoutDir çağrılabilir.

## <a name="how-to-remove-older-versions-from-a-layout"></a>Bir düzeninden eski sürümlerini kaldırma

Çevrimdışı bir önbellek düzeni güncelleştirmeleri gerçekleştirdikten sonra Düzen önbellek klasörünün en son Visual Studio yüklemesi tarafından artık gerekli olmayan bazı eski paketler olabilir. Kullanabileceğiniz `--clean` eski paketlerin bir Çevrimdışı Önbellek klasör kaldırma seçeneği.

Bunu yapmak için eski paketleri içeren katalog manifest(s) için dosya yollarını gerekir. Çevrimdışı düzeni önbellek "Arşivi" klasöründe katalog bildirimleri bulabilirsiniz. Bir düzen'ı güncelleştirdiğinizde var. kaydedilir. "Arşivi" klasöründe, "her biri bir kullanılmayan katalog bildirimi içeren klasörleri adlı bir veya daha fazla GUID" yoktur. "GUID" klasörlerin sayısını çevrimdışı önbelleğiniz yapılan güncelleştirme sayısı ile aynı olmalıdır.

Bazı dosyalar her "GUID" klasöre kaydedilir. İki çoğu ilgi "catalog.json" dosyası ve bir "version.txt" dosyası dosyalardır. "Catalog.json" dosya geçirilecek gerekir kullanılmayan katalog bildirimidir `--clean` seçeneği. Diğer version.txt dosyası bu eski katalog bildirimi sürümünü içerir. Sürüm numarasına göre artık kullanılmayan paketler bu katalog bildirimden kaldırmak isteyip istemediğinize karar verebilirsiniz. Bir "GUID" klasörler üzerinden geçerken aynı yapabilirsiniz. Üzerinde katalogları kararı sonra istediğiniz temiz çalıştırmak `--clean` bu katalog dosyaları yollara sağlayarak komutu.

İşte bazı örnekler nasıl kullanılacağı temiz seçeneği:

```cmd
vs_enterprise.exe --layout <layoutDir> --clean <file-path-of-catalog1> <file-path-of-catalog2> …
```

```cmd
vs_enterprise.exe --layout <layoutDir> --clean <file-path-of-catalog1> --clean <file-path-of-catalog2> …
```

Vs_enterprise.exe içinde de çalıştırabilirsiniz &lt;layoutDir&gt;. Örnek buradadır:

```cmd
c:\VS2017Layout\vs_enterprise.exe --layout c:\VS2017Layout --clean c:\VS2017Layout\Archive\1cd70189-fc55-4583-8ad8-a2711e928325\Catalog.json --clean c:\VS2017Layout\Archive\d420889f-6aad-4ba4-99e4-ed7833795a10\Catalog.json
```

Bu komutu çalıştırdığınızda, Kurulum bu kaldıracak dosyaların listesini bulmak için Çevrimdışı Önbellek klasörü analiz eder. Ardından, silinmesi ve silme işlemleri onaylamak için giderek dosyalarını gözden geçirmek için bir fırsat sahip olur.

## <a name="get-support"></a>Destek alma

Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sayfası. Sorun giderme adımlarını hiçbiri yardımcı, bize yükleme Yardımı (yalnızca İngilizce) için canlı sohbet tarafından başvurabilirsiniz. Ayrıntılar için bkz [Visual Studio destek sayfası](https://visualstudio.microsoft.com/vs/support/#talktous).

Birkaç diğer destek seçenekleri şunlardır:

* Ürün sorunları bize bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem Visual Studio Yükleyicisi ve Visual Studio IDE görünür aracı.
* Üzerinde bir ürün önerisi bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunlarını izlemek ve yanıtlar bulmak [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/).
* ABD ve diğer Visual Studio geliştiriciler aracılığıyla devreye [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio). (Bu seçenek gerektiren bir [GitHub](https://github.com/) hesabı.)

## <a name="see-also"></a>Ayrıca bkz.

* [Visual Studio'yu yükleyin](install-visual-studio.md)
* [Visual Studio Yönetici Kılavuzu](visual-studio-administrator-guide.md)
* [Komut satırı parametrelerini kullanarak Visual Studio'yu yükleme](use-command-line-parameters-to-install-visual-studio.md)
* [Visual Studio örneklerini algılamaya ve yönetmeye yönelik araçlar](tools-for-managing-visual-studio-instances.md)
* [Visual Studio dağıtımları ağ tabanlı denetim güncelleştirmeleri](controlling-updates-to-visual-studio-deployments.md)
