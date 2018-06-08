---
title: Visual Studio performans ipuçları ve püf noktaları
ms.date: 08/31/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 2fbcb59e-e981-4b40-8b7a-c1140d31ec4b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 08b2e1087b97cb16a52a8abdf8f204fd0f3a0bfb
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845203"
---
# <a name="visual-studio-performance-tips-and-tricks"></a>Visual Studio performans ipuçları ve püf noktaları

Visual Studio performans önerileri nadir durumlarda oluşabilir düşük bellek durumlar için tasarlanmıştır. Bu durumlarda, değil kullanıyor olabilecek bazı Visual Studio özellikleri en iyi duruma getirebilirsiniz. Aşağıdaki ipuçları genel öneriler amaçlanmamıştır.

> [!NOTE]
> Bellek sorunları nedeniyle ürün kullanmakta zorluk yaşıyorsanız, aracılığıyla bize [geri bildirim aracı](../ide/how-to-report-a-problem-with-visual-studio-2017.md).

## <a name="use-a-64-bit-os"></a>Bir 64-bit işletim sistemi kullanın

Sisteminiz Windows 32-bit sürümünden bir 64-bit sürümüne yükseltirseniz, sanal bellek miktarı için Visual Studio 2 GB ile 4 GB'den genişletin. 32 bit işlem olsa bile bu önemli ölçüde daha büyük iş yüklerini işlemek üzere Visual Studio sağlar.

Daha fazla bilgi için bkz: [bellek sınırları](https://msdn.microsoft.com/library/windows/desktop/aa366778(v=vs.85).aspx#memory_limits) ve [/LARGEADDRESSAWARE 64-bit Windows sürümlerinde kullanmak](https://blogs.msdn.microsoft.com/oldnewthing/20050601-24/?p=35483/).

## <a name="disable-automatic-file-restore"></a>Otomatik dosya geri yükleme devre dışı bırak

Visual Studio'nun önceki oturumda açık bırakılmış belgeleri otomatik olarak açılır. Bu, bir çözüm % 30 veya daha fazla proje türü ve açılmakta olan belgeleri bağlı olarak yüklemek için gereken kez uzatmak. Windows Forms ve XAML ve bazı JavaScript ve typescript dosyaları gibi tasarımcıları açılması yavaş olabilir.

Visual Studio otomatik belge geri yükleme önemli ölçüde daha yavaş yüklemek bir çözüm ne zaman açtığını çubuğu sarı bildirir. Aşağıdaki adımları izleyerek otomatik dosya açmayı devre dışı bırakabilirsiniz:

1. Seçin **Araçları** > **seçenekleri** açmak için **seçenekleri** iletişim kutusu.

1. Üzerinde **proje ve çözüm** > **genel** sayfasında, seçimini **yeniden çözüm yük belgelerde**.

Otomatik dosya geri yükleme devre dışı bırakırsanız, açmak istediğiniz dosyaları bulmak için hızlı bir şekilde kullanmaktır [gitmek için](../ide/go-to.md). Seçin **Düzenle** > **gitmek için** > **tüm Git**, veya basın **Ctrl**+**T** .

## <a name="configure-debugging-options"></a>Hata ayıklama seçeneklerini yapılandırma

Genellikle bellek hata ayıklama oturumları sırasında düşük çalıştırıyorsanız, bir veya daha fazla yapılandırma değişikliklerini yaparak performansı en iyi duruma getirebilirsiniz.

- **Yalnızca kendi kodum etkinleştir**

    En basit iyileştirme etkinleştirmektir **sadece kendi kodumu** yalnızca projenizi simgelerini yükler özelliği. Bu özelliği etkinleştirmek, yönetilen uygulamaları (.NET) hata ayıklama için kaydetme önemli bellekte sonuçlanabilir. Bu seçenek zaten bazı proje türleri varsayılan olarak etkindir.

    Etkinleştirmek için **sadece kendi kodumu**, seçin **Araçları** > **seçenekleri** > **hata ayıklama**  >   **Genel**ve ardından **sadece kendi kodumu etkinleştir**.

- **Yüklemek için simgeler belirtin**

    Yerel hata ayıklama için simge dosyaları yükleme (*.pdb*) bellek kaynakları açısından maliyetlidir. Hata ayıklayıcı simgesi ayarlarınızı bellekten kazanacak şekilde yapılandırabilirsiniz. Genellikle, yalnızca projenizden modüllerini yüklemek için çözüm yapılandırın.

    Simge yükleme belirtmek için **Araçları** > **seçenekleri** > **hata ayıklama** > **simgeleri**.

    Seçenekleri ayarlamak **yalnızca modülleri belirtilen** yerine **tüm modülleri** ve ardından verdiğiniz yüklemek için modüllerine belirtin. Hata ayıklama sırasında belirli modüller de tıklayabilir **modülleri** açık bir modül simgesi yük içerecek şekilde penceresi. (Hata ayıklama sırasında penceresini açmak için seçin **hata ayıklama** > **Windows** > **modülleri**.)

    Daha fazla bilgi için bkz: [simge dosyaları anlamak](https://blogs.msdn.microsoft.com/visualstudioalm/2015/01/05/understanding-symbol-files-and-visual-studios-symbol-settings/).

- **Tanılama araçları devre dışı bırak**

    CPU kullandıktan sonra profil oluşturma devre dışı bırakmanız önerilir. Bu özellik, büyük miktarda kaynağı kullanabilir. CPU profil etkinleştirildikten sonra bu durum açıkça yapıldığında kapatmayı değer olacak şekilde sonraki hata ayıklama oturumları arasında kalıcı. Tanılama araçları sağlanan özellikler ihtiyacınız yoksa hata ayıklama sırasında devre dışı bırakarak bazı kaynaklar kaydedebilirsiniz.

    Devre dışı bırakmak için **tanılama araçları**, hata ayıklama oturumu başlatmak için seçin **Araçları** > **seçenekleri** > **etkinleştirmek tanılama Araçlar**ve seçeneğin işaretini kaldırın.

    Daha fazla bilgi için bkz: [profil oluşturma araçları](../profiling/profiling-tools.md).

## <a name="disable-tools-and-extensions"></a>Araçlar ve uzantılar devre dışı bırak

Bazı araçlar ya da uzantıları performansını artırmak için kapatılabilir.

> [!TIP]
> Performans sorunlarını genellikle, bir kerede tek uzantıları kapatmak kapatarak ve performans yeniden denetleme da ayırabilirsiniz.

### <a name="managed-language-service-roslyn"></a>Yönetilen dil hizmeti (Roslyn)

.NET derleme Platformu ("Roslyn") performans konuları hakkında daha fazla bilgi için bkz: [büyük çözümler için başarım düşünceleri](https://github.com/dotnet/roslyn/wiki/Performance-considerations-for-large-solutions).

- **Tam çözüm analizini devre dışı bırak**

    Visual Studio derleme çağırmadan önce hatalarla ilgili zengin bir deneyim sağlamak amacıyla, çözümün tamamında çözümlemesi gerçekleştirir. Bu özellik hataları mümkün olan en kısa sürede belirlemek kullanışlıdır. Ancak, büyük çözümler için bu özellik önemli bellek kaynaklarını tüketebilir. Bellek baskısı veya benzer sorunlar yaşıyorsanız, bu kaynakları boşaltmak için bu deneyimi devre dışı bırakabilirsiniz. Varsayılan olarak, bu seçenek etkin için Visual Basic ve C# için devre dışı.

    Devre dışı bırakmak için **tam çözüm analizini**, seçin **Araçları** > **seçenekleri** > **metin düzenleyici**sonra seçin Her iki **Visual Basic** veya **C#**. Seçin **Gelişmiş** ve seçimini **tam çözüm analizini etkinleştir**.

- **CodeLens devre dışı bırak**

    Visual Studio gerçekleştirir bir **tüm başvuruları Bul** görüntülendiği her yöntemini görev. CodeLens başvuru sayısı satır içi görüntüsünü gibi özellikler sağlar. İş ayrı bir işlemde gibi gerçekleştirilir *ServiceHub.RoslynCodeAnalysisService32*. Büyük çözümlerde veya kaynak kısıtlı sistemlerde, bu özellik performans üzerinde önemli bir etkisi olabilir. Bellek sorunları yaşıyorsanız, örneğin, 4 GB makinede veya bu işlem için yüksek CPU kullanımından büyük bir çözümde yüklenirken, kaynakları boşaltmak için CodeLens devre dışı bırakabilirsiniz.

    Devre dışı bırakmak için **CodeLens**, seçin **Araçları** > **seçenekleri** > **metin düzenleyici**  >   **Tüm diller** > **CodeLens**ve özellik seçimini kaldırın.

    > [!NOTE]
    > CodeLens Visual Studio Professional ve Enterprise sürümlerinde kullanılabilir.

### <a name="other-tools-and-extensions"></a>Diğer araçları ve uzantıları

- **Uzantılarını devre dışı bırakma**

    Uzantıları yeni işlevsellik sağlayan veya varolan işlevlerini genişletmek için Visual Studio eklenen ek yazılım bileşenleridir. Uzantıları genellikle bir kaynak bellek kaynağı sorunları olabilir. Bellek kaynağı sorunla karşılaşıyorsanız, senaryo veya iş akışının nasıl etkilediğini görmek için aynı anda tek uzantıları devre dışı bırakmayı deneyin.

    Uzantılarını devre dışı bırakmak için şu adrese gidin **Araçları** > **Uzantılar ve güncelleştirmeler**, belirli bir uzantıyı devre dışı bırakın.

- **XAML Tasarımcısı devre dışı bırak**

    XAML Tasarımcısı'nı varsayılan olarak etkindir, ancak yalnızca açarsanız kaynaklarını tüketir bir *.xaml* dosya. XAML dosyaları ile çalışır, ancak Tasarımcı işlevselliği kullanmak istiyor musunuz, bazı Bellek boşaltmak için bu özelliği devre dışı bırakın.

    Devre dışı bırakmak için **XAML Tasarımcısı**gidin **Araçları** > **seçenekleri** > **XAML Tasarımcısı**  >  **Etkinleştirmek XAML Tasarımcısı**ve seçeneğin işaretini kaldırın.

- **İş yüklerini kaldırın**

    Visual Studio yükleyicisi, artık kullanılmayan iş yükleri kaldırmak için kullanabilirsiniz. Bu eylem paketler ve artık gerekmeyen derlemeleri atlayarak başlatma ve çalışma zamanı maliyet verimli hale getirebilirsiniz.

## <a name="force-a-garbage-collection"></a>Çöp toplama zorla

CLR bir atık toplama bellek yönetimi sistemi kullanır. Bu sistemde, bazen bellek artık gerekli olmayan nesneleri tarafından kullanılır. Bu durum geçici; Çöp toplayıcı, performans ve kaynak kullanım buluşsal yöntemler temel alarak bu belleği serbest bırakır. Visual Studio'da bir kısayol tuşu kullanarak kullanılmayan belleği toplamak için CLR zorlayabilirsiniz. Çöp koleksiyonu için bekleyen önemli miktarda ve çöp toplama zorlamak, bellek kullanımı görmelisiniz *devenv.exe* işlem bırak **Görev Yöneticisi'ni**. Bu yöntemi kullanmak nadiren gereklidir. (Tam bir yapı, hata ayıklama oturumu veya bir çözüm açık olay) pahalı bir işlem tamamlandıktan sonra ancak, ne kadar bellek gerçekten işlem tarafından kullanılıyor belirlemenize yardımcı olur. Visual Studio (yönetilen ve yerel) karma olduğundan, bazen yerel ayırıcısı ve atık toplayıcı sınırlı bellek kaynakları için rekabete giriyorsa için mümkündür. Yüksek bellek kullanımı koşullar altında çalıştırmak için atık toplayıcı zorla yardımcı olabilir.

Çöp toplama zorlamak için kısayol tuşu kullanın: **Ctrl**+**Alt**+**Shift**+**F12**, **Ctrl**+**Alt**+**Shift**+**F12** (Bu iki kez basın).

Çöp toplama güvenilir bir şekilde zorlama çalışma, Visual Studio geri bildirim aracı ile bir rapor dosyası bu davranış büyük olasılıkla bir hata olduğundan, senaryonuzun yapar.

CLR atık toplayıcı ayrıntılı bir açıklaması için bkz: [çöp toplamanın Temelleri](/dotnet/standard/garbage-collection/fundamentals).

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio performansı en iyi duruma getirme](../ide/optimize-visual-studio-performance.md)
- [Çözümleri daha hızlı (Visual Studio blog) yükleme](https://blogs.msdn.microsoft.com/visualstudio/2018/04/04/load-solutions-faster-with-visual-studio-2017-version-15-6/)