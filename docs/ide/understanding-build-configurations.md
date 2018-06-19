---
title: Derleme yapılandırmalarını anlama
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-compile
ms.topic: conceptual
f1_keywords:
- SolutionProperties.ActiveConfig
- vs.build.newprojectconfiguration
- vc.proj.configurationsctrl.multipleconfigs
- vs.build.editsolutionconfigurations
- vs.build.editprojectconfigurations
- vs.multipleconfigurations
- vs.build.newsolutionconfiguration
- VS.ConfigurationManager
- VS.MultipleConfig
helpviewer_keywords:
- solution build configurations, about build configurations
- build configurations
- project build configurations
- build configurations, advanced
- projects [Visual Studio], build configuration
- solutions [Visual Studio], build configuration
ms.assetid: 934c727d-3a22-429c-bd13-3552cecf2e24
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cb699b02723e88454f26f4b897cfd7ba3ff46592
ms.sourcegitcommit: a8e01952be5a539104e2c599e9b8945322118055
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32425131"
---
# <a name="understand-build-configurations"></a>Derleme yapılandırmalarını anlama

Çözüm ve proje özelliklerini derlemeleri farklı türde kullanmak üzere farklı yapılandırmaları depolayabilirsiniz. Oluştur, seçin, değiştirmek veya bir yapılandırma silmek için kullanabileceğiniz **Configuration Manager**. Menü çubuğunda açmak için seçin **yapı** > **Configuration Manager**, yalnızca yazın veya **yapılandırma** içinde **hızlı başlatma**kutusu. Aynı zamanda **çözüm yapılandırmaları** listesini **standart** bir yapılandırma seçin veya açmak için araç **Configuration Manager**.

> [!NOTE]
> Çözüm yapılandırma ayarları araç çubuğunda bulunamıyor ve erişemiyor **Configuration Manager**, [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] geliştirme ayarlarını uygulanabilir. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Basic Geliştirici ayarları uygulanmış yapılandırmalarını yönetme](../ide/how-to-manage-build-configurations-with-visual-basic-developer-settings-applied.md).

Varsayılan olarak, hata ayıklama ve yayın yapılandırmaları kullanarak oluşturulan projeleri bulunmaktadır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] şablonları. Bir uygulama hata ayıklama hata ayıklama yapılandırmasını destekler ve sürüm yapılandırmasında dağıtılabilir uygulama sürümünü oluşturur. Daha fazla bilgi için bkz: [nasıl yapılır: ayarlama hata ayıklama ve yayın yapılandırmaları](../debugger/how-to-set-debug-and-release-configurations.md). Ayrıca, özel çözüm yapılandırmaları ve proje yapılandırmaları oluşturabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: oluşturma ve düzenleme yapılandırmaları](../ide/how-to-create-and-edit-configurations.md).

## <a name="solution-configurations"></a>Çözüm yapılandırmaları

Bir çözüm yapılandırmasını nasıl Çözümdeki projeler oluşturulan ve dağıtılan belirtir. Çözüm yapılandırmasını değiştirmek veya yeni bir tane tanımlamak için **Configuration Manager**altında **etkin çözüm yapılandırması**, seçin **Düzenle** veya **yeni** .

Her giriş **proje bağlamları** bir çözüm yapılandırması kutusunda çözümdeki bir proje ile temsil eder. Her birleşimi için **etkin çözüm yapılandırması** ve **etkin çözüm platformu**, her proje nasıl kullanıldığını ayarlayabilirsiniz. (Çözüm platformlar hakkında daha fazla bilgi için bkz: [anlayın yapı platformları](../ide/understanding-build-platforms.md).)

> [!NOTE]
> Ne zaman yeni bir çözüm yapılandırması tanımlamak ve seçmek **yeni proje yapılandırmaları oluşturma** onay kutusunu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] otomatik olarak yeni yapılandırma tüm projeleri atar. Benzer şekilde, ne zaman, yeni bir çözüm platformu tanımlamak ve seçmek **yeni proje platformları oluşturma** onay kutusunu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] otomatik olarak yeni platformu tüm projeleri atar. Ayrıca, yeni bir platformu hedefleyen bir projede eklerseniz, Visual Studio, platform çözümü platformlar listesine ekler ve tüm projeleri atar.
>
> Hala her proje için ayarları değiştirebilirsiniz.

Etkin çözüm yapılandırma ayrıca IDE bağlamı sağlar. Örneğin, bir proje üzerinde çalışıyorsanız ve yapılandırmayı belirtir, bir mobil aygıt için oluşturulacak **araç** bir mobil cihaz projesinde kullanılabilecek öğelerini görüntüler.

## <a name="project-configurations"></a>Proje yapılandırmaları
 Yapılandırması ve platformu, Proje hedefleri birlikte onu yapılandırıldığında kullanmak üzere özelliklerini belirtmek için kullanılır. Bir proje özellik tanımları her birleşimi yapılandırması ve platformu için farklı bir kümesi olabilir. Bir proje özelliklerini değiştirmek için özellik sayfalarını kullanabilirsiniz. (İçinde **Çözüm Gezgini**, proje için kısayol menüsünü açın ve ardından **özellikleri**.)

 Her proje yapılandırması için gerektiği şekilde yapılandırmaya bağlı özellikleri tanımlayabilirsiniz. Örneğin, belirli bir yapı için hangi proje öğeleri eklenecektir ayarlayabilir ve ne çıktı dosyaları oluşturulabilir, bunlar burada yerleştirilecek ve nasıl bunlar iyileştirilir.

 Proje yapılandırmaları oldukça farklı olabilir. Örneğin, kendi çıktı dosyasını başka bir yapılandırma kendi yürütülebilir en yüksek hızda çalıştığını belirtebilir sırasında en az alan kaplar için iyileştirilmiş bir yapılandırmasının özelliklerini belirtebilir.

 Proje yapılandırmaları çözümü tarafından depolanan — kullanıcı tarafından — böylece bir ekip tarafından paylaşılabilir.

 Proje bağımlılıkları yapılandırma bağımsız olmakla birlikte, yalnızca etkin çözüm yapılandırmasında belirtilen projeleri oluşturulacak.

## <a name="how-visual-studio-assigns-project-configurations"></a>Visual Studio Proje yapılandırmaları nasıl atar
 Yeni bir çözüm yapılandırmasını tanımlayın ve ayarları mevcut bir kopyalama, Visual Studio varsayılan proje yapılandırmaları atamak için aşağıdaki ölçütleri kullanır. Ölçüt gösterilen sırada değerlendirilir.

1.  Bir proje yapılandırma adı varsa (*\<yapılandırma adı > \<platform adı >*) tam olarak eşleşir yeni bir çözüm yapılandırması, bu yapılandırma adı atanır. Yapılandırma adları büyük küçük harfe duyarlı değildir.

2.  Projeyi Yapılandırma adı bölümü yeni çözüm yapılandırması ile eşleşen bir yapılandırma adı varsa, platform bölümü veya ile eşleşip eşleşmediğini yapılandırmayı atanır.

3.  Hala hiçbir eşleşme varsa, projede listelenen ilk yapılandırma atanır.

## <a name="how-visual-studio-assigns-solution-configurations"></a>Visual Studio çözüm yapılandırmaları nasıl atar
 Bir proje yapılandırma oluşturduğunuzda (içinde **Configuration Manager**, seçerek **yeni** açılır menüde **yapılandırma** sütunu, bu proje için) ve seçin **yeni çözüm yapılandırmaları oluşturma** onay kutusu, Visual Studio'nun desteklenen her platformda Projeyi derlemek benzer adlı çözüm yapılandırması arar. Bazı durumlarda, Visual Studio varolan çözüm yapılandırmaları yeniden adlandırır veya yenilerini tanımlar.

 Visual Studio çözüm yapılandırmaları atamak için aşağıdaki ölçütleri kullanır.

-   Bir proje yapılandırma bir platform belirtmeyen veya sadece bir platform belirtir, sonra yeni proje yapılandırmasının adı ile eşleşen bir çözüm yapılandırması bulunan eklenen veya. Bu çözüm yapılandırmasını varsayılan adını platform ad içermez; formundadır  *\<proje yapılandırma adı >*.

-   Bir proje birden çok platform destekliyorsa, bir çözüm yapılandırması bulunamadı veya desteklenen her platform için eklendi. Her çözüm yapılandırmasının adı proje yapılandırma adı ve platform adı içerir ve bir biçime sahip  *\<proje yapılandırma adı > \<platform adı >*.

## <a name="see-also"></a>Ayrıca bkz.

- [İzlenecek yol: bir uygulama oluşturma](../ide/walkthrough-building-an-application.md)
- [Derleme ve oluşturma](../ide/compiling-and-building-in-visual-studio.md)
- [Çözümler ve projeler](../ide/solutions-and-projects-in-visual-studio.md)
- [C/C++ derleme başvurusu](/cpp/build/reference/c-cpp-building-reference)
- [Devenv komut satırı anahtarları](../ide/reference/devenv-command-line-switches.md)