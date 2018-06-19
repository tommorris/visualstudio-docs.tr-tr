---
title: HLSL gölgelendirici hata ayıklayıcısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.graphics.shaderviewer
ms.assetid: 4ccec541-3c49-42bd-972a-686eb3a88fbc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 30f7bc86de6f94a328fa51f499985944e3e10258
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31482080"
---
# <a name="hlsl-shader-debugger"></a>HLSL Gölgelendirici Hata Ayıklayıcısı
HLSL Hata Ayıklayıcısı'ndaki Visual Studio grafik Çözümleyicisi HLSL gölgelendirici kodunuzu uygulamanızı gerçek koşullarda nasıl çalıştığını anlamanıza yardımcı olur.  
  
 HLSL hata ayıklayıcısı şudur:  
  
 ![HLSL hata ayıklama kullanarak izleyin ve yığın windows çağırın. ] (media/gfx_diag_demo_hlsl_debugger_orientation.png "gfx_diag_demo_hlsl_debugger_orientation")  
  
## <a name="understanding-the-hlsl-debugger"></a>HLSL hata ayıklayıcısını anlama  
 HLSL hata ayıklayıcısı, gölgelendirici kodunuzda ortaya çıkan sorunları anlamanıza yardımcı olur. HLSL kodda hata ayıklama [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] diğer dillerde yazılmış hata ayıklama kodu benzer — Örneğin, C++, C# veya Visual Basic. Aynı diğer dillere hata ayıklaması yaparken olduğu gibi, değişkenlerin içeriğini inceleyebilir, kesim noktaları ayarlayabilir, kodda adım adım ilerleyebilir ve çağrı yığınına yaklaşabilirsiniz.  
  
 GPU iş parçacıkları yüzlerce üzerinde aynı anda gölgelendirici kod çalıştırarak yüksek performans elde etmek için ancak HLSL hata ayıklayıcısı bu bilgilerin tümünü anlamlı yardımcı olacak şekilde sunmak için diğer grafik Çözümleyicisi araçları ile birlikte çalışmak üzere tasarlanmıştır . Grafik Çözümleyicisi yakalanan çerçeveleri grafik günlüğe kaydedilen bilgileri kullanarak yeniden oluşturur; HLSL hata ayıklayıcısı gölgelendirici kod çalıştırırken GPU yürütme gerçek zamanlı izlemez. Grafik günlük çıktısı herhangi bir bölümünü yeniden oluşturmak için yeterli bilgi içerir ve grafik analiz sağladığından tam piksel ve bir hata oluştuğu olay yardımcı olacak araçlar sabitleme, HLSL hata ayıklayıcısı yalnızca tam gölgelendirici benzetimini yapmak sahip olduğundan İlgilendiğiniz iş parçacığı. Başka bir deyişle, gölgelendiricinin çalışması, iç çalışmalarının tam görünümde olduğu CPU üzerinde benzetilebilir. Bu da, HLSL hata ayıklayıcısına CPU benzeri bir hata ayıklama deneyimi kazandırır.  
  
 Ancak, HLSL hata ayıklayıcısı şu an için aşağıdaki bakımlardan sınırlıdır:  
  
-   HLSL hata ayıklayıcısı Düzenle ve devam et desteklemiyor, ancak, gölgelendiriciler değişiklikleri yapın ve sonuçları görmek için çerçeveyi yeniden oluşturun.  
  
-   Bir uygulamanın ve gölgelendirici kodunun hatalarını aynı anda ayıklamak mümkün değildir. Ancak, bunlar arasında geçiş yapabilirsiniz.  
  
-   İzle penceresine değişkenler ve kayıtlar ekleyebilirsiniz, ancak ifadeler desteklenmez.  
  
 Yine de, HLSL hata ayıklayıcısı başka bir yöntemle sağlanabilecek olandan daha iyi ve daha CPU benzeri bir hata ayıklama deneyimi sağlar.  
  
## <a name="hlsl-shader-edit--apply"></a>HLSL gölgelendirici Uygula & Düzenle  
 HLSL gölgelendirici hata ayıklayıcısı Düzenle ve devam et CPU hata ayıklayıcı GPU yürütme modeli gölgelendirici geri durumuna izin vermediği için yapan aynı şekilde desteklemiyor. Bunun yerine, HLSL hata ayıklayıcısı HLSL kaynak dosyaları düzenleyin ve ardından olanak tanıyan Uygula & Düzenle destekleyen **Uygula** değişikliklerinizin etkisini görmek için çerçeveyi yeniden oluşturmak için. Değiştirilen gölgelendirici kodunuzu projenizin özgün HLSL kaynak dosyasını bütünlüğünü korumak için ayrı bir dosyada depolanır, ancak yaptığınız değişikliklerle memnun kaldığınızda seçebileceğiniz **kopyalayın...**  değişiklikleri projenize kopyalamak için. Bu özelliği kullanarak hızlı bir şekilde hataları içeren gölgelendirici kodu yinelemek ve pahalı yeniden oluşturma ve yakalama adımlarını iş akışı hata ayıklama, HLSL ortadan kaldırmak.  
  
## <a name="hlsl-disassembly"></a>HLSL ayrıştırma  
 HLSL gölgelendirici hata ayıklayıcısı HLSL gölgelendirici derleme HLSL kaynak kod listesi sağındaki listesini sağlar.  
  
## <a name="debugging-hlsl-code"></a>HLSL kodunda hata ayıklama  
 HLSL hata ayıklayıcısı ardışık düzen aşamaları veya piksel geçmişi windows erişebilir.  
  
#### <a name="to-start-the-hlsl-debugger-from-the-graphics-pipeline-stages-window"></a>HLSL hata ayıklayıcısını Grafik Ardışık Düzen Aşamaları penceresinden başlatmak için  
  
1.  İçinde **grafik ardışık düzen aşamaları** penceresi, hata ayıklamak istediğiniz gölgelendirici ile ilişkili olan ardışık düzen aşaması bulun.  
  
2.  Ardışık Düzen aşaması başlığın altında seçin **hata ayıklamayı Başlat**, küçük yeşil bir ok görünür.  
  
    > [!NOTE]
    >  HLSL hata ayıklayıcısına bu giriş noktası, karşılık gelen aşamanın yalnızca ilk gölgelendirici iş parçacığında (yani işlenen ilk köşe veya piksel) hata ayıklar. Piksel geçmişi bu gölgelendirici aşamaları başka bir iş parçacığı erişmek için kullanabilirsiniz.  
  
#### <a name="to-start-the-hlsl-debugger-from-the-graphics-pixel-history"></a>HLSL hata ayıklayıcısını Grafik Piksel Geçmişi'nden başlatmak için  
  
1.  İçinde **grafik piksel geçmişi** penceresi, hata ayıklamak istediğiniz gölgelendirici ile ilişkili çizim çağrısı genişletin. Her bir çizim çağrısı birden fazla temel öğeye karşılık gelebilir.  
  
2.  Çizim çağrısı ayrıntılarında, elde edilen renk katkısı gölgelendirici kodunda bir hata olduğunu gösteren bir temel öğeyi genişletin. Hata olduğunu ortaya koyan birden fazla temel öğe varsa, soruna tanı koymayı zorlaştırabilecek hata birikiminden kaçınmak için bu duruma işaret eden ilk temel öğeyi seçin.  
  
3.  İlkel ayrıntılarında hata ayıklama isteyip istemediğinizi seçin **köşe gölgelendirici** veya **piksel gölgelendirici**. Piksel gölgelendiricisinin doğru olduğu, ancak köşe gölgelendiricisinin kendisine yanlış sabitler aktarması nedeniyle yanlış renk katkısı ürettiğinden şüphelendiğiniz durumlarda, köşe gölgelendiricisi için hata ayıklama uygulayın. Aksi durumlarda piksel gölgelendiricisi için hata ayıklama uygulayın.  
  
     Seçilen gölgelendirici sağında seçin **hata ayıklamayı Başlat**, küçük yeşil bir ok görünür.  
  
    > [!NOTE]
    >  HLSL hata ayıklayıcısına bu giriş noktası, ya seçilen çizim çağrısına, temel öğeye ve seçtiğiniz piksele karşılık gelen piksel gölgelendiricisi iş parçacığına ya da sonuçları çizim çağrısı, temel öğe ve seçmiş olduğunuz piksel tarafından ilişkilendirilen köşe gölgelendiricisi iş parçacıklarına hata ayıklama uygular. Köşe gölgelendiricileri durumunda, köşe gölgelendiricisi ayrıntılarını genişleterek giriş noktasını belirli bir köşeye kadar iyice daraltabilirsiniz.  
  
 HLSL hata ayıklayıcısı gölgelendirici hatalarını ayıklamak üzere kullanma hakkında daha fazla örnekler için bkz [örnekler](graphics-diagnostics-examples.md) veya izlenecek yollar Ayrıca Bkz bölümündeki bağlanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: Köşe gölgeleme nedeniyle nesnelerin eksikliği](walkthrough-missing-objects-due-to-vertex-shading.md)   
 [İzlenecek yol: Gölgeleme nedeniyle hataları işleme hata ayıklama](walkthrough-debugging-rendering-errors-due-to-shading.md)   
 [İzlenecek Yol: Hesaplayıcı Gölgelendiricisinde Hata Ayıklamak İçin Grafik Tanılamayı Kullanma](walkthrough-using-graphics-diagnostics-to-debug-a-compute-shader.md)