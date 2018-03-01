---
title: "Intellitest ile kodunuz için birim testleri oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 2015-10-05
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.UnitTest.CreateIntelliTest
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 4ec391c698a53caa93796634ccf6fd8bf6bdcb41
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
---
# <a name="generate-unit-tests-for-your-code-with-intellitest"></a>Intellitest ile kodunuz için birim testleri oluşturma
Intellitest test verileri ve birim testleri dizisi oluşturmak için .NET kodunuzu araştırır. Koddaki her deyim için bir test giriş oluşturulan bu deyim yürütülecek. Servis talebi çözümleme kodda koşullu her dal için gerçekleştirilir. Örneğin, `if` deyimleri, onaylar ve özel durumlar oluşturan tüm işlemleri analiz edilir. Bu çözümleme yüksek kod kapsamı ile birim testleri oluşturmak, yöntemlerin her biri için parametreli birim testi için test verileri oluşturmak için kullanılır.  
  
 Intellitest çalıştırdığınızda, hangi testlerin başarısız oluyor ve bunları düzeltmek için tüm gerekli kodu eklemek kolayca görebilirsiniz. Hangi regresyon suite sağlamak amacıyla bir test projesi kaydetmek için oluşturulan testleri seçebilirsiniz. Kodunuzu değiştirmek gibi oluşturulan testleri kod değişikliklerinizin ile senkronize tutmaya Intellitest yeniden çalıştırın.  

## <a name="availability-and-extensions"></a>Kullanılabilirlik ve uzantıları

**Oluşturma Intellitest** ve **çalıştırmak Intellitest** menü komutları:

* Yalnızca Enterprise Edition, Visual Studio 2015'te kullanılabilir ve sonrasında bulunmaktadır.

* .NET Framework hedefleyen yalnızca C# kod destekler.

* Olan [Genişletilebilir](#extend-framework)ve verme testleri destek mstest'i, mstest'i V2, NUnit, xUnit biçimi.
  
* X64 desteklemeyen yapılandırma.  
  
## <a name="explore-use-intellitest-to-explore-your-code-and-generate-unit-tests"></a>Keşfedin: kullanım Intellitest kodunuzu keşfetmek ve birim testleri oluşturmak  
 Birim testleri oluşturmak için türlerinizi ortak olmalıdır. Aksi takdirde, [birim testleri oluşturma](#NoRun) bunları oluşturmadan önce ilk.  
  
1.  Çözümünüzü Visual Studio'da açın. Ardından, test etmek istediğiniz yöntemleri vardır sınıfı dosyasını açın.  
  
2.  Yöntemi, kodunuzda sağ tıklatın ve seçin **çalıştırmak Intellitest** , yönteminde kod için birim testleri oluşturmak için.  
  
     ![Sağ &#45; yönteminizi tıklatın birim testleri oluşturmak için](../test/media/runpex.png "RunPEX")  
  
     Intellitest kodunuz farklı girişle birçok kez çalışır. Her çalışma giriş test verileri ve elde edilen çıkış gösteren tablo ya da özel durum gösterilir.  
  
     ![Keşif sonuçları penceresi testleriyle görüntülenen](../test/media/pexexplorationresults.png "PEXExplorationResults")  
  
     Bir sınıfta tüm genel yöntemler için birim testleri oluşturmak için yalnızca belirli bir yöntemi yerine sınıfı sağ tıklatın. Ardından **çalıştırmak Intellitest**. Aşağı açılan liste araştırması Sonuçları penceresinde sınıfında birim testleri ve her bir yöntemi için giriş verileri görüntülemek için kullanın.  
  
     ![Listeden görüntülemek için test sonuçları seçin](../test/media/selectpextest.png "SelectPEXTest")  
  
     Geçişi, denetleyin testleri için sonuç sütunu bildirilen sonuçlarında beklentilerinizi kodunuz için aynı. Başarısız testleri için kodunuzu uygun şekilde düzeltin. Ardından düzeltmeler doğrulamak için Intellitest yeniden çalıştırın.  
  
## <a name="persist-save-the-unit-tests-as-a-regression-suite"></a>Sürdür: birim testlerini regresyon paketi Kaydet  
  
1.  Bir test projeye parametreli birim testini kaydetmek istediğiniz veri satırları seçin.  
  
     ![Testleri seçin; Sağ & # 45'i tıklatın ve Kaydet'i seçin;](../test/media/savepextests.png "SavePEXTests")  
  
     Oluşturuldu - parametreli birim testi her satır için karşılık gelen tek tek birim testleri kaydedilir ve test projesinin görüntüleyebilir. test projesi ve parametreli birim testi g.cs dosyasında karşılık gelen .cs dosyasında kaydedilir. Birim testleri çalıştırma ve Test Gezgini sonuçlarından için el ile oluşturulan birim testleri gibi görüntüleyin.  
  
     ![Birim testi görüntülemek için test yöntemi açık sınıf dosyasında](../test/media/testmethodpex.png "TestMethodPEX")  
  
     Gerekli tüm başvuruları test projesi için de eklenir.  
  
     Yöntemi kodu değişirse, birim testleri değişikliklerle eşitleme tutmaya Intellitest yeniden çalıştırın.  
  
## <a name="assist-use-intellitest-to-focus-code-exploration"></a>Yardımcısı: Kullanım Intellitest için odak kod araştırması  
  
1.  Daha karmaşık kodu varsa, Intellitest kodunuzu incelenmesi odaklanan ile yardımcı olur. Örneğin, bir parametre olarak arabirime sahip bir yöntemi olması ve arabirimi uygulayan birden fazla sınıf ise Intellitest bu sınıfların bulur ve bir uyarı bildirir.  
  
     Ne yapmak istiyorsunuz karar vermek için uyarıları görüntüleyin.  
  
     ![Uyarıları görüntülemek](../test/media/pexviewwarning.png "PEXViewWarning")  
  
2.  Kod araştırın ve test etmek istediğiniz anlamak sonra arabirimi sınamak üzere kullanmak için hangi sınıfların seçmek için uyarı düzeltebilirsiniz.  
  
     ![Sağ &#45;uyarıyı tıklatın ve düzeltme seçin;](../test/media/pexfixwarning.png "PEXFixWarning")  
  
     Bu seçenek PexAssemblyInfo.cs dosyasına eklenir.  
  
     `[assembly: PexUseType(typeof(Camera))]`  
  
3.  Şimdi parametreli birim testi oluşturmak ve test verileri yalnızca, sabit sınıfını kullanarak Intellitest yeniden çalıştırabilirsiniz.  
  
     ![Test verileri oluşturmak için Intellitest yeniden](../test/media/pexwarningsfixed.png "PEXWarningsFixed")  
  
## <a name="specify-use-intellitest-to-validate-correctness-properties-that-you-specify-in-code"></a>Belirtin: kullanım Intellitest kodda belirtme doğruluk özellikleri doğrulanacak  

Girişleri ve çıkışları doğrulamak için oluşturulan birim testleri istediğiniz genel ilişkisi belirtin. Bu özellikteki test yöntemi gibi görünüyor, ancak Evrensel quantified yöntemi kapsüllenir. Bu parametreli birim test olanak veren bir güvenlik yöntemidir ve yaptığınız tüm onayları Intellitest oluşturabilen tüm giriş için olası değerler tutmanız gerekir.  
  
##  <a name="QandALink"></a>SORU- CEVAP  
  
### <a name="q-can-you-use-intellitest-for-unmanaged-code"></a>S: yönetilmeyen kod için Intellitest kullanabilir miyim?  

**Y:** Hayır, Intellitest, yalnızca yönetilen kod ile çalışır.  
  
### <a name="q-when-does-a-generated-test-pass-or-fail"></a>S: zaman oluşturulan bir test geçti başarısız veya?  

**Y:** başka bir birim testi gibi hiçbir özel durum oluşursa geçirir. Tüm onaylama başarısız olursa veya test altındaki kodun işlenmeyen bir özel durum oluşturursa başarısız olur.  
  
 Bazı özel durumlar varsa, geçirilebilecek bir test varsa, bir test yöntemi, test sınıfı veya derleme, gereksinimlerinize göre aşağıdaki özniteliklerin düzeyi ayarlayabilirsiniz:  
  
-   **PexAllowedExceptionAttribute**  
  
-   **PexAllowedExceptionFromTypeAttribute**  
  
-   **PexAllowedExceptionFromTypeUnderTestAttribute**  
  
-   **PexAllowedExceptionFromAssemblyAttribute**  
  
### <a name="q-can-i-add-assumptions-to-the-parameterized-unit-test"></a>S: varsayımlar parametreli birim testine ekleyebilir miyim?  

**Y:** Evet, varsayımları için belirli bir yöntem birim testi için test veri gerekli değil belirtmek için kullanın. Kullanım <xref:Microsoft.Pex.Framework.PexAssume> varsayımlar eklemek için sınıfı. Örneğin, uzunlukları değişkeni şöyle null olmayan bir varsayım ekleyebilirsiniz.  
  
 `PexAssume.IsNotNull(lengths);`  
  
 Varsayılır ekleyip Intellitest yeniden artık ilgili değilse test verileri kaldırılır.  
  
### <a name="q-can-i-add-assertions-to-the-parameterized-unit-test"></a>S: parametreli birim testi için onayları ekleyebilir miyim?  

**Y:** Intellitest birim testleri çalıştığında deyiminizde sunduğundan aslında doğru olduğunu Evet, kontrol eder. Kullanım <xref:Microsoft.Pex.Framework.PexAssert> sınıf veya onayları eklemek için test çerçevesi ile birlikte gelen API onaylama. Örneğin, iki değişken eşit bir onaylama ekleyebilirsiniz.  
  
 `PexAssert.AreEqual(a, b);`  
  
 Bir onaylama ekleyip Intellitest yeniden değerinizi geçerli olduğundan ve değilse sınama başarısız kontrol eder.  
  
###  <a name="NoRun"></a>S: parametreli birim testleri çalıştırmadan önce Intellitest oluşturabilir miyim?  

**Y:** Evet, sınıf veya yöntemini sağ tıklayın ve ardından seçin **oluşturma Intellitest**.  
  
 ![Sağ &#45;Düzenleyici'yi tıklatın, oluşturma Intellitest seçin;](../test/media/pexcreateintellitest.png "PEXCreateIntelliTest")  
  
 Proje ve testleri nasıl adlandırıldığı değiştirmek veya testlerinizi oluşturmak için varsayılan biçimi kabul edin. Yeni test projesi oluşturma veya varolan bir projeye testlerinizi kaydedin.  
  
 ![Mstest'i varsayılan Intellitest oluşturun](../test/media/pexcreateintellitestmstest.png "PEXCreateIntelliTestMSTest")  

<a name="extend-framework"></a>  
### <a name="q-can-i-use-other-unit-test-frameworks-with-intellitest"></a>S: diğer birim test çerçevelerini ile Intellitest kullanabilir miyim?  

**Y:** Evet, şu adımları izleyin [bulma ve diğer çerçeveler yükleme](../test/install-third-party-unit-test-frameworks.md).
Test framework uzantıları, aynı zamanda Visual Studio Market'te bulunabilir kullanılabilir:

* [Test oluşturucuları için NUnit uzantısı](https://marketplace.visualstudio.com/items?itemName=NUnitDevelopers.TestGeneratorNUnitextension)
* [Test oluşturucuları için xUnit.net uzantısı](https://marketplace.visualstudio.com/items?itemName=BradWilson.xUnitnetTestExtensions)


Visual Studio'yu yeniden başlatın ve çözümünüzü yeniden sonra sınıf veya yöntemini sağ tıklayın ve ardından seçin **oluşturma Intellitest**. Yüklü framework buradan seçin:  
  
![Diğer birim testi çerçevesi için Intellitest seçin](../test/media/pexcreateintellitestextensions.png "PEXCreateIntelliTestExtensions")  
  
Karşılık gelen tek tek birim testleri oluşturmak için Intellitest çalıştırın. g.cs dosyaları.  

  
### <a name="q-can-i-learn-more-about-how-the-tests-are-generated"></a>S: testleri nasıl oluşturulduğu hakkında daha fazla bilgi?  

**Y:** bu üst düzey bir özeti almak için Evet'i, [blog gönderisi](http://blogs.msdn.com/b/visualstudioalm/archive/2015/07/05/intellitest-one-test-to-rule-them-all.aspx).
