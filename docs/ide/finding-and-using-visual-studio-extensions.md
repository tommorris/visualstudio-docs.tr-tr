---
title: "Visual Studio uzantıları bulabilir ve | Microsoft Docs"
ms.custom: 
ms.date: 06/07/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.ExtensionManager
helpviewer_keywords:
- install extensions
- install packages
- managing extensions visual studio
ms.assetid: 4ca92d93-31b9-47ef-8109-4a429d9e2ca3
caps.latest.revision: "42"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: beec883c66182b3a840c0052b237c2ba41c5b023
ms.sourcegitcommit: 062795f922e7b59fe00d3d95a01a9a8a28840017
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/24/2018
---
# <a name="find-and-use-visual-studio-extensions"></a>Bulma ve Visual Studio uzantıları kullanma

Visual Studio uzantıları, Visual Studio içinde çalıştırın ve yeni veya geliştirilmiş Visual Studio özellikleri sağlayan kod paketlerdir. Visual Studio uzantıları hakkında daha fazla bilgi bulabilirsiniz: [Visual Studio SDK](../extensibility/visual-studio-sdk.md).

Kullanabileceğiniz **Uzantılar ve güncelleştirmeler** Visual Studio uzantılarını ve örnek Web siteleri ve diğer yerlerden yükleyin ve ardından etkinleştir, devre dışı bırakmak, güncelleştirme veya bunları kaldırmak için iletişim kutusu. (**Araçlar / Uzantılar ve güncelleştirmeler**, veya türü **uzantıları** içinde **hızlı başlatma** penceresi). İletişim kutusu da yüklü örnekleri ve uzantıları için güncelleştirmeleri gösterir. Web sitelerinden uzantıları indirmesi veya diğer geliştiricilerden alabilirsiniz.

> [!NOTE]
> Visual Studio 2015'ten başlayarak, Visual Studio Market'te barındırılan uzantıları otomatik olarak güncelleştirilir. Bu ayarı aracılığıyla değiştirebilirsiniz **Uzantılar ve güncelleştirmeler** iletişim.  Bölümüne bakarak **otomatik uzantısı güncelleştirmeler** aşağıda Ayrıntılar için.

## <a name="finding-visual-studio-extensions"></a>Visual Studio uzantıları bulma

Uzantılar'dan yükleyebilirsiniz [Visual Studio Market'te](https://marketplace.visualstudio.com/vs). Uzantılar; denetimler, örnekler, şablonlar, araçlar veya Visual Studio'ya işlevsellik katan diğer bileşenler olabilir. Visual Studio uzantıları VSIX paket biçiminde destekler; bu proje şablonları içerir, öğe şablonlarını, **araç** öğeleri, yönetilen uzantısı çerçevesi (MEF) bileşenleri ve VSPackages. Ayrıca indirin ve yükleyin MSI tabanlı uzantılar, ancak **Uzantılar ve güncelleştirmeler** iletişim kutusu etkinleştirmek veya devre dışı. Visual Studio Market'te VSIX ve MSI uzantılarını içerir.

## <a name="installing-or-uninstalling-visual-studio-extensions"></a>Yükleme veya Visual Studio uzantılarını kaldırma

İçinde **Uzantılar ve güncelleştirmeler**, yüklemek istediğiniz uzantısı bulunamıyor. (Adını veya adının uzantısı'nın bir parçası biliyorsanız, içinde arama yapabilirsiniz **arama** penceresi.) Tıklatın **karşıdan**.  Uzantısı yükleme için zamanlanacak. Visual Studio tüm örneklerini kapatıldıktan sonra uzantınızı yüklenir.

Bağımlılıkları olan bir uzantıyı yüklemeye çalışırsanız, yükleyici bunların yüklenmiş olup olmadığını denetler. Bunlar yüklü değilse, **Uzantılar ve güncelleştirmeler** iletişim kutusu uzantısını yüklemeden önce yüklü olması gereken bağımlılıkları listeler.

Bir uzantıyı kullanmayı bırakmak isterseniz devre dışı bırakabilir veya kaldırabilirsiniz. Bir uzantı devre dışı bırakıldığında yüklü kalır, ancak etkin değildir. Yalnızca VSIX uzantılarını devre dışı bırakabilirsiniz; bir MSI kullanılarak yüklenen uzantıları yalnızca kaldırılabilir. Uzantı bulun ve tıklatın **kaldırma** veya **devre dışı**. Devre dışı bırakılmış bir uzantı kaldırmak için Visual Studio yeniden başlatmalısınız.

## <a name="per-user-and-administrative-extensions"></a>Kullanıcı Başına ve Yönetim Uzantıları

Çoğu uzantıları kullanıcı başına uzantıları ve yüklendiği **%LocalAppData%\Microsoft\VisualStudio\\< Visual Studio sürümü\>\Extensions\\**  klasör. Birkaç uzantıları yönetim uzantıları ve yüklendiği  **\<Visual Studio yükleme klasörü > \Common7\IDE\Extensions\\**  klasör.

Sisteminizi hataları veya kötü amaçlı kod içerebilir uzantıları karşı korumak için yalnızca Visual Studio normal kullanıcı izinlerine sahip çalıştırıldığında yüklemek için kullanıcı başına uzantıları kısıtlayabilirsiniz. Bu, Visual Studio Yönetici izinleriyle çalıştırdığınızda kullanıcı başına uzantıları devre dışı anlamına gelir. Bunu yapmak için şu adrese gidin **Uzantılar ve güncelleştirmeler** seçenekler sayfası (**Araçlar / Seçenekler**, **ortam**, **Uzantılar ve güncelleştirmeler**, veya yalnızca tür **uzantısı** içinde **hızlı başlatma** penceresi). Clear **yönetici olarak çalışırken kullanıcı uzantıları başına yük** onay kutusunu işaretleyin, sonra Visual Studio'yu yeniden başlatın.

## <a name="automatic-extension-updates"></a>Otomatik uzantısı güncelleştirmeleri

Kullanıcı başına uzantıları, yeni bir sürümü için Visual Studio Market'te kullanılabilir olduğunda otomatik olarak güncelleştirilir.  Uzantısı'nın yeni sürümü algılandı ve arka planda ve Visual Studio sonraki yeniden başlatmada yüklü, uzantının yeni sürümünü çalıştıran.

Yalnızca kullanıcı başına uzantıları otomatik olarak güncelleştirilebilir.  Tüm kullanıcılar güncelleştirilmez ve yeni sürümler aracılığıyla yine de el ile yüklemek için yüklenen yönetim uzantıları **Uzantılar ve güncelleştirmeler** iletişim kutusu **güncelleştirmeleri** düğümü. Hangi uzantıların uzantının Ayrıntılar bölmesinde otomatik olarak güncelleştirilecek görebilirsiniz **Uzantılar ve güncelleştirmeler** iletişim.

Otomatik güncelleştirmeleri devre dışı bırakmak istiyorsanız, tüm uzantıları veya yalnızca belirli uzantılara özelliğini devre dışı bırakabilirsiniz.

- Tüm uzantıları için otomatik güncelleştirmeleri devre dışı bırakmayı tercih **Uzantılar ve güncelleştirmeler ayarlarınızı değiştirmek** bağlamak **Uzantılar ve güncelleştirmeler** iletişim ve işaretini **otomatik olarak güncelleştir Uzantıları**.

- Belirli bir uzantı için otomatik güncelleştirmeleri devre dışı bırakmak için onay kutusunu temizleyin **otomatik olarak bu uzantı güncelleştirme** uzantının Ayrıntılar bölmesinde seçeneğini sağ tarafında **Uzantılar ve güncelleştirmeler** iletişim.

> [!NOTE]
> Visual Studio 2015 güncelleştirme 2'de başlayarak, belirtebilirsiniz (içinde **Araçlar / Seçenekler / ortamı / Uzantılar ve güncelleştirmeler**) kullanıcı başına uzantılar, tüm kullanıcı uzantıları veya her iki (varsayılan ayar) için Otomatik Güncelleştirmeler isteyip istemediğinizi.

## <a name="extension-crashunresponsiveness-notifications"></a>Uzantı kilitlenme/yanıt vermeyi durdurma sorununu bildirimleri

Yeni **Visual Studio 2017 sürüm 15.3**, Visual Studio hakkında sizi uyarır, uzantı önceki bir oturumu sırasında bir çökmesine neden dahil şüphelendiği durumunda. Visual Studio kilitlendiğinde özel durum yığını depolar. Visual Studio başlatır, sonraki açışınızda yaprak ile başlayan ve temel çalışma yığınının inceler. Visual Studio bir çerçeve yüklü ve etkin uzantının bir parçası olan bir modüle ait olduğunu belirlerse, bir bildirim gösterilir.

Yeni **Visual Studio sürümü 15,6 preview 3**, Visual Studio de bildirir, bir uzantı yanıt vermediği için kullanıcı Arabirimi neden suspects durumunda.

Bu bildirimler gösterilen sırada bildirimi yok sayabilirsiniz veya aşağıdaki eylemlerden birini gerçekleştirin:

- Seçin **bu uzantıyı devre dışı bırakmak**. Visual Studio uzantısını devre dışı bırakır ve, devre dışı bırakma etkinleşmesi için sisteminizi yeniden başlatması gerekip gerekmediğini bilmenizi sağlar. Uzantı yeniden etkinleştirebilirsiniz **Uzantılar ve güncelleştirmeler** istiyorsanız, iletişim kutusu.

- Seçin **bu iletiyi bir daha gösterme**. 
  - Bildirim önceki bir oturumda bir kilitlenme ilgiliyse, Visual Studio artık bir bildirim bu uzantı ile ilişkilendirilmiş bir kilitlenme olduğunda oluşur gösterir. Yanıt vermeyi durdurma sorununu kilitlenmelerine veya diğer uzantıları ile ilişkilendirilebilir yanıt vermeyi durdurma sorununu için veya bu uzantı ile ilişkili olabilir, visual Studio hala bildirimleri göster. 
  - Bildirim yanıt vermeyi durdurma sorununu ilgiliyse bu uzantı yanıt vermeyi durdurma sorununu ile ilişkili olduğunda IDE bildirim artık göster. Visual Studio hala bu uzantı için kilitlenme ilgili bildirimler ve diğer uzantıları için kilitlenme ve yanıt vermeyi durdurma sorununu ilgili bildirimler gösterir. 

- Seçin **daha fazla bilgi edinin** bu sayfaya geliyor.

- Seçin **X** bildirim kapatmak için bildirim sonunda düğmesi. Gelecekteki bir kilitlenme veya UI yanıt vermeyi durdurma sorununu ile ilişkilendirilen uzantısı örnekleri için yeni bir bildirim görüntülenir.

> [!NOTE]
> Bir kullanıcı Arabirimi yanıt vermeyi durdurma sorununu veya kilitlenme bildirimi yalnızca uzantının modüllerinden birini yığında UI yanıt vermeyen veya ne zaman kilitlenme oluştu anlamına gelir. Bu mutlaka uzantısı sorunlu olduğu anlamına gelmez. Uzantı yanıt vermeyen UI veya bir kilitlenme sırayla sonuçlandı Visual Studio parçası olan kod adlandırılan mümkündür. Ancak, bildirim hala UI yanıt vermeyi durdurma sorununu ya da kilitlenme sonuçlanan uzantı sizin için önemli değilse yararlı olabilir. Bu durumda, uzantıyı devre dışı bırakma UI yanıt vermeyi durdurma sorununu ya da kilitlenme gelecekte üretkenliğinizi etkilemeden önler. 

## <a name="sample-master-copies-and-working-copies"></a>Örnek ana kopya ve çalışma kopyalar

Çevrimiçi bir örneği yüklediğinizde, çözüm iki konumda depolanır:

- Çalışma kopyası belirtilen konumda depolanır **yeni proje** iletişim kutusu.

- Ayrı bir ana kopya bilgisayarınızda depolanır.

Kullanabileceğiniz **Uzantılar ve güncelleştirmeler** bu örnekleri ile ilgili görevleri gerçekleştirmek için iletişim kutusunda:

- Yüklediğiniz örneklerin ana kopyalarını listeleyin.

- Bir örneğin ana kopyasını devre dışı bırakın veya kaldırın.

- Örnek Paketleri (bir teknoloji veya özellik ile ilgili örnek koleksiyonları) yükleyin.

- Tek tek çevrimiçi örnekleri yükleyin. (Ayrıca bu uygulamasında gerçekleştirebileceğiniz **yeni proje** iletişim kutusu.)

- Yüklü örnekler için kaynak kodu değişiklikleri yayımlandığında güncelleştirme bildirimlerini görüntüleyin.

- Bir güncelleştirme bildirimi olduğunda yüklü bir örnek ana kopyasını güncelleştirin.

## <a name="installing-without-using-the-extensions-and-updates-dialog-box"></a>Uzantılar ve Güncelleştirmeler İletişim Kutusunu Kullanmadan Yükleme

.Vsix dosyalarında paketli uzantıları Visual Studio Market'te dışındaki konumlarda bulunabilir. **Uzantılar ve güncelleştirmeler** iletişim kutusu, bu dosyaları algılayamıyor, ancak dosyayı çift veya dosya seçerek ve ENTER tuşuna basarak bir .vsix dosyası yükleyebilirsiniz. Bundan sonra yönergeleri izlemeniz yeterlidir. Uzantısı yüklü olduğunda kullanabileceğiniz **Uzantılar ve güncelleştirmeler** iletişim kutusu etkinleştirmek, devre dışı bırakın veya kaldırın.

## <a name="extension-types-not-supported-by-the-extensions-and-updates-dialog-box"></a>Uzantıları tarafından desteklenmeyen uzantı türleri ve güncelleştirmeleri iletişim kutusu

Visual Studio devam eder Microsoft Installer (MSI) tarafından yüklenen Uzantıları desteği ancak ile **Uzantılar ve güncelleştirmeler** değişiklik yapmadan iletişim kutusu.

> [!TIP]
> MSI tabanlı uzantı extension.vsixmanifest dosya içeriyorsa, uzantı görünür **Uzantılar ve güncelleştirmeler** iletişim kutusu.
