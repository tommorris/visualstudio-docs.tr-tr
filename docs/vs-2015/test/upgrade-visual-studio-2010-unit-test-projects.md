---
title: Visual Studio 2010 birim testi projelerini yükseltme | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1502b51-d6db-4894-9fbf-4a5723e4bb1a
caps.latest.revision: 8
ms.author: gewarren
manager: douge
ms.openlocfilehash: e06a58e6015a99db83bf729d16196551c5126d12
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629596"
---
# <a name="upgrade-visual-studio-2010-unit-test-projects"></a>Visual Studio 2010 birim testi projelerini yükseltme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)] Test projesi uyumluluğunu içerir [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] SP1 test projeleri. Örneğin, test ile oluşturulan projeleri [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] SP1 kullanarak açılabilir [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)] olmadan yükseltme. Bu nedenle, takımınızın her ikisini birden kullanabilirsiniz [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] SP1 ve [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)] aynı test projesi ile çalışmak için. Daha fazla bilgi için [testlerini Visual Studio 2010'dan yükseltme](http://msdn.microsoft.com/en-us/e9c8b7f6-bd72-448e-8edb-d090dcc5cf52).  
  
 [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)] Birim testi için birkaç değişiklik getirir. Bu değişiklikler nedeniyle, Visual Studio'nun önceki sürümleri arasındaki uyumluluk sorunları anlamak önemlidir ve [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)]. Birim testi için değişiklikler arasında önemli bir değişiklik olan [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)] bir birim test projesi şablonunu dahil olmak üzere birden fazla test projesi şablonunu içerir. Yeni birim testleri, yeni birim test projesi şablonunu eklenir. Birim testleri, kodlanmış UI test projesi şablonunu adlı başka bir yeni test projesi şablonu da eklenebilir. Yeni test proje şablonları hakkında daha fazla bilgi için bkz. [Visual Studio'nun önceki sürümleri yükseltme testlerden](http://msdn.microsoft.com/en-us/e9c8b7f6-bd72-448e-8edb-d090dcc5cf52). Yeni birim testi projeleri, artık varsayılan olarak bir test ayarları dosyası içerir. Test ayarları dosyası tarafından hariç, birim testleriniz performansını artırır. Uyumluluk için Visual Studio 2010 kullanarak oluşturduğunuz mevcut test projelerinizi kullanmaya devam edebilirsiniz. Ancak, performansı artırmak için test projesi için test ayarları dosyası belirli bir gereksiniminiz olmadığı sürece ilişkilendirilmiş test ayarları dosyasını kaldırmanızı öneririz. Örneğin, dağıtılmış bir ortamda birim testlerinizi çalıştırmak veya belirli tanılama verilerini toplamak ihtiyacınız varsa, test ayarları dosyasını korumak seçebilirsiniz. Yeni birim testi proje şablonunu kullanarak benzer bir gereksinimi varsa, veya kodlanmış UI testi proje şablonunu el ile test ayarları dosyası için de ekleyebilirsiniz.  
  
> [!NOTE]
>  Mevcut birim testleri uygulamanızın [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] SP1 test projeleri arasında sorunsuz bir şekilde çalışır [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] SP1 ve [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)]. Birim testlerini içeren bir Visual Studio 2010 test projesi açıldığında test proje dosyaları için hiçbir değişiklik yapılmaz [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)], veya tam tersi.  
  
> [!CAUTION]
>  Visual Studio 2010 açamıyor C + +/ CLI bu hedefleri 11.0 araç takımı proje — diğer bir deyişle, Visual Studio 2012'de oluşturulan bir proje. Bu kısıtlamanın uygulandığı tüm C + +/ CLI projeleri, değil yalnızca C + +/ CLI birim testi projeleri.  
  
> [!NOTE]
>  Komut satırından vstest.console.exe kullanarak yeni birim testleri çalıştırabilirsiniz. Vstest.console.exe kullanımı hakkında daha fazla bilgi için bkz. [VSTest.Console.exe komut satırı seçenekleri](http://msdn.microsoft.com/library/52e1689d-b1a8-4589-bd98-99a55acd0a11), ya da Yardım anahtarını kullanarak komutu çalıştırın: **vstest.console.exe /?**. MStest.exe kullanarak mevcut birim testleri çalıştırmaya devam edebilirsiniz. Daha fazla bilgi için [otomatikleştirilmiş testleri mstest'i kullanarak komut satırından çalıştırma](http://msdn.microsoft.com/library/39b61ad0-0055-44b5-963f-25d8a6b51581) ve [MSTest.exe komut satırı seçenekleri](http://msdn.microsoft.com/library/8813ba7f-e790-4e92-9f91-7080508a1c36).  
  
 Başka bir önemli değişiklik Yeni Test Gezgini ' dir. İçinde [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)], bazı test windows aşina Visual Studio'nun önceki sürümden olabilir, Test Görünümü penceresi gibi kullanım dışı bırakıldı. Test Gezgini, daha iyi destek geliştiriciler ve birim testi içinde yazılım geliştirme yöntemleri bünyesine takımlar için tasarlanmıştır. Daha fazla bilgi için [Test Gezgini ile birim testleri çalıştırma](../test/run-unit-tests-with-test-explorer.md).  
  
## <a name="compatibility-issues-between-visual-studio-2010-sp1-and-visual-studio-2012"></a>Visual Studio 2010 SP1 ve Visual Studio 2012 arasındaki uyumluluk sorunları  
 Birim testlerini Visual Studio 2010 SP1 arasında geçiş yaptığınızda bilmeniz gereken bazı sorunları şunlardır ve [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)]:  
  
|Birim Test işlevleri|Sorun|Çözüm|  
|-----------------------------|-----------|--------------|  
|Test listeleri (.vsmdi dosyaları) bırakılmıştır [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)].|Yeni test listeleri (.vsmdi dosyaları) oluşturabilir veya Visual Studio'dan test listeleri artık olacaktır. **İpucu:** Test kategorileri Microsoft Visual Studio'nun önceki sürümlerindeki test listeleri işlevinden daha fazla esneklik sağlar. Mantıksal işleçler test kategorileri ile birden çok kategoriden testleri birlikte çalışmaya veya birden çok kategoriye ait testleri çalışan testleri sınırlamak için kullanabilirsiniz. Ayrıca, test kategorilerinin, test yöntemlerinizi oluşturduktan sonra test listelerinizi sürdürmenize gerek yoktur ve test yöntemleri oluşturduğunuzda eklenmesi kolaydır. Test kategorilerini kullanarak, iade etme ve kullanıma gerekmez  **\<çözüm adı > .vsmdi** test listelerini sürdüren dosya. Daha fazla bilgi için [Defining Test Categories to Group Your Tests](http://msdn.microsoft.com/library/2c26a648-f068-4d60-99b6-b9747b7bdbc9).|-Test listelerini kullanmak, var olan test projeleri ile uyumluluğu korumak için Visual Studio kullanarak .vsmdi dosyalarını düzenlemek hala mümkün.<br />-Visual Studio ile geçirilen test listelerinden çalıştıramazsınız karşın yine de bunları çalıştırabileceğiniz komut satırından mstest.exe kullanarak. Daha fazla bilgi için [otomatikleştirilmiş testleri mstest'i kullanarak komut satırından çalıştırma](http://msdn.microsoft.com/library/39b61ad0-0055-44b5-963f-25d8a6b51581)<br />-Test listesi yapı Tanımınızda kullandıysanız, onu kullanmaya devam edebilirsiniz. Daha fazla bilgi için [nasıl yapılır: yapılandırma ve çalıştırma zamanlanmış testleri uygulamanızı oluşturduktan sonra](http://msdn.microsoft.com/en-us/32acfeb1-b1aa-4afb-8cfe-cc209e6183fd) ve [yapı işleminizde testler](http://msdn.microsoft.com/library/d05743a1-c5cf-447e-bed9-bed3cb595e38).|  
|Özel erişimciler bırakılmıştır [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)].<br /><br /> Visual Studio'nun önceki sürümlerinde, bir iç uygulama programlama arabirimleri (API) belirtin ve sırayla gerekir, testlerinizi çağırabilirsiniz genel karşılığı API oluşturmak için toplanıldı kullanabilirsiniz ürününüzü iç API'lere çağırın. Test Saplamaları oluşturma ve bu saplama içinde kod parçacığı oluşturmak için kod oluşturma sonra kullanabilirsiniz.|Artık özel erişimciler oluşturmak mümkün olacaktır.|<ul><li>Visual Studio 2010 test projeleri derleme ve iş [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)]. Yapı çıkış uyarıları içerir.</li><li>İç API'leri test etmek yine de gerekliyse, bu seçenekler vardır:<br /><br /> <ul><li>Kullanım <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PrivateObject> sınıfı iç ve özel API'ler, kodunuzda erişirken yardımcı olmak için. Bu Microsoft.VisualStudio.QualityTools.UnitTestFramework.dll derlemede bulunur.</li><li>İç veya özel API'lere kodunuzu yansıtacak şekilde yükseltirseniz bir yansıma çerçevesi oluşturun.</li><li>Erişmeye çalıştığınız kodun iç ise API'lerini kullanarak erişebilir olabilir <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> test kodunuzu iç API'lerine erişimi olabilir.</li></ul></li></ul>|  
|Test etkisi kaldırıldı|||  
|Çalıştırma sonuçları Test Gezgini'nden TRX günlükleri aracılığıyla paylaşımını.||Komut satırı hem ekip TRX günlükleri elde edebilirsiniz.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Taşıma, geçirme ve Visual Studio projelerini yükseltme](../porting/porting-migrating-and-upgrading-visual-studio-projects.md)   
 [Kodunuza birim testi](../test/unit-test-your-code.md)   
 [Visual Studio'nun önceki sürümlerinden testleri yükseltme](http://msdn.microsoft.com/en-us/e9c8b7f6-bd72-448e-8edb-d090dcc5cf52)   
 [Visual Studio 2010'dan Kodlanmış UI Testlerini Yükseltme](../test/upgrading-coded-ui-tests-from-visual-studio-2010.md)