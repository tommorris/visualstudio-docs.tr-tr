---
redirect_url: /visualstudio/ide/visual-studio-ide
ms.openlocfilehash: 5f1fa39d6e6cde1664a8aaa34aed7cba726b1d56
ms.sourcegitcommit: 64c7682ec3a2cbea684e716803398d4278b591d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/15/2017
---
# <a name="get-started-with-visual-studio"></a>Visual Studio ile çalışmaya başlama
Visual Studio, uygulamaları geliştirmek için güçlü bir araçtır. Henüz yapmadıysanız, devam edin ve yükleyip [Visual Studio](https://www.visualstudio.com/vs/). Video bkz [Visual Studio - IDE'yi ayarı ile çalışmaya başlama](https://www.youtube.com/watch?v=xLCedknQkN0&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK&index=1) istediğiniz Visual Studio indirme ve şekilde yapılandırma hakkında daha fazla bilgi.

## <a name="visual-studio-tour"></a>Visual Studio turu
Visual Studio aracı windows, menüleri ve araç çubuklarını topluca tümleşik geliştirme ortamını IDE da bilinen bir grup vardır. Visual Studio IDE geliştirme görevleri gerçekleştirmenize yardımcı olur. Burada, büyük olasılıkla en sık kullanacağınız IDE öğeleri hızlı bir genel bakış verilmiştir.

### <a name="code-editor"></a>Kod Düzenleyicisi
Bir en yoğun olarak kullanılan aracı windows Visual Studio, burada yazma, görüntüleyebilir ve kodunuzu gidin budur.

![Kod Düzenleyicisi](../ide/media/VSIDE_CodeWindow.png)

Kod girerken, Kod düzenleyicisinde daha hızlı ve kolay bir şekilde yazma ve deyim tamamlama, söz dizimi renklendirme, eşleme modu ve daha fazlası gibi özellikler sağlayarak kodunuzu bulmanıza yardımcı olur. Video daha fazla bilgi için bkz [görsel düzenleme ve kodunuzu gezinme Studio ile-çalışmaya başlama](https://www.youtube.com/watch?v=4glwwioCVjA&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK&index=5)

Bazı çözüm türleri adlı windows içerebilir *forms*, Windows Presentation Foundation (WPF) formlarını, Windows forms, Genişletilebilir uygulama biçimlendirme dili (XAML) formlar ve diğerleri gibi. Bu durumda, bir görsel tasarımcı sürükle ve bırak denetimleri, düğmeler ve kullanıcıların uygulamanızı çalıştırdığınızda olmadığını ile etkileşim forma liste kutuları gibi olanak sağlayan bu alana görürsünüz.

### <a name="solution-explorer"></a>Çözüm Gezgini
Araç penceresi adlı **Çözüm Gezgini** tüm kod dosyaları listelenmektedir. Çözüm Gezgini, çözümler ve projeler gruplandırarak kodunuzu düzenlemenize yardımcı olur. Kalın yazı tipiyle proje adlı *başlangıç projesi*. Çözümünüzü başlattığınızda çalışan ilk kod değil. Başlangıç projesi değiştirebilirsiniz. Video bkz [Visual Studio - IDE yapı taşlarını ile çalışmaya başlama](https://www.youtube.com/watch?v=JHc3_gsCmZg&index=2&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK) daha fazla bilgi için.

![Çözüm Gezgini düğümleri daraltılmış](../ide/media/VSIDE_SolutionExplorer2_callouts.png)

 Projenin düğümünü genişletin, Çözüm Gezgini çözümler ve projeler yanı sıra, her projedeki tüm dosyalar listelenmektedir. Her proje kaynak kodu dosyaları ve görüntü veya kitaplıklar gibi kaynak dosyaları gibi bir veya daha fazla dosyalarını içerir.

![Çözüm Gezgini](../ide/media/VSIDE_SolutionExplorer3.png)

Dosyaları çözümler ve projeler özelliklerini görmek için seçin **özellikleri** komutu (sağ tıklatma) kısayol menüsünden veya seçin **görünüm, Özellikler penceresini** menüsünde.

![Özellik penceresi](../ide/media/VSIDE_SolutionExplorer4.png)

Bir çözüm ya da proje, ancak oluşturmak için kodlama başlamak için yok. Yalnızca hemen başlayın ve bir Git deposu ve hemen düzenleme başlangıç dosyaları gibi Visual Studio'da Aç kod dosyaları kopyalanamıyor. Çözüm Gezgini'nde dosyaları görünür ve get söz dizimi renklendirme, temel deyim tamamlama ve daha fazla bilgi, geleneksel çözümleri olduğu gibi. Bkz: [projeleri veya çözümler olmadan kod Visual Studio geliştirme](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md) daha fazla bilgi için.

### <a name="toolbar-and-menus"></a>Araç çubuğu ve menüleri
Projenizi çalıştırmak için yeni çözümler oluşturmasına, dosyaları ve daha fazlasını kaydetmek, Visual Studio araç çubuğu ve menü komutlarını kullanın. Kodunuzu hata ayıklama için çalıştırılmaya hazır olduğunda, örneğin, seçebilirsiniz **Başlat** araç veya düğmesine seçebilirsiniz **hata ayıklama, hata ayıklamayı Başlat** menüsünde. Yeni bir çözüm oluşturmak için seçtiğiniz **yeni proje** düğmesini veya seçin **dosya, yeni, proje** menü ve benzeri.

![Visual Studio araç çubuğu](../ide/media/VSIDE_SolutionExplorer5_callouts.png)

Araç çubuğu simgeleri ve menü komutlarını şu anda seçili öğe anlamı bağlamı bağlı olarak, değiştirebileceğinizi unutmayın. Neredeyse tüm komutlar, klavye komutları aracılığıyla yanı sıra fare aracılığıyla erişilebilir.

### <a name="team-explorer"></a>Ekip Gezgini
**Takım Gezgini** kaynak denetimi araçları gibi bağlanmanıza olanak sağlayan [Git](https://git-scm.com/) ve [Team Foundation sürüm denetimi (TFVC'yi)](https://www.visualstudio.com/en-us/docs/tfvc/overview) kodunuzu yerel olarak depolamak veya diğer kişilerle üzerinde barındırılan paylaşmak için hizmet. Görevleri ve daha fazlasını izlemek için de kullanabilirsiniz.

Videolarını görmek [Visual Studio - IDE yapı taşlarını ile çalışmaya başlama](https://www.youtube.com/watch?v=JHc3_gsCmZg&index=2&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK) ve [Visual Studio - Proje kaynak denetiminden açma ile çalışmaya başlama](https://www.youtube.com/watch?v=pc9vX_4RGV4&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK&index=3) daha fazla bilgi için.

![Ekip Gezgini](../ide/media/TeamExplorer.png)

### <a name="output-window"></a>Çıktı penceresi
**Çıkış** penceredir burada Visual Studio hata ayıklama ve hata iletileri, derleyici uyarıları, yayımlama durum iletilerini ve daha fazlası gibi kendi bildirimleri gönderir. Her ileti türü kendi sekmesi vardır.

![Çıktı penceresi](../ide/media/VSIDE_OutputWindow.png)

Hata ayıklama için çıkış penceresini kullanma hakkında daha fazla bilgi için bkz: [Visual Studio ile hata ayıklama sırasında çıktı penceresi](https://blogs.msdn.microsoft.com/visualstudioalm/2015/02/09/the-output-window-while-debugging-with-visual-studio/).

## <a name="first-steps"></a>İlk adımlar
- **Büyük resim Al** - Visual Studio'da bulunan önemli özelliklerin çoğunu özetini almak için bir tura katılın! Bkz: [Visual Studio IDE özelliği Turu](../ide/visual-studio-ide.md).
- **Kurulum** - indirin ve Visual Studio yükleme, bkz: hakkında bilgi almak için [yükleme Visual Studio 2017](../install/install-visual-studio.md).
- **Temel** - Visual Studio nasıl çalıştığı hakkında daha fazla bilgi için bkz: [alma başlatıldı geliştirme ile Visual Studio](../ide/get-started-developing-with-visual-studio.md).
- **Ayarları** - çalışmak için istediğiniz şekilde sığması için Visual Studio özelleştirmeyi öğrenin. Bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).
- **Öğreticiler** - bir öğreticide gibi ilerlemeyi nasıl Visual Studio'da kod geliştirme hakkında daha fazla bilgi için [Visual C# ve Visual Basic ile çalışmaya başlama](../ide/getting-started-with-visual-csharp-and-visual-basic.md) veya [VisualStudio'daC++ileçalışmayabaşlama](../ide/getting-started-with-cpp-in-visual-studio.md).
- **Videolar** - diğer özellikler ve Visual Studio yönlerini hakkında daha fazla bilgi için üzerinde videosuna göz atın [Microsoft Visual Studio kanal](https://www.youtube.com/user/VisualStudio/videos) YouTube'da, Visual Studio videolarının [Channel 9](https://channel9.msdn.com/Tags/visual+studio), veya [Microsoft sanal Akademi](https://mva.microsoft.com/product-training/visual-studio-courses#!jobf=Developer).

## <a name="access-cloud-based-resources"></a>Erişim bulut tabanlı kaynaklar
Bulut tabanlı kaynaklar uygulama ya da oyun kullanmak istiyorsanız, bunu ekleyerek yapabilirsiniz [Azure Hizmetleri](https://azure.microsoft.com/en-us/services/). .NET için Azure SDK'sını yükleyerek alabilirsiniz **Azure geliştirme** yeni Visual Studio Yükleyicisi'ni kullanarak iş yükü. Yüklenen paketler, SDK’nın 2.9.5 sürümüyle aynı özellik düzeyindedir. Visual Studio’nun bu sürümünde ve bundan sonraki tüm sürümlerinde, .NET için Azure SDK yalnızca Visual Studio Yükleyicisi’nden edinilebilir.

Azure geliştirme iş yükü yükledikten sonra yeni bir araç penceresi adlı Visual Studio'da kullanılabilir **Cloud Explorer**. Cloud Explorer gidin ve Azure varlıklar ve Visual Studio içinde kaynakları yönetmenize olanak sağlar. Belirli bir işlemi Azure portalında gerektiriyorsa, bulut Gezgini gitmeniz gerekir Azure portalında yere götüren bağlantılar sağlar.

![Bulut Gezgini](../ide/media/VSIDE_CloudExplorer.png)

Cloud Explorer kullanma hakkında daha fazla bilgi edinmek için [bulut Gezgini ile yönetme Azure kaynaklarını](https://azure.microsoft.com/en-us/documentation/articles/vs-azure-tools-resources-managing-with-cloud-explorer/).
Azure geliştirme iş yükü yükleme de size [Azure için Visual Studio Araçları](https://www.visualstudio.com/vs/azure-tools/) ilgili diğer araçları yanı sıra.

## <a name="tips-and-tricks"></a>İpuçları ve püf noktaları
Kısayollar faydalı ipuçları ve püf noktaları Visual Studio dışında daha fazla yararlanmak nasıl için aşağıdakilere bakın.
- [Başlarken ile Visual Studio - ipuçları ve püf noktaları](https://www.youtube.com/watch?v=vmXqGwn1Glk&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK&index=4)
- [Visual Studio için Üretkenlik İpuçları](../ide/productivity-tips-for-visual-studio.md)
- [Visual Studio ipuçları ve püf noktaları](https://channel9.msdn.com/events/TechEd/2013/DEV-B353)
- [C++ hata ayıklama ipuçları ve püf noktaları](https://channel9.msdn.com/Shows/Visual-Studio-Toolbox/C-Plus-Plus-Debugging-Tips-and-Tricks)
- [Visual Studio'nun en yararlı (ve kapatacağı) ipuçları [Scott Hanselman blog]](https://www.hanselman.com/blog/VisualStudiosMostUsefulAndUnderusedTips.aspx)
- [Visual Studio - yükleme Visual Studio uzantıları ile çalışmaya başlama](https://www.youtube.com/watch?v=MWLLQaknRZY&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK&index=7)
