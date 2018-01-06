---
title: "Visual Studio grafik Tanılama ile çalışmaya başlama | Microsoft Docs"
ms.custom: 
ms.date: 05/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59131181-1caa-4b7f-be4b-e84709634edf
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 36045b311a73af96df51553f9025a1de84c93b78
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="getting-started-with-visual-studio-graphics-diagnostics"></a>Visual Studio grafik Tanılama ile çalışmaya başlama
Grafik Tanılama'yı ilk kez kullanmak hazırlarsınız Bu bölümde, ardından Direct3D uygulamasından çerçeveleri yakalamak ve grafik Çözümleyicisi'nde incelemeniz.  
  
## <a name="requirements"></a>Gereksinimler  
 Visual Studio grafik Tanılama'yı kullanmak için Visual Studio Enterprise, Visual Studio Professional ya da Visual Studio Community kullanmanız gerekir.  Visual Studio Code dahil olmak üzere diğer sürümleri, bu özelliği içermiyor.
 
 [!INCLUDE[downloadvs](../includes/downloadvs_md.md)]  
  
### <a name="windows-10-prerequisites"></a>Windows 10 önkoşulları  
 İsteğe bağlı bir Windows özelliği *grafik araçları* grafik tanılama Windows 10 gerekli yakalama ve kayıttan yürütme altyapısı sağlar.  
  
 Grafik araçlarını yükleme hakkında daha fazla bilgi için bkz: [yükleme grafik araçları için Windows 10](#InstallGraphicsTools).  
  
### <a name="windows-81-prerequisites"></a>Windows 8.1 önkoşulları  
 Windows Yazılım Geliştirme Seti (SDK) Windows 8.1 için Windows 8.1 üzerindeki grafik tanılama gerektirdiği ve Windows 8.1 ve Windows 8 için geliştirmeyi destekler yakalama ve kayıttan yürütme altyapısı sağlar.  
  
 [Windows 8.1 için Windows Yazılım Geliştirme Seti (SDK) yükle](https://msdn.microsoft.com/en-us/windows/desktop/bg162891.aspx)  
  
 Windows 8.1 çalıştıran bir geliştirme makineden Windows 10 çalıştıran bir uzak kayıttan yürütme makinesini kullanmak için Windows 10 SDK geliştirme makinesine ve kayıttan yürütme makinesini isteğe bağlı grafik araçları özelliği yüklemeniz gerekir.  
  
##  <a name="InstallGraphicsTools"></a>Windows 10 için grafik araçlarını yükleme  
 Windows 10'da grafik tanılama altyapı isteğe bağlı bir adlı Windows özelliği tarafından sağlanan *grafik araçları*. Bu özellik, yakalama ve uygulama edilen hedefleri olup yakalanan bağımsız olarak grafik bilgilerini Windows 10 windows veya Direct3D'ın hangi sürümü kullanıyorsa önceki bir sürümünü oynatmak için gereklidir. Grafik araçları özelliği önceden yüklemeyi seçebilirsiniz; Aksi durumda, bir grafik Tanılama oturumu Visual Studio'dan yüklü isteğe bağlı ilk başlattığınızda olur.  
  
#### <a name="to-install-graphics-tools-for-windows-10"></a>Windows 10 için grafik araçları yüklemek için  
  
1.  Aramada, yazın **uygulamalar ve Özellikler** ve ardından açın **uygulamalar ve Özellikler** ayarlar.
  
3.  Sağ tarafındaki **uygulamalar ve Özellikler** iletişim kutusunda, seçin **isteğe bağlı özellikler yönetmek** (altında **uygulamalar ve Özellikler**).

    **İsteğe bağlı özellikler yönetmek** iletişim kutusu görüntülenir.
  
4.  İçinde **isteğe bağlı özellikler yönetmek** iletişim kutusunda, seçin **özellik ekleme**. Yükleyebileceğiniz isteğe bağlı özelliklerin bir listesi görüntülenir.  
  
5.  Seçin **grafik araçları** özellikleri listesinden ardından **yükleme**.  
  
 Windows 10 SDK'yı yüklediğinizde grafik araçları özelliği otomatik olarak yüklenir.  
  
> [!TIP]
>  İsteğe bağlı grafik araçları özelliği Windows 10 basit yakalama ve kayıttan yürütme işlevleri sağlar: komut satırı yakalama programı gibi **dxcap.exe**— desteği, test ve tanılama senaryoları kullanılabilir makineler, geliştirici araçları yüklü değil. Daha fazla bilgi için bkz: [yakalama komut satırı aracı](command-line-capture-tool.md) konu.  
  
## <a name="using-graphics-diagnostics-for-the-first-time"></a>İlk kez grafik tanılamayı kullanma  
 Gereksinim duyduğunuz her şeyi sahip olduğunuza göre grafik Tanılama'ı kullanmaya başlamak hazırsınız. Bu adımları izlemeniz yeterlidir.  
  
### <a name="1---create-a-direct3d-app"></a>1 - bir Direct3D uygulaması oluşturma  
 Grafik Tanılama, mükemmel keşfetmek için kendi Direct3D uygulamasını zaten aldıysanız! Aksi takdirde, aşağıdakilerden birini kullanın:

- **DirectX 11 uygulama (Evrensel Windows)** veya **DirectX 12 uygulama (Evrensel Windows)** proje şablonlarını Windows 10 için.
- **DirectX uygulama (Windows 8.1)** Windows 8.1 için proje şablonu.
- [Direct3D 12 UAP örnek](https://code.msdn.microsoft.com/Direct3D-12-UAP-Sample-ecb1779f) Windows 10 için.  
- [DirectX Mermer Labirent oyun örnek](https://code.msdn.microsoft.com/windowsapps/DirectX-Marble-Maze-Game-e4806345) Windows 8.1 için.  
  
 Geçmeden önce uygulama oluşturduğunuzdan emin olun.  
  
### <a name="2---start-a-graphics-diagnostics-session"></a>2 - bir grafik Tanılama oturumu Başlat  
 Artık, ilk grafik Tanılama oturumu başlatmak hazırsınız. Visual Studio'da ana menüde seçin **Debug, grafikler, grafik hata ayıklamayı Başlat**, veya yalnızca basın **Alt + F5**. Bu, uygulamanızın grafik tanılama altında başlatır ve Visual Studio Tanılama oturumu windows görüntüler.  
  
> [!IMPORTANT]
>  Uygulamanızı Windows 10 çalıştırıyorsanız ve isteğe bağlı bir grafik araçları özelliği henüz yüklemediniz, bunu şimdi yapın istenir. Windows 10 grafik tanılama kullanabilmeniz için önce yüklemeniz gerekir.  
  
### <a name="3---capture-frames"></a>3 - yakalama çerçeveler  
 Uygulamanızı başlar başlamaz çerçeveleri yakalamak hazırsınız.  
  
#### <a name="to-capture-single-frames"></a>Tek çerçeveleri yakalamak için  
  
-   Visual Studio'da, **yakalama çerçeve** Grafik araç çubuğu veya Tanılama oturumu penceresi düğmesinden. Veya, uygulamanızı odak varsa, yalnızca basın **Print Screen** klavyenizde anahtar.
  
#### <a name="to-capture-a-sequence-of-frames"></a>Bir dizi kare yakalamak için  
  
-   Tanılama oturumu penceresinde, Visual Studio'da ayarlayın **yakalamak için çerçeveler** sonra istediğiniz sırayla yakalamak için çerçeve sayısı için yukarıda açıklanan tek çerçeveleri yakalamak için yöntemlerden birini kullanarak dizisi yakalayın.  
  
     Tek çerçeveleri yeniden yakalamak için **yakalamak için çerçeveler** için *1*.  
  
 Çerçeve yakalamayı yalnızca bittiğinde uygulamayı çıkmak veya seçin **durdurmak** Tanılama oturumu penceresi ve Grafik araç çubuğu düğmesinden.  
  
### <a name="4---examine-captured-frames-in-the-graphics-analyzer"></a>4 - Grafik Çözümleyicisi yakalanan çerçeveleri inceleyin  
 Artık yalnızca yakalanan çerçeve incelemek hazırsınız. Bir çerçeve çözümleme başlatmak için tanılama oturumu penceresinden incelemek istediğiniz çerçeve kare sayısını seçin. Çerçevede açılır **grafik Çözümleyicisi**, buradan Direct3D uygulamanızı sorunları işleme izlemek için nasıl kullandığını incelemek için grafik tanılama araçlarını kullanın, veya kullanmak **çerçeve analizi** aracı kendi performansını anlayın.  
  
 Yanlış çerçeve Tanılama oturumu penceresinde seçili veya başka bir çerçeve incelemek isterseniz yeni bir grafik Çözümleyicisi gelen seçebilirsiniz. Üzerinde **işleme hedef** sekmesinde grafik günlük penceresinin işleme hedef görüntü altında genişletin **çerçeve listesi** ve incelemek için başka bir çerçeve'i seçin.  
  
 Grafik Çözümleyicisi araçları birlikte kullanma hakkında daha fazla bilgi için bkz: [örnekleri](graphics-diagnostics-examples.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Direct3D 12 grafik](http://msdn.microsoft.com/en-us/52094ae3-3b44-4689-9ee7-1ba1b3a779cb)