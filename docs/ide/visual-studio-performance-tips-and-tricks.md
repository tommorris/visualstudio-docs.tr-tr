---
title: "Visual Studio performans ipuçları ve püf noktaları | Microsoft Docs"
ms.date: 08/31/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugger
ms.assetid: 2fbcb59e-e981-4b40-8b7a-c1140d31ec4b
caps.latest.revision: "1"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 936d0df8c838227c5d6c99b0f04f1069eae8a277
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="visual-studio-performance-tips-and-tricks"></a>Visual Studio performans ipuçları ve püf noktaları

Visual Studio performans önerileri nadir durumlarda oluşabilir düşük bellek durumlar için tasarlanmıştır. Bu durumlarda, değil kullanıyor olabilecek bazı Visual Studio özellikleri en iyi duruma getirebilirsiniz. Aşağıdaki ipuçları genel öneriler amaçlanmamıştır.

> [!NOTE]
> Bellek sorunları nedeniyle ürün kullanmakta zorluk yaşıyorsanız, geri bildirim aracı aracılığıyla bize bildirin.

## <a name="optimize-your-environment"></a>Ortamınıza en iyi duruma getirme

- **64 bit işletim sistemi kullanın**

    Sisteminiz Windows 32-bit sürümünden bir 64-bit sürümüne yükseltirseniz, sanal bellek miktarı için Visual Studio 2 GB ile 4 GB'den genişletin. Bu, 32 bitlik işlem olsa bile önemli ölçüde daha büyük iş yüklerini işlemek üzere Visual Studio sağlar.

    Daha fazla bilgi için bkz: [bellek sınırları](https://msdn.microsoft.com/en-us/library/windows/desktop/aa366778(v=vs.85).aspx#memory_limits) ve [/LARGEADDRESSAWARE 64-bit Windows sürümlerinde kullanarak](https://blogs.msdn.microsoft.com/oldnewthing/20050601-24/?p=35483/).

## <a name="configure-solution-and-projects"></a>Çözüm ve projeleri yapılandırma

Çok sayıda proje çok büyük bir çözüm varsa, aşağıdaki iyileştirmeleri yaparak yararlı:

- **Unload projeleri**

    Nadiren kullanılan tek tek projeleri Çözüm Gezgini'nden sağ bağlam menüsünü kullanarak el ile kaldırma.

- **Çözümü yeniden Düzenle**

    Yaygın olarak kullanılan projelerle birkaç küçük çözüm dosyalarına çözümünüzü bölebilirsiniz. Bu yeniden düzenleme iş akışınız için bellek kullanımını önemli ölçüde azaltan. Ayrıca daha küçük çözümleri daha hızlı yük.

## <a name="configure-debugging-options"></a>Hata ayıklama seçeneklerini yapılandırma
Genellikle bellek hata ayıklama oturumları sırasında düşük çalıştırıyorsanız, bir veya daha fazla yapılandırma değişikliklerini yaparak performansı en iyi duruma getirebilirsiniz.

- **Yalnızca kendi kodum etkinleştir**

    En basit iyileştirme etkinleştirmektir **sadece kendi kodumu** yalnızca projenizi simgelerini yükler özelliği. Bu özelliği etkinleştirmek, yönetilen uygulamaları (.NET) hata ayıklama için kaydetme önemli bellekte sonuçlanabilir. Bu seçenek zaten bazı proje türleri varsayılan olarak etkindir.

    Etkinleştirmek için **sadece kendi kodumu**, seçin **Araçlar > Seçenekler > hata ayıklama > Genel**ve ardından **sadece kendi kodumu etkinleştir**.

- **Yüklemek için simgeler belirtin**

    Yerel hata ayıklama için simge dosyaları (.pdb) yükleniyor bellek kaynakları açısından pahalı. Hata ayıklayıcı simgesi ayarlarınızı bellekten kazanacak şekilde yapılandırabilirsiniz. Genellikle, yalnızca projenizden modüllerini yüklemek için çözüm yapılandırın.

    Simge yükleme belirtmek için **Araçlar > Seçenekler > hata ayıklama > simgeleri**.

    Seçenekleri ayarlamak **yalnızca modülleri belirtilen** yerine **tüm modülleri** ve ardından verdiğiniz yüklemek için modüllerine belirtin. Hata ayıklama sırasında belirli modüller de tıklayabilir **modülleri** açık bir modül simgesi yük içerecek şekilde penceresi. (Hata ayıklama sırasında penceresini açmak için seçin **hata ayıklama > Windows > modülleri**.)

    Daha fazla bilgi için bkz: [simge dosyaları anlama](https://blogs.msdn.microsoft.com/visualstudioalm/2015/01/05/understanding-symbol-files-and-visual-studios-symbol-settings/).

- **Tanılama araçları devre dışı bırak**

    CPU kullandıktan sonra profil oluşturma devre dışı bırakmanız önerilir. Bu özellik, büyük miktarda kaynağı kullanabilir. CPU profil etkinleştirildikten sonra bu durum açıkça yapıldığında kapatmayı değer olacak şekilde sonraki hata ayıklama oturumları arasında kalıcı. Tanılama araçları sağlanan özellikler ihtiyacınız yoksa hata ayıklama sırasında devre dışı bırakarak bazı kaynaklar kaydedebilirsiniz.

    Tanılama araçları devre dışı bırakmak için bir hata ayıklama oturumu başlatmak için seçin **Araçlar > Seçenekler > etkinleştirmek tanılama araçları**ve seçeneğin işaretini kaldırın.

    Daha fazla bilgi için bkz: [profil oluşturma araçları](https://docs.microsoft.com/en-us/visualstudio/profiling/profiling-tools).

## <a name="disable-tools-and-extensions"></a>Araçlar ve uzantılar devre dışı bırak
Bazı araçlar ya da uzantıları performansı için devre dışı bırakılmış olabilir.

> [!TIP]
> Performans sorunlarını genellikle, bir kerede tek uzantıları kapatmak kapatarak ve performans yeniden denetleme da ayırabilirsiniz.

### <a name="managed-language-services-roslyn"></a>Yönetilen dil Hizmetleri (Roslyn)

[Büyük çözümler için başarım düşünceleri] Roslyn performans konuları hakkında daha fazla bilgi için bkz: (https://github.com/dotnet/roslyn/wiki/Performance-considerations-for-large-solutions).

- **Tam çözüm analizini devre dışı bırak**

    Visual Studio derleme çağırmadan önce hatalarla ilgili zengin bir deneyim sağlamak amacıyla, çözümün tamamında çözümlemesi gerçekleştirir. Bu özellik hataları mümkün olan en kısa sürede belirlemek kullanışlıdır. Ancak, çok büyük çözümler için bu özellik önemli bellek kaynaklarını tüketebilir. Bellek baskısı veya benzer sorunlar yaşıyorsanız, bu kaynakları boşaltmak için bu deneyimi devre dışı bırakabilirsiniz. Varsayılan olarak, bu seçenek etkin için Visual Basic ve C# için devre dışı.

    Devre dışı bırakmak için **tam çözüm analizini**, seçin **Araçlar > Seçenekler > Metin Düzenleyicisi >< Visual Basic veya C# >**. Ardından **Gelişmiş** ve seçimini **tam çözüm analizini etkinleştir**.

- **CodeLens devre dışı bırak**

    Visual Studio gerçekleştirir bir **tüm başvuruları Bul** görüntülendiği her yöntemini görev. CodeLens başvuru sayısı satır içi görüntüsünü gibi özellikler sağlar. İş, ayrı bir işlemde (örneğin, ServiceHub.RoslynCodeAnalysisService32) gerçekleştirilir. Düşük öncelikli olarak çalıştırılan olsa bile bu özellik çok büyük çözümlerde ya da kısıtlı kaynak sistemlerde performansı önemli etkiye sahiptir. Bu işlem yüksek CPU karşılaştığınız ya da (örneğin, 4 GB makine üzerinde büyük bir çözümde yüklenirken) bellek sorunları varsa, kaynakları boşaltmak için bu özelliği devre dışı bırakma deneyebilirsiniz.

    CodeLens devre dışı bırakmayı tercih **Araçlar > Seçenekler > Metin Düzenleyicisi > tüm diller > CodeLens**ve özellik seçimini kaldırın.

    Bu özellik, Visual Studio Professional ve Visual Studio Enterprise içinde kullanılabilir.

### <a name="other-tools-and-extensions"></a>Diğer araçları ve uzantıları

- **Uzantılarını devre dışı bırakma**

    Uzantıları yeni işlevsellik sağlayan veya varolan işlevlerini genişletmek için Visual Studio eklenen ek yazılım bileşenleridir. Uzantıları genellikle bir kaynak bellek kaynağı sorunları olabilir. Bellek kaynağı sorunla karşılaşıyorsanız, senaryo veya iş akışının nasıl etkilediğini görmek için aynı anda tek uzantıları devre dışı bırakmayı deneyin.

    Uzantılarını devre dışı bırakmak için şu adrese gidin **Araçlar | Uzantılar ve güncelleştirmeler**, belirli bir uzantıyı devre dışı bırakın.

- **XAML Tasarımcısı devre dışı bırak**

    XAML Tasarımcısı'nı varsayılan olarak etkindir, ancak yalnızca açarsanız kaynaklarını tüketir bir. XAML dosyası. XAML dosyaları ile çalışır, ancak Tasarımcı işlevselliği kullanmak istiyor musunuz, bazı Bellek boşaltmak için bu özelliği devre dışı bırakın.

    XAML Tasarımcısı devre dışı bırakmak için şu adrese gidin **Araçlar > Seçenekler > XAML Tasarımcısı > etkinleştirmek XAML Tasarımcısı**ve seçeneğin işaretini kaldırın.

- **İş yüklerini kaldırın**

    Visual Studio yükleyicisi, artık kullanılmayan iş yükleri kaldırmak için kullanabilirsiniz. Bu eylem paketler ve artık gerekmeyen derlemeleri atlayarak başlatma ve çalışma zamanı maliyet verimli hale getirebilirsiniz.

## <a name="force-a-garbage-collection"></a>Çöp toplama zorla

CLR bir atık toplama bellek yönetimi sistemi kullanır. Bu sistemde, bazen bellek artık gerekli olmayan nesneleri tarafından kullanılır. Bu durum geçici; Çöp toplayıcı, performans ve kaynak kullanım buluşsal yöntemler temel alarak bu belleği serbest bırakır. Visual Studio'da bir kısayol tuşu kullanarak kullanılmayan belleği toplamak için CLR zorlayabilirsiniz. Çöp koleksiyonu için bekleyen önemli miktarda ve çöp toplama zorlamak, Görev Yöneticisi'nde bırakma işleminin bellek kullanımını devenv.exe görmeniz gerekir. Bu yöntemi kullanmak nadiren gereklidir. (Tam bir yapı, hata ayıklama oturumu veya bir çözüm açık olay) pahalı bir işlem tamamlandıktan sonra ancak, ne kadar bellek gerçekten işlem tarafından kullanılıyor belirlemenize yardımcı olur. Visual Studio (yönetilen ve yerel) karma olduğundan, bazen yerel ayırıcısı ve atık toplayıcı sınırlı bellek kaynakları için rekabete giriyorsa için mümkündür. Yüksek bellek kullanımı koşullar altında çalıştırmak için atık toplayıcı zorla yardımcı olabilir.

Çöp toplama zorlamak için kısayol tuşu kullanın: **Ctrl + Alt + Shift + F12**, **Ctrl + Alt + Shift + F12** (Bu iki kez basın).

Çöp toplama güvenilir bir şekilde zorlama çalışma, Visual Studio geri bildirim aracı ile bir rapor dosyası bu davranış büyük olasılıkla bir hata olduğundan, senaryonuzun yapar.

CLR atık toplayıcı ayrıntılı bir açıklaması için bkz: [temel çöp koleksiyonu](https://msdn.microsoft.com/en-us/library/ee787088(v=vs.110).aspx).

## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio IDE](../ide/index.md)
