---
title: Birim testi kodunuzu | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio, unit tests
- unit tests, verifying code with
- testing code, automated tests
ms.assetid: c191de3e-3f3b-471e-b828-29ec24e80e2c
caps.latest.revision: "62"
ms.author: douge
manager: douge
ms.workload: multiple
ms.openlocfilehash: a60e3236769cbaf35a9b232629834a8b8d52a852
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="unit-test-your-code"></a>Kodunuza Birim Testi Uygulama
Birim testleri mantık hataları sınıflarda yöntemler aramak için hızlı bir şekilde geliştiriciler ve sınayıcılar vermek [!INCLUDE[csharp_current_short](../misc/includes/csharp_current_short_md.md)], [!INCLUDE[vb_current_short](../debugger/includes/vb_current_short_md.md)], ve [!INCLUDE[cpp_current_short](../misc/includes/cpp_current_short_md.md)] projeleri.  
  
 Birim testi araçları şunları içerir:  
  
1.  **Test Gezgini.** Test Gezgini, birim testleri çalıştırmanıza ve sonuçları görüntülemenize izin verir. Test Gezgini, üçüncü taraf çerçeve dahil, Gezgin için bağdaştırıcısı olan herhangi bir test çerçevesini kullanabilir.  
  
2.  **Microsoft birim testi çerçevesini yönetilen kod için.** Yönetilen kod için Microsoft birim testi çerçevesi Visual Studio ile yüklenir ve .NET kodunu test etmek için bir çerçeve sağlar.  
  
3.  **C++ için Microsoft birim test çerçevesi.** C++ için Microsoft birim testi çerçevesi Visual Studio ile yüklenir ve yerel kodu test etmek için bir çerçeve sağlar.  Visual Studio ile Google Test, Boost.Test ve CTest çerçeveleri kapsanmaktadır ve üçüncü taraf bağdaştırıcıları için ek sınama çerçeveleri kullanılabilir. Daha fazla bilgi için bkz: [C/C++ için birim testleri yazma](writing-unit-tests-for-c-cpp.md). 
  
4.  **Kapsamı araçları kodu.** Test Gezgini'nde bir tek komuttan birim testlerinizin çalıştıracağı ürün kodu miktarını belirleyebilirsiniz.  
  
5.  **Microsoft Fakes yalıtım çerçevesi.** Microsoft Fakes yalıtım çerçevesi, test edilen kodda bağımlılıklar oluşturan üretim ve sistem kodunun yerine geçecek sınıflar ve yöntemler oluşturabilir. Bir işlev için sahte temsilciler uygulayarak, bağımlılık nesnesinin davranışını ve çıkışını denetlersiniz.  
  
 Aynı zamanda [Intellitest](../test/generate-unit-tests-for-your-code-with-intellitest.md) test verileri ve birim testleri dizisi oluşturmak için .NET kodunuzu keşfetmek için. Koddaki her deyim için bir test giriş oluşturulan bu deyim yürütülecek. Servis talebi çözümleme kodda koşullu her dal için gerçekleştirilir.  
  
## <a name="key-tasks"></a>Ana görevler  
 Birim testlerini anlamaya ve oluşturmaya yardımcı olmaları için aşağıdaki konuları kullanın:  
  
|Görevler|İlişkili Konular|  
|-----------|-----------------------|  
|**Hızlı başlar ve izlenecek yollar:** birim Visual Studio'da kod örneklerinden testi öğrenmek için aşağıdaki konuları kullanın.|-   [Yönetilen kod için birim testleri izlenecek yol: Oluşturma ve çalıştırma](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md)<br />-   [Hızlı Başlangıç: Test Gezgini ile güdümlü geliştirme test etme](../test/quick-start-test-driven-development-with-test-explorer.md)<br />-   [Mevcut C++ uygulamalarına birim testleri ekleme](../test/unit-testing-existing-cpp-applications-with-test-explorer.md)<br />-   [Yerel kod Test Gezgini ile birim testi](http://msdn.microsoft.com/en-us/8a09d6d8-3613-49d8-9ffe-11375ac4736c)|  
|**Test Gezgini ile birim testi:** Test Gezgini daha üretken ve verimli birim testleri oluşturma nasıl yardımcı olabileceğini öğrenin.|-   [Birim testi temelleri](../test/unit-test-basics.md)<br />-   [Birim testi projesi oluşturma](../test/create-a-unit-test-project.md)<br />-   [Test Gezgini ile birim testleri çalıştırma](../test/run-unit-tests-with-test-explorer.md)<br />-   [Üçüncü şahıs birim test çerçevelerini yükleme](../test/install-third-party-unit-test-frameworks.md)<br />-   [Birim testleri Visual Studio 2010'dan yükseltme](http://msdn.microsoft.com/en-us/9bb75856-f68a-4de2-a084-b08a947a1172)|  
|**Birim testi yönetilen kodu:**|-   [Yönetilen kod için Microsoft Birim Test Çerçevesi ile .NET Framework için birim testleri yazma](../test/writing-unit-tests-for-the-dotnet-framework-with-the-microsoft-unit-test-framework-for-managed-code.md)|  
|**Birim testi C++ kodu**|-   [C++ için Microsoft birim testi çerçevesi ile C/C++ için birim testleri yazma](../test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp.md)|  
|**Yalıtmak birim testleri**|-   [Microsoft Fakes ile Test edilen kodu yalıtma](../test/isolating-code-under-test-with-microsoft-fakes.md)|  
|**Birim testleri kullanarak ne oranda projenizin kodun test edildiğini belirlemek için kod kapsamı kullanın:** kod kapsamı özelliği hakkında daha fazla bilgi [!INCLUDE[vsprvsts](../code-quality/includes/vsprvsts_md.md)] test araçları.|-   [Test edildiğini belirlemek ne kadar kodun için kod kapsamını kullanma](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)|  
|**Yük testleri için birim testleri kullanarak stres ve Performans Analizi gerçekleştirebilir:** bir yük testi oluşturma ve yalıtmak performans ve stres uygulamanızdaki sorunları gidermek için birim testleri ekleyin. **Not:** oluşturma ve yük testleri kullanarak Visual Studio Enterprise gerektirir.|-   [Oluşturma ve yük testlerini düzenleme](http://msdn.microsoft.com/en-us/e2985d15-60a7-4177-93b4-f986c2936337)<br />-   [Nasıl yapılır: Web performans testleri ve birim testleri bir yük testi senaryosuna ekleme](http://msdn.microsoft.com/en-us/03cc073e-9bdf-4530-ae46-504a51884594)<br />-   [Nasıl yapılır: bir Yük Testi Senaryosundan Web testleri ve birim testleri kaldırma](http://msdn.microsoft.com/en-us/3d6128d2-82b0-42fc-bda2-23a8aa03be07)|  
|**Kalite kapıları ayarlama ve:** kod kod kalitesini sağlamaya yardımcı olmak için iade önce testleri çalıştırmak zorlamak için kalite kapıları oluşturabilirsiniz.|-   [Kalite kapıları ayarlama ve uygulama](http://msdn.microsoft.com/Library/bdc5666e-6cf0-45b2-a0a1-133c3f61e852)|  
|**Birim test türü genişletmek:** Birim Test çerçevesi içinde olmayabilir testlerinizi işlevselliği ekleyebilirsiniz. Örneğin, bir testin normal kullanıcı olarak çalışıp çalışmayacağını belirten bir test özelliği ekleyebilirsiniz. Veya çerçeveyi, bir yönteme satır öznitelikleri eklemek ve bu satırda bulunan verileri testin içinde kullanmak üzere genişletebilirsiniz.|Birim testi çerçevesi genişletme örnek kod için aşağıdakilere bakın [Microsoft Web sitesini](http://go.microsoft.com/fwlink/?LinkId=185591).|  
|**Testi seçenekleri ayarlayın:** Örneğin, test sonuçları nerede depolanacağını belirtebilirsiniz.|[.runsettings dosyasını kullanarak birim testlerini yapılandırma](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md)|  
  
## <a name="related-tasks"></a>İlişkili görevler  
 [Microsoft Test Yöneticisi'nde test sonuçlarını gözden geçirme](http://msdn.microsoft.com/en-us/9fb3e429-78df-4fe2-89ed-0ad1db0738f4)  
  
 Test sonuçları ve nasıl görüntülendiği, kaydedildiği ve silindiği de dahil bunlarla çalışma yollarını açıklar.  
  
 [Microsoft Visual Studio'yu kullanarak sistem testleri çalıştırma](/devops-test-docs/test/running-automated-tests-using-microsoft-visual-studio)  
  
 Visual Studio kullanarak aksine kullanma hakkında bilgi için bağlantılar sağlar [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)] otomatikleştirilmiş testleri çalıştırmak için.  
  
## <a name="reference"></a>Başvuru  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting>  
 Öznitelikler, özel durumlar, bildirimler ve birim testini destekleyen diğer sınıfları sağlayan UnitTesting ad alanını açıklar.  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Web>  
 UnitTesting ad alanı sağlayarak genişletir ad alanı desteğini UnitTesting.Web açıklar [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] ve Web hizmeti birim testleri.  
  
## <a name="external-resources"></a>Dış kaynaklar  
  
### <a name="videos"></a>Videolar  
 [Kanal 9: Birim XAML kullanarak oluşturulan, UWP uygulamaları testi](http://go.microsoft.com/fwlink/?LinkId=226285)  
  
### <a name="forums"></a>Forumlar  
 [Visual Studio birim testi](http://go.microsoft.com/fwlink/?LinkId=224477)  
  
### <a name="guidance"></a>Kılavuz  
 [Visual Studio 2012 - bölüm 2 ile sürekli teslimat için test etme: birim testi: iç test etme](http://go.microsoft.com/fwlink/?LinkID=255188)  
  
### <a name="reference"></a>Başvuru  
 [Birim testleri için içerik dizini](http://go.microsoft.com/fwlink/?LinkID=254719)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kod kalitesini geliştirme](/visualstudio/test/improve-code-quality)   
 [Uygulamayı test etme](/devops-test-docs/test/test-apps-early-and-often)
