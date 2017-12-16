---
title: "Belirlemek ne kadar kodun için kod kapsamı test kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: code coverage
dev_langs:
- CSharp
- VB
- CPP
ms.author: douge
manager: douge
ms.openlocfilehash: 2d5c28f63dd432f2270ef8f3d91427b5196af139
ms.sourcegitcommit: 64c7682ec3a2cbea684e716803398d4278b591d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/15/2017
---
# <a name="using-code-coverage-to-determine-how-much-code-is-being-tested"></a>Ne Kadar Kodun Test Edildiğini Belirlemek için Kod Kapsamını Kullanma
Proje kodunuzun ne oranda aslında birim testleri gibi kodlanmış testler tarafından test edilen belirlemek için Visual Studio kod kapsamı özelliğini kullanabilirsiniz. Etkin hatalara karşı koruma sağlamak için testleriniz çalışmalı veya kodunuzun büyük bir kısmını 'kapsamalıdır'.  
  
 Kod Kapsamı Çözümleme (CLI) yönetilen ve yönetilmeyen (yerel) kod için uygulanabilir.  
  
 Test yöntemlerini Test Gezgini'ni kullanarak çalıştırdığınızda kod kapsamı bir seçenektir. Sonuçlar tablosu, her derleme sınıfı ve yöntemi içinde çalışan kod yüzdesini gösterir. Ayrıca, kaynak düzenleyici hangi kodun test edildiğini gösterir.  
  
 ![Kod kapsamı sonuçları renklendirme ile](../test/media/codecoverage1.png "CodeCoverage1")  
  
 **Gereksinimler**  
  
-   Visual Studio Enterprise  
  
### <a name="to-analyze-code-coverage-on-unit-tests-in-test-explorer"></a>Test Gezgini'ndeki birim testlerinde kod kapsamını analiz etmek için  
  
1.  Üzerinde **Test** menüsünde seçin **kod kapsamını çözümleme**.  
  
2.  Hangi satırların çalıştırmak görmek için seçin ![kod kapsamı renkleri simgesini göster](../test/media/codecoverage-showcoloringicon.png "CodeCoverage ShowColoringIcon")**kod kapsamı renkleri göster**.  
  
     Renkleri değiştirmek için ya da kalın yüz kullanmayı seçin **Araçları**, **seçenekleri**, **ortam**, **yazı tiplerini ve renkleri**, **Göster ayarlarını: metin düzenleyici**. Altında **öğeleri görüntüleme**, kapsamı öğeleri ayarlayın.  
  
3.  Sonuçlar düşük kapsamı gösterirse, hangi kod parçalarının uygulanmadığını araştırın ve bunları kapsamak için daha fazla test yazın. Geliştirme ekipleri için tipik olarak yaklaşık %80 kod kapsamı hedeflenir. Bazı durumlarda, düşük kapsam kabul edilebilir. Örneğin, düşük kapsamı bazı kodlar standart şablonundan oluşturulduğu kabul edilebilir.  
  
> [!TIP]
>  Doğru sonuçlar elde etmek için:  
>   
>  -   Bu derleyici optimizasyonunun kapalı olduğundan emin olun.  
>   
>      Yönetilmeyen (yerel) kod ile çalışıyorsanız, bir hata ayıklama yapısı kullanın.  
> -   Her derleme için .pdb (simge) dosyaları oluşturduğunuzdan emin olun.  
>   
>  Beklediğiniz sonuç alamazsanız bkz [kod kapsamı sorunlarını giderme](../test/troubleshooting-code-coverage.md). biçimindeki telefon numarasıdır. Kod kapsamı kodunuzu güncelleştirdikten sonra çalıştırmak unutmayın. Kodunuzu değiştirdikten sonra veya testleri çalıştırdığınızda kapsam sonuçları ve kod renklendirme otomatik olarak güncelleştirilmez.  
  
## <a name="reporting-in-blocks-or-lines"></a>Bloklarda veya satırlarda raporlama  
 Kod kapsamı sayılı *blokları*. Bir blok, tek bir giriş ve çıkış noktası kodu parçasıdır.  Programın denetim akışı blok bir test çalışması sırasında başarılı olursa, o blok kapsanan olarak sayılır. Blok kullanılma sayısının sonuç üzerinde etkisi yoktur.  
  
 Ayrıca seçerek satırları bakımından gösterilen sonuçları olabilir **Sütun Ekle/Kaldır** tablo üstbilgisindeki. Test, kodun herhangi bir satırında tüm kod bloklarına uygulanırsa, tek satır olarak sayılır. Uygulanan ve uygulanmayan bazı kod blokları bir satır içerdiğinde bu kısmi bir satır olarak sayılır.  
  
 Yüzdeler kaynak kodunda gördüğünüz parçaların boyutuyla daha yakından ilişkili olduğundan bazı kullanıcılar satırları saymayı tercih eder. Birçok satır kaplayan olsa bile uzun bir blok hesaplama tek bir blok olarak sayılacaktır.  
  
## <a name="managing-code-coverage-results"></a>Kod kapsama sonuçlarını yönetme  
 Kod Kapsama Sonuçları penceresi genellikle en son çalıştırma sonucunu gösterir. Sonuçlar test verilerini değiştirirseniz veya testlerinizin her defasında yalnızca bir kısmını çalıştırırsanız değişir.  
  
 Kod kapsamı penceresini önceki sonuçları veya diğer bilgisayarlarda elde edilen sonuçları görüntülemek için de kullanılabilir.  
  
 Birçok çalıştırmanın sonucunu örneğin farklı test verileri kullanan çalışmalardan birleştirebilirsiniz.  
  
-   **Önceki bir sonuç kümesini görüntülemek için**, aşağı açılan menüsünden seçin. Menü, yeni bir çözüm açtığınızda temizlenen geçici bir liste gösterir.  
  
-   **Önceki oturumdan sonuçlarını görüntülemek için**, seçin **alma kod kapsamı sonuçları**, çözümünüzdeki test sonucu klasöre gidin ve .coverage dosyasını içeri aktarın.  
  
     Karşılama renklendirme .coverage dosyası oluşturulurken kaynak kodu değişirse yanlış olabilir.  
  
-   **Sonuçları metin olarak okunabilir hale getirmek için**, seçin **kod kapsamı sonuçlarını dışarı aktar**. Bu, diğer araçlarla işlemek veya kolayca posta ile göndermek okunabilir .coveragexml dosyasını oluşturur.  
  
-   **Sonuçları başka birine göndermek için**, .coverage dosyası veya dışarı aktarılan .coveragexml dosya göndermek. Sonra dosyayı içe aktarabilirsiniz. Kaynak kodun aynı sürümü varsa, kapsam renklendirmeyi görebilirsiniz.  
  
## <a name="merging-results-from-different-runs"></a>Farklı çalışmalardan sonuçları birleştirme  
 Bazı durumlarda, test verilerine bağlı olarak kodunuzda farklı bloklar kullanılacaktır. Bu nedenle, farklı bir test çalışmasının sonuçlarını birleştirmek isteyebilirsiniz.  
  
 Örneğin, giriş "2" ile bir test çalıştırdığınızda, belirli bir işlevin %50'sinin kapsandığını bulun. Giriş "-2" ile ikinci kez test çalıştırdığınızda diğer %50'si işlev kapsamında görünüm renklendirme kapsamına bakın. Şimdi iki test çalışması sonuçlarını birleştirin ve işlevin %100 kapsamında rapor ve görünümü renklendirme kapsamını gösterin.  
  
 Kullanım ![kod kapsamı penceresinde birleştirme düğmesi için simge](../test/media/codecoverage-mergeicon.png "CodeCoverage MergeIcon")**kod kapsamı sonuçları birleştirme** Bunu yapmak için. Son çalışmaların veya alınan sonuçların herhangi bir bileşimini seçebilirsiniz. Dışa aktarılan sonuçları birleştirmek istiyorsanız, bunları önce almanız gerekir.  
  
 Kullanım **kod kapsamı sonuçlarını dışarı aktar** bir birleştirme işlemi sonuçlarını kaydetmek için.  
  
### <a name="limitations-in-merging"></a>Birleştirmede sınırlamalar  
  
-   Kodun farklı sürümlerinden kapsama verilerini birleştirirseniz, sonuçlar ayrı ayrı gösterilir, ancak birleştirilmez. Tam olarak birleştirilmiş sonuçlar almak için test verilerini değiştirerek kodun aynı yapısını kullanın.  
  
-   Dışa ve sonra içe alınmış sonuç dosyasını birleştirirseniz, sonuçları bloklarla değil yalnızca çizgilerle görüntüleyebilirsiniz. Kullanım **Sütun Ekle/Kaldır** satır verilerini göstermek için komutu.  
  
-   ASP.NET projesinin testlerinden sonuçları birleştirirseniz, birleştirilmiş değil ayrı testlerin sonuçları görüntülenir. Bu yalnızca ASP.NET yapılarına uygulanır: başka bir derleme için sonuçlar birleştirilecektir.  
  
## <a name="excluding-elements-from-the-code-coverage-results"></a>Kod kapsamı sonuçlarından öğeleri hariç tut  
 Örneğin kodu bir metin şablonundan oluşturulan tedarik puanlarını kodunuzda belirli öğeler dışında isteyebilirsiniz. Öznitelik Ekle `System.Diagnostics.CodeAnalysis.ExcludeFromCodeCoverage` aşağıdaki kod öğeleri hiçbirine: sınıf, yapı, yöntemi, özelliği, özellik ayarlayıcısı veya alıcı, olay. Hariç tutulan bir sınıfın türetilmiş sınıfları dışarıda tuttuğunu unutmayın.  
  
 Örneğin:  
  
```csharp  
  
using System.Diagnostics.CodeAnalysis;   
...  
public class ExampleClass1  
{   
    [ExcludeFromCodeCoverage]  
    void ExampleMethod() {...}  
  
    [ExcludeFromCodeCoverage] // exclude property  
    int ExampleProperty1   
    { get {...} set{...}}  
  
    int ExampleProperty2  
    {  
        get  
        {  
            ...  
        }  
        [ExcludeFromCodeCoverage] // exclude setter  
        set  
        {  
            ...  
        }  
    }  
  
}  
[ExcludeFromCodeCoverage]  
class ExampleClass2 { ... }  
  
```  
  
```vb  
Imports System.Diagnostics.CodeAnalysis  
  
Class ExampleClass1          
    <ExcludeFromCodeCoverage()>  
    Public Sub ExampleSub1()  
        ...  
    End Sub  
  
    ' Exclude property  
    < ExcludeFromCodeCoverage()>  
    Property ExampleProperty1 As Integer  
        ...  
    End Property  
  
    ' Exclude setter  
    Property ExampleProperty2 As Integer  
        Get  
            ...  
        End Get  
        <ExcludeFromCodeCoverage()>  
        Set(ByVal value As Integer)  
            ...  
        End Set  
    End Property  
End Class  
  
<ExcludeFromCodeCoverage()>  
Class ExampleClass2  
...  
End Class  
  
```  
  
```cpp  
// A .cpp file compiled as managed (CLI) code.  
using namespace System::Diagnostics::CodeAnalysis;  
...  
public ref class ExampleClass1  
{  
  public:  
    [ExcludeFromCodeCoverage]  
    void ExampleFunction1() { ... }  
  
    [ExcludeFromCodeCoverage]  
    property int ExampleProperty2 {...}  
  
    property int ExampleProperty2 {  
      int get() { ... }  
     [ExcludeFromCodeCoverage]  
      void set(int value) { ...  }  
   }  
  
}  
  
[ExcludeFromCodeCoverage]  
public ref class ExampleClass2  
{ ... }  
  
```  
  
### <a name="excluding-elements-in-native-c-code"></a>Yerel C++ kod öğeleri hariç  
 C++ koddaki yönetilmeyen (yerel) öğeleri dışlamak için:  
  
```cpp  
  
#include <CodeCoverage\CodeCoverage.h>  
...  
  
// Exclusions must be compiled as unmanaged (native):  
#pragma managed(push, off)  
  
// Exclude a particular function:  
ExcludeFromCodeCoverage(Exclusion1, L"MyNamespace::MyClass::MyFunction");  
  
// Exclude all the functions in a particular class:  
ExcludeFromCodeCoverage(Exclusion2, L"MyNamespace::MyClass2::*");  
  
// Exclude all the functions generated from a particular template:   
ExcludeFromCodeCoverage(Exclusion3, L"*::MyFunction<*>");  
  
// Exclude all the code from a particular .cpp file:  
ExcludeSourceFromCodeCoverage(Exclusion4, L"*\\unittest1.cpp");  
  
// After setting exclusions, restore the previous managed/unmanaged state:  
#pragma managed(pop)  
  
```  
  
 Aşağıdaki makroları kullanın:  
  
 `ExcludeFromCodeCoverage(`*ExclusionName* `, L"` *FunctionName*`");`  
  
 `ExcludeSourceFromCodeCoverage(`*ExclusionName* `, L"` *SourceFilePath*`");`  
  
-   *ExclusionName* benzersiz bir ad değil.  
  
-   *FunctionName* tam işlev adı. Joker karakterler içerebilir. Örneğin, bir sınıfın tüm işlevleri dışlamak için yazma`MyNamespace::MyClass::*`  
  
-   *SourceFilePath* yerel veya bir .cpp dosyasının UNC yoludur. Joker karakterler içerebilir. Aşağıdaki örnek, belirli bir dizindeki tüm dosyaları hariç tutar:`\\MyComputer\Source\UnitTests\*.cpp`  
  
-   `#include <CodeCoverage\CodeCoverage.h>`  
  
-   Herhangi bir ad alanı veya sınıf içindeki değil genel ad alanındaki dışlama makroları için çağrılar yerleşir.  
  
-   Dışlamaları birim test kod dosyasına veya uygulama kod dosyasına yerleştirebilirsiniz.  
  
-   Dışlamalar yönetilmeyen (yerel) kod derleyici seçeneği ayarlama veya kullanarak derlenmelidir `#pragma managed(off)`.  
  
> [!NOTE]
>  C + işlevler hariç tutulacak +/ CLI kod, öznitelik Uygula `[System::Diagnostics::CodeAnalysis::ExcludeFromCodeCoverage]` işlevi. Bu C# ile aynıdır.  
  
### <a name="including-or-excluding-additional-elements"></a>Dahil veya hariç ek öğeler  
 Kod kapsamı çözümlemesi yüklü olan ve bir .pdb dosyası .dll veya .exe dosyası ile aynı dizinde bulunan derlemeler üzerinde yapılır. Bu nedenle bazı durumlarda uygun .pdb dosyalarının kopyalarını alarak eklenen derleme kümesini genişletebilirsiniz.  
  
 .runsettings dosyasını yazarak seçilen kod kapsamı çözümleme derlemeleri ve öğeleri üzerinde daha fazla denetimle alıştırma yapabilirsiniz. Örneğin, kendi sınıfları için öznitelikler eklemek zorunda kalmadan belirli tür derlemeleri hariç tutabilirsiniz. Daha fazla bilgi için bkz: [kod kapsamı çözümlemeyi özelleştirme](../test/customizing-code-coverage-analysis.md).  
  
## <a name="analyzing-code-coverage-in-the-build-service"></a>Yapı hizmetindeki kod kapsamı çözümleme  
 Kodunuzda denetlediğinizde, testiniz diğer ekip üyelerinden gelen diğer tüm testlerle birlikte yapı sunucusunda çalışır. (Bu ayarlamış yüklemediyseniz, bkz: [yapı işleminizin testler](http://msdn.microsoft.com/Library/d05743a1-c5cf-447e-bed9-bed3cb595e38).) Tüm proje kapsamı en güncel ve kapsamlı resmini gösteren için kod kapsamı, Yapı hizmetini çözümlemek yararlıdır. Ayrıca, Otomatik Sistem testleri ve geliştirme makinelerde genellikle çalıştırma diğer kodlanmış testleri içerecektir.  
  
1.  Takım Gezgini'nde Aç **derlemeler**ve ardından eklemek veya derleme tanımı düzenleyin.  
  
2.  Üzerinde **işlem** sayfasında **otomatikleştirilmiş testler**, **Test kaynak**, **çalıştırma ayarları**. Ayarlama **çalıştırma ayarlarını dosya türü** için **kod kapsamı etkin**.  
  
     Birden fazla Test Kaynağı tanımı varsa, her biri için bu adımı yineleyin.  
  
    -   *Adında bir alan yok ancak **türü, çalıştırma ayarları dosyası**.*  
  
         Altında **otomatikleştirilmiş testler**seçin **Test derleme** ve üç nokta düğmesini seçin **[...]**  satırın sonundaki. İçinde **Ekle/Düzenle testi** iletişim kutusunda **Test Çalıştırıcısı**, seçin **Visual Studio Test Çalıştırıcısı**.  
  
 ![Derleme tanımı için kod kapsamı ayarlama](../test/media/codecoverage-plaincc.png "CodeCoverage plainCC")  
  
 Yapı çalıştıktan sonra kod kapsamı sonuçları test çalıştırmasına eklenir ve yapı özet olarak görünür.  
  
## <a name="analyzing-code-coverage-in-a-command-line"></a>Komut Satırında Kod Kapsamı Çözümleme  
 Komut satırından testleri çalıştırmak için vstest.console.exe kullanın. Kod kapsamı, bu yardımcı programın bir seçeneğidir. Daha fazla bilgi için bkz: [VSTest.Console.exe komut satırı seçenekleri](/devops-test-docs/test/vstest-console-exe-command-line-options).  
  
1.  Visual Studio Geliştirici Komut Satırını başlatın:  
  
     Windows **Başlat** menüsünde seçin **tüm programlar**, **Microsoft Visual Studio**, **Visual Studio Araçları**,  **Geliştirici komut istemi**.  
  
2.  Çalıştır:  
  
     `vstest.console.exe MyTestAssembly.dll /EnableCodeCoverage`  
  
## <a name="troubleshooting"></a>Sorun giderme  
 Kod kapsamı sonuçları görmüyorsanız bkz [kod kapsamı sorunlarını giderme](../test/troubleshooting-code-coverage.md).  
  
## <a name="external-resources"></a>Dış kaynaklar  
  
### <a name="guidance"></a>Kılavuz  
 [Visual Studio 2012 - bölüm 2 ile sürekli teslimat için test etme: birim testi: iç test etme](http://go.microsoft.com/fwlink/?LinkID=255188)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kod kapsamı çözümlemeyi özelleştirme](../test/customizing-code-coverage-analysis.md)   
 [Kod kapsamı sorunlarını giderme](../test/troubleshooting-code-coverage.md)   
 [Kodunuza Birim Testi Uygulama](../test/unit-test-your-code.md)
