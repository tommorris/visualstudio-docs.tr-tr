---
title: "Visual Studio 2010 birim testi projelerini yükseltme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1502b51-d6db-4894-9fbf-4a5723e4bb1a
caps.latest.revision: "8"
ms.author: douge
manager: douge
ms.openlocfilehash: 2e3e99bfad1ebf33f23c3b38189568935d0cedee
ms.sourcegitcommit: c0422a3d594ea5ae8fc03f1aee684b04f417522e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2017
---
# <a name="upgrade-visual-studio-2010-unit-test-projects"></a>Visual Studio 2010 birim testi projelerini yükseltme
[!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]Test projesi uyumluluğunu içeren [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] SP1 test projeleri. Örneğin, test ile oluşturulan projeleri [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] SP1 kullanarak açılabilir [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] yükseltme olmadan. Bu nedenle, ekibinizin kullanabilirsiniz [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] SP1 ve [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] aynı test projesi ile çalışmak için. Daha fazla bilgi için bkz: [testlerini Visual Studio 2010'dan yükseltme](http://msdn.microsoft.com/en-us/e9c8b7f6-bd72-448e-8edb-d090dcc5cf52).  
  
 [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]Birim testi için birkaç değişiklik getirir. Bu değişiklikler nedeniyle, Visual Studio'nun önceki sürümleri arasındaki uyumluluk sorunları anlamak önemlidir ve [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]. Birim testi değişiklikler arasında önemli bir değişiklik olan [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] bir birim testi proje şablonu dahil olmak üzere birden çok test proje şablonu içerir. Yeni birim testleri yeni birim testi proje şablonu eklenir. Birim testleri de kodlanmış UI test proje şablonu adlı başka bir yeni test projesi şablona dahil edilebilir. Yeni test proje şablonları hakkında daha fazla bilgi için bkz: [Visual Studio'nun önceki sürümleri yükseltme testlerden](http://msdn.microsoft.com/en-us/e9c8b7f6-bd72-448e-8edb-d090dcc5cf52). Yeni birim testi projelerini artık varsayılan olarak bir test ayarları dosyası içerir. Test ayarları dosyasını hariç tutarak, birim testleri performansını artırır. Uyumluluk için Visual Studio 2010 kullanarak oluşturduğunuz varolan test projelerinizi kullanmaya devam edebilirsiniz. Ancak, performans nedenleriyle test projesi için test ayarları dosyası belirli bir gereksiniminiz yoksa ilişkili test ayarları dosyası kaldırmanızı öneririz. Örneğin, dağıtılmış bir ortama birim testleri çalıştırma veya belirli Tanılama verileri toplayacak şekilde ihtiyacınız varsa test ayarları dosyasını korumak seçebilirsiniz. Yeni birim testi projesi şablonunu kullanarak benzer bir gereksinimi varsa veya kodlanmış UI testi proje şablonu el ile test ayarları dosyası için de ekleyebilirsiniz.  
  
> [!NOTE]
>  Var olan birim testleri, [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] SP1 test projeleri arasında sorunsuz çalışır [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] SP1 ve [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]. Birim testleri içeren bir Visual Studio 2010 test projesi açıldığında test proje dosyalarına değişiklik yapılmaz [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], ya da tam tersini.  
  
> [!CAUTION]
>  Visual Studio 2010 açamıyor C + +/ CLI proje bu hedefleri 11.0 araç takımı — diğer bir deyişle, Visual Studio 2012 veya sonraki bir sürümde oluşturulmuş bir projeyi. Bu kısıtlama geçerli tüm C + +/ CLI projeleri, değil yalnızca C + +/ CLI birim testi projelerini.  
  
> [!NOTE]
>  Vstest.console.exe komut satırından kullanarak yeni birim testleri çalıştırabilirsiniz. Vstest.console.exe kullanma hakkında daha fazla bilgi için bkz: [VSTest.Console.exe komut satırı seçenekleri](/devops-test-docs/test/vstest-console-exe-command-line-options), veya Yardım anahtarı kullanarak komutu çalıştırın: **vstest.console.exe /?**. MStest.exe kullanarak var olan birim testleri çalıştırmaya devam edebilirsiniz. Daha fazla bilgi için bkz: [otomatikleştirilmiş testleri mstest'i kullanarak komut satırından çalıştırma](/devops-test-docs/test/run-automated-tests-from-the-command-line-using-mstest) ve [MSTest.exe komut satırı seçenekleri](/devops-test-docs/test/mstest-exe-command-line-options).  
  
 Başka bir önemli yeni Test Gezgini değişikliktir. İçinde [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], Windows'un önceki Visual Studio sürümünden olabilir test windows bazıları, Test Görünümü penceresi gibi kullanım dışı bırakıldı. Test Gezgini daha iyi destek geliştiricileri ve kendi yazılım geliştirme uygulamalarını test etme birimi birleştirmek ekipleri için tasarlanmıştır. Daha fazla bilgi için bkz: [Test Gezgini ile birim testleri çalıştırma](../test/run-unit-tests-with-test-explorer.md).  
  
## <a name="compatibility-issues-between-visual-studio-2010-sp1-and-visual-studio-2012-or-later"></a>Visual Studio 2010 SP1 ve Visual Studio 2012 veya sonraki sürümünü arasındaki uyumluluk sorunları  
 Birim testleri Visual Studio 2010 SP1 arasında geçiş yaptığınızda dikkate etmeniz gereken bazı sorunlar şunlardır ve [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]:  
  
|Birim Test işlevi|Sorun|Çözüm|  
|-----------------------------|-----------|--------------|  
|Test listeleri (.vsmdi dosyaları) içinde kullanım dışı [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)].|Artık yeni test listeleri (.vsmdi dosyaları) oluşturma veya Visual Studio'dan test listeleri mümkün olmayacaktır. **İpucu:** Test kategorileri Microsoft Visual Studio'nun önceki sürümleri işlevinden test listeleri daha fazla esneklik sağlar. Mantıksal işleçler test kategorileri ile birlikte birden çok kategoriden testleri çalıştırmak için veya birden çok kategorilere ait Testleri Çalıştır testleri sınırlamak için kullanabilirsiniz. Ayrıca, test kategorilerini test yöntemlerinizi oluşturur ve test yöntemlerinizi oluşturduktan sonra test listeleri gerekmez eklemek kolaydır. Test kategorilerini kullanarak denetleyip kullanıma elinizde  **\<çözüm adı > .vsmdi** test listelerini tutar dosya. Daha fazla bilgi için bkz: [Grup bilgisayarınızı testler için Test kategorilerini tanımlama](/devops-test-docs/test/defining-test-categories-to-group-your-tests).|-Test listeleri kullanın varolan test projelerinizi uyumluluğu korumak için Visual Studio kullanarak .vsmdi dosyalarını düzenlemek açabilir.<br />-Visual Studio ile geçirilen test listelerinden çalıştıramazsınız rağmen hala onları çalıştırabilirsiniz mstest.exe komut satırından kullanma. Daha fazla bilgi için bkz: [otomatikleştirilmiş testleri mstest'i kullanarak komut satırından çalıştırma](/devops-test-docs/test/run-automated-tests-from-the-command-line-using-mstest)<br />-, Bir test listesi derleme tanımı'nda kullanıyorsanız, bunu kullanmaya devam edebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: yapılandırma ve çalıştırma zamanlanmış testleri uygulamanızı oluşturduktan sonra](http://msdn.microsoft.com/en-us/32acfeb1-b1aa-4afb-8cfe-cc209e6183fd) ve [yapı işleminizin testler](http://msdn.microsoft.com/Library/d05743a1-c5cf-447e-bed9-bed3cb595e38).|  
|Özel erişimciler dışıdır [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)].<br /><br /> Visual Studio'nun önceki sürümleri Publicize bir iç uygulama programlama arabirimleri (API) belirtin ve sırayla olur, testlerinizi içinde çağırabilirsiniz ortak karşılık gelen API oluşturmak için kullanabilir ürününüzü iç API çağırın. Kod oluşturma sonra test saplamalar oluşturun ve o saplama içindeki kod parçacığını oluşturmak için de kullanabilir.|Artık özel erişimciler oluşturmak mümkün olmayacaktır.|<ul><li>Visual Studio 2010 test projeleri derlemek ve iş [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]. Derleme çıktı uyarıları içerir.</li><li>İç API'ları sınamak gerekiyorsa, bu seçenekler vardır:<br /><br /> <ul><li>Kullanım <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PrivateObject> iç ve özel API kodunuzdaki erişirken yardımcı sınıfı. Bu Microsoft.VisualStudio.QualityTools.UnitTestFramework.dll bütünleştirilmiş kodunda bulunamadı.</li><li>İç veya özel API erişmek üzere kodunuzu yansıtacak şekilde doğrulayamazsınız bir yansıma framework oluşturun.</li><li>Erişmeye çalıştığınız kodu iç ise, API'leri kullanılarak erişim olabilir <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> test kodunuzu iç API'lerine erişimi yaşayabilirsiniz.</li></ul></li></ul>|  
|Test etkisi kaldırıldı|||  
|Test Gezgini TRX günlükleri ile çalıştırma sonuçları paylaşımı.||Komut satırı hem ekip TRX günlüklerini elde edebilirsiniz.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Taşıma, geçirme ve Visual Studio projelerini yükseltme](../porting/port-migrate-and-upgrade-visual-studio-projects.md)   
 [Kodunuza birim testi](../test/unit-test-your-code.md)   
 [Testleri Visual Studio'nun önceki sürümlerinden yükseltme](http://msdn.microsoft.com/en-us/e9c8b7f6-bd72-448e-8edb-d090dcc5cf52)   
 [Visual Studio 2010'dan kodlanmış UI testlerini yükseltme](../test/upgrading-coded-ui-tests-from-visual-studio-2010.md)
