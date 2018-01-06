---
title: "Kod kapsamı çözümlemeyi özelleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f6337c35-acae-4c5f-b5d9-ac5ff687ef18
caps.latest.revision: "16"
ms.author: douge
manager: douge
ms.workload: multiple
ms.openlocfilehash: 2bbac737c6f5bbb3dbe99b0ceae2eb648bcf4295
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="customizing-code-coverage-analysis"></a>Kod Kapsamı Çözümlemeyi Özelleştirme
Varsayılan olarak, Visual Studio kod kapsamı aracı birim testleri sırasında yüklenen tüm çözüm derlemelerinin (.exe/.dll) çözümler. Çoğu zaman iyi çalıştığı için bu varsayılanı korumanız önerilir. Daha fazla bilgi için bkz: [kullanarak kod kapsamı belirleme ne kadar kodun için test](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md).  
  
 Kod kapsamı davranışını özelleştirmeden önce bazı alternatifleri düşünün:  
  
-   *Sınama kodu gelen kod kapsamı sonuçları hariç ve yalnızca uygulama kodunun dahil etmek istediğiniz.*  
  
     Ekleme `ExcludeFromCodeCoverage Attribute` test sınıfınıza.  
  
-   *Çözümüme parçası olmayan derlemeleri eklemek istiyorsunuz.*  
  
     Bu derlemeler için .pdb dosyalarını alın ve bunları derleme .dll dosyaları gibi aynı klasöre kopyalayın.  
  
 Kod kapsamı davranışını özelleştirmek için kopyalama [bu konunun sonundaki örnek](#sample) ve dosya uzantısı .runsettings kullanarak çözümünüze ekleyin. Kendi gereksinimlerinize ve ardından Düzenle **Test** menüsünde seçin **Test ayarları**, **Test Ayarları Seç** dosya. Bu konunun geri kalanını bu yordam daha ayrıntılı biçimde açıklar.  
  
## <a name="the-runsettings-file"></a>.runsettings dosyası  
 Gelişmiş kod kapsamı ayarları .runsettings dosyasında belirtilir. Bu, birim test etme araçları tarafından kullanılan yapılandırma dosyasıdır. Kopyaladığınız öneririz [bu konunun sonundaki örnek](#sample) ve kendi gereksinimlerinize uyacak şekilde düzenleyin.  
  
-   *Visual Studio 2010'da kullanılan .testsettings dosyasına ne oldu?*  
  
     Visual Studio 2010'da .testsettings dosyası MSTest çerçevesine dayalı birim testleri için geçerlidir. Visual Studio 2012'de test araçları yalnızca MSTest için değil aynı zamanda NUnit ve xUnit.net gibi diğer çerçeveler için de uygulanır. .testsettings dosyası bu işe yaramaz. .runsettings dosyası, tüm test çerçeveleri ile çalışacak şekilde test araçlarını özelleştirmek için tasarlanmıştır.  
  
 Kod kapsamını özelleştirmek için çözümünüze bir .runsettings dosyası eklemeniz gerekir:  
  
1.  Uzantısı ile bir çözüm öğesi olarak bir .xml dosyasına eklemek `.runsettings`:  
  
     Çözüm Gezgini'nde, çözüm kısayol menüsünden seçin **Ekle**, **yeni öğe**seçip **XML dosyası**. Dosya gibi biten bir adla kaydetme`CodeCoverage.runsettings`  
  
2.  Bu konunun sonundaki örnekte verilen içerik ekleyin ve sonra gereksinimleriniz için aşağıdaki bölümlerde açıklandığı şekilde özelleştirin.  
  
3.  Üzerinde **Test** menüsünde seçin **Test ayarları**, **Test ayarları dosyasını seçin** ve dosyayı seçin.  
  
4.  Şimdi çalıştırdığınızda **kod kapsamını çözümleme**, bu `.runsettings` dosya davranışını kontrol. Kod kapsamı yeniden çalıştırmalısınız unutmayın: testleri veya kodunuzun güncelleştirdiğinizde önceki kapsamı sonuçları ve kod renklendirme otomatik olarak gizli değil.  
  
5.  Özel ayarlar açın ve kapatın, seçimini kaldırın veya dosyayı seçmek için **Test**, **Test ayarlarını** menüsü.  
  
 ![Test ayarları menüsü özel ayarlar dosyasıyla](../test/media/codecoverage-settingsfile.png "CodeCoverage AyarlarDosyası")  
  
 Birim testlerinin diğer yönleri aynı .runsettings dosyasında yapılandırılabilir. Daha fazla bilgi için bkz: [Birim Test kodunuzu](../test/unit-test-your-code.md).  
  
### <a name="specifying-symbol-search-paths"></a>Simge arama yolu belirtme  
 Kod kapsamı bulunan derlemeler için simgeleri (.pdb dosyaları) gerektirir. Çözümünüz tarafından oluşturulmuş derlemeler için, simge dosyaları genellikle ikili dosyalarda bulunur ve kod kapsamı otomatik olarak çalışır. Ancak bazı durumlarda, kod kapsamı çözümlemenizde başvurulmuş derlemeleri eklemek isteyebilirsiniz. Bu gibi durumlarda .pdb dosyaları ikili bitişik olmayabilir, ancak .runsettings dosyasında simge arama yolu belirtebilirsiniz.  
  
```xml  
<SymbolSearchPaths>                
      <Path>\\mybuildshare\builds\ProjectX</Path>  
      <!--More paths if required-->  
</SymbolSearchPaths>  
  
```  
  
> [!WARNING]
>  Sembol çözünürlük özellikle pek çok derlemeyle uzak dosya konumu kullanırken zaman alabilir. Bu nedenle, ikili (.dll ve .exe) dosyaları ile aynı yerel konuma uzak .pdb dosyalarını kopyalamayı düşünün.  
  
### <a name="excluding-and-including"></a>Dahil ve hariç  
 Belirtilen derleme kod kapsamını çözümleme dışı bırakabilirsiniz. Örneğin:  
  
```minterastlib  
<ModulePaths>  
  <Exclude>  
   <ModulePath>Fabrikam.Math.UnitTest.dll</ModulePath>  
   <!-- Add more ModulePath nodes here. -->  
  </Exclude>  
</ModulePaths>  
```  
  
 Alternatif olarak, hangi derlemelerin dahil edileceğini belirtebilirsiniz. Bu yaklaşımın daha fazla derlemeleri çözümü eklediğinizde dezavantajı vardır, listeye eklemeyi unutmamalısınız:  
  
```minterastlib  
<ModulePaths>  
  <Include>  
   <ModulePath>Fabrikam.Math.dll</ModulePath>  
   <!-- Add more ModulePath nodes here. -->  
  </Include>  
</ModulePaths>  
```  
  
 Varsa `<Include>` kod kapsamı işleme yüklenir ve kendisi için tüm derlemeler (.dll ve .exe dosyaları) içerir sonra boştur **.pdb** dosyaları bulunabilir, bir yan tümcesinde eşleşen öğeleri dışında bir `<Exclude>` listesi.  
  
 `Include`önce işlenen `Exclude`.  
  
### <a name="regular-expressions"></a>Normal ifadeler  
 Dahil ve hariç düğümler normal ifadeler kullanır. Daha fazla bilgi için bkz: [Visual Studio'da normal ifadeler kullanarak](../ide/using-regular-expressions-in-visual-studio.md). Normal ifadeler joker karakterler ile aynı değildir. Özellikle:  
  
1.  **. \***  herhangi bir karakter dizesi ile eşleşir  
  
2.  **\\.** eşleşen bir nokta ".")  
  
3.  **\\( \\)** eşleşen ayraç "(")  
  
4.  **\\\\**bir dosya yolu ayırıcısı eşleşen "\\"  
  
5.  **^**başlatma dizesinin eşleşir  
  
6.  **$**Dize sonu ile eşleşir  
  
 Tüm eşlemeler büyük/küçük harf duyarsızdır.  
  
 Örneğin:  
  
```xml  
<ModulePaths>  
  <Include>  
    <!-- Include all loaded .dll assemblies (but not .exe assemblies): -->  
    <ModulePath>.*\.dll$</ModulePath>  
  </Include>  
  <Exclude>  
    <!-- But exclude some assemblies: -->  
    <ModulePath>.*\\Fabrikam\.MyTests1\.dll$</ModulePath>  
    <!-- Exclude all file paths that contain "Temp": -->  
    <ModulePath>.*Temp.*</ModulePath>   
  </Exclude>  
</ModulePaths>  
  
```  
  
> [!WARNING]
>  Atlatılamayan ve eşleşmeyen parantezler gibi normal ifadede bir hata varsa kod kapsamı çözümleme çalışmaz.  
  
### <a name="other-ways-to-include-or-exclude-elements"></a>Öğeleri içerecek veya dışlayacak diğer yollar  
 Bkz: [bu konunun sonundaki örnek](#sample) örnekleri için.  
  
-   `ModulePath`-Derlemeleri tarafından derleme dosya yolu belirtilmelidir.  
  
-   `CompanyName`-Şirket özniteliği tarafından derlemeleri eşleşir.  
  
-   `PublicKeyToken`-eşleşmeleri imzalı derlemeler tarafından ortak anahtar belirteci. Örneğin, tüm Visual Studio bileşenleri ve uzantıları eşleşen `<PublicKeyToken>^B03F5F7F11D50A3A$</PublicKeyToken>`.  
  
-   `Source`-öğeleri bunlar tanımlı kaynak dosya yolu adıyla eşleşir.  
  
-   `Attribute`-belirli bir öznitelik bağlı öğeleri eşleşir. Adın sonunda "Öznitelik" dahil özniteliğin tam adını belirtin.  
  
-   `Function`-tam adıyla yordamları, İşlevler veya yöntemler eşleşir.  
  
 **İşlev adı eşleştirme**  
  
 Normal ifadenizin tam ad alanı, sınıf adı, yöntemin adı ve parametre listesi de dahil olmak üzere, işlev adıyla eşleşmesi gerekir. Örneğin,  
  
-   C# veya Visual Basic:`Fabrikam.Math.LocalMath.SquareRoot(double)`  
  
-   C++:`Fabrikam::Math::LocalMath::SquareRoot(double)`  
  
```xml  
<Functions>  
  <Include>  
    <!-- Include methods in the Fabrikam namespace: -->  
    <Function>^Fabrikam\..*</Function>  
    <!-- Include all methods named EqualTo: -->  
    <Function>.*\.EqualTo\(.*</Function>  
  </Include>  
  <Exclude>  
    <!-- Exclude methods in a class or namespace named UnitTest: -->  
    <Function>.*\.UnitTest\..*</Function>  
  </Exclude>  
</Functions>  
  
```  
  
## <a name="how-to-specify-runsettings-files-while-running-tests"></a>Testleri çalıştırırken .runsettings dosyaları belirleme  
  
### <a name="to-customize-runsettings-in-visual-studio-tests"></a>Visual Studio testlerinde runsettings özelleştirmek için  
 Seçin **Test**, **Test ayarları**, **Test ayarları dosyasını seçin** ve .runsettings dosyasını seçin. Dosya, Test Ayarları menüsünde görünür ve seçebilir veya iptal edebilirsiniz. Kullandığınız her seçili olsa da, .runsettings dosyasını geçerlidir **kod kapsamını çözümleme**.  
  
### <a name="to-customize-run-settings-in-a-command-line-test"></a>Komut satırı testinde ayarları çalıştırmayı özelleştirmek için  
 Komut satırından testleri çalıştırmak için vstest.console.exe kullanın. Ayarlar dosyası, bu yardımcı programın bir parametresidir. Daha fazla bilgi için bkz: [kullanarak vstest.Console aracını komut satırından](/devops-test-docs/test/using-vstest-console-from-the-command-line).  
  
1.  Visual Studio Geliştirici Komut Satırını başlatın:  
  
     Windows **Başlat**, seçin **tüm programlar**, **Microsoft Visual Studio**, **Visual Studio Araçları**, **Geliştirici Komut İstemi**.  
  
2.  Çalıştır:  
  
     `vstest.console.exe MyTestAssembly.dll /EnableCodeCoverage /Settings:CodeCoverage.runsettings`  
  
### <a name="to-customize-run-settings-in-a-build-definition"></a>Bir yapı tanımında ayarları çalıştırmayı özelleştirmek için  
 Bir takım yapısından kod kapsama verisi elde edebilirsiniz.  
  
 ![Bir derleme tanımınız runsettings belirtme](../test/media/codecoverage-buildrunsettings.png "CodeCoverage buildRunsettings")  
  
1.  .runsettings dosyanızın işaretli olduğundan emin olun.  
  
2.  Takım Gezgini'nde Aç **derlemeler**ve ardından eklemek veya derleme tanımı düzenleyin.  
  
3.  Üzerinde **işlem** sayfasında **otomatikleştirilmiş testler**, **Test kaynak**, **çalıştırma ayarları**. Seçin, **.runsettings** dosya.  
  
    -   *Ancak **Test derleme** yerine görünür **Test kaynak**. Çalıştığımda ayarlamak **çalıştırma ayarları** alan yalnızca seçtiğim .testsettings dosyaları.*  
  
         Altında **otomatikleştirilmiş testler**seçin **Test derleme**ve seçin **[...]**  satırın sonundaki. İçinde **Ekle/Düzenle testi** iletişim kutusu, kümesi **Test Çalıştırıcısı** için **Visual Studio Test Çalıştırıcısı**.  
  
 Sonuçlar yapı raporunun özet bölümünde görünürdür.  
  
##  <a name="sample"></a>Örnek .runsettings dosyasını  
 Bu kodu kopyalayın ve kendi gereksinimlerinize göre düzenleyin. Bu varsayılan .runsettings dosyasıdır.  
  
 (.Runsettings dosyasını diğer kullanımlar için bkz: [.runsettings dosyasını kullanarak birim testlerini yapılandırma](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md).)  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<!-- File name extension must be .runsettings -->  
<RunSettings>  
  <DataCollectionRunSettings>  
    <DataCollectors>  
      <DataCollector friendlyName="Code Coverage" uri="datacollector://Microsoft/CodeCoverage/2.0" assemblyQualifiedName="Microsoft.VisualStudio.Coverage.DynamicCoverageDataCollector, Microsoft.VisualStudio.TraceCollector, Version=11.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a">  
        <Configuration>  
          <CodeCoverage>  
<!--  
Additional paths to search for .pdb (symbol) files. Symbols must be found for modules to be instrumented.  
If .pdb files are in the same folder as the .dll or .exe files, they are automatically found. Otherwise, specify them here.  
Note that searching for symbols increases code coverage runtime. So keep this small and local.  
-->   
<!--             
            <SymbolSearchPaths>                
                   <Path>C:\Users\User\Documents\Visual Studio 2012\Projects\ProjectX\bin\Debug</Path>  
                   <Path>\\mybuildshare\builds\ProjectX</Path>  
            </SymbolSearchPaths>  
-->  
  
<!--  
About include/exclude lists:  
Empty "Include" clauses imply all; empty "Exclude" clauses imply none.  
Each element in the list is a regular expression (ECMAScript syntax). See http://msdn.microsoft.com/library/2k3te2cs.aspx.  
An item must first match at least one entry in the include list to be included.  
Included items must then not match any entries in the exclude list to remain included.  
-->  
  
            <!-- Match assembly file paths: -->  
            <ModulePaths>  
              <Include>  
                <ModulePath>.*\.dll$</ModulePath>  
                <ModulePath>.*\.exe$</ModulePath>  
              </Include>  
              <Exclude>  
                <ModulePath>.*CPPUnitTestFramework.*</ModulePath>  
              </Exclude>  
            </ModulePaths>  
  
            <!-- Match fully qualified names of functions: -->  
            <!-- (Use "\." to delimit namespaces in C# or Visual Basic, "::" in C++.)  -->  
            <Functions>  
              <Exclude>  
                <Function>^Fabrikam\.UnitTest\..*</Function>           
                <Function>^std::.*</Function>  
                <Function>^ATL::.*</Function>  
                <Function>.*::__GetTestMethodInfo.*</Function>  
                <Function>^Microsoft::VisualStudio::CppCodeCoverageFramework::.*</Function>  
                <Function>^Microsoft::VisualStudio::CppUnitTestFramework::.*</Function>  
              </Exclude>  
            </Functions>  
  
            <!-- Match attributes on any code element: -->  
            <Attributes>  
              <Exclude>  
                <!-- Don't forget "Attribute" at the end of the name -->  
                <Attribute>^System\.Diagnostics\.DebuggerHiddenAttribute$</Attribute>  
                <Attribute>^System\.Diagnostics\.DebuggerNonUserCodeAttribute$</Attribute>  
                <Attribute>^System\.Runtime\.CompilerServices.CompilerGeneratedAttribute$</Attribute>  
                <Attribute>^System\.CodeDom\.Compiler.GeneratedCodeAttribute$</Attribute>  
                <Attribute>^System\.Diagnostics\.CodeAnalysis.ExcludeFromCodeCoverageAttribute$</Attribute>  
              </Exclude>  
            </Attributes>  
  
            <!-- Match the path of the source files in which each method is defined: -->  
            <Sources>  
              <Exclude>  
                <Source>.*\\atlmfc\\.*</Source>  
                <Source>.*\\vctools\\.*</Source>  
                <Source>.*\\public\\sdk\\.*</Source>  
                <Source>.*\\microsoft sdks\\.*</Source>  
                <Source>.*\\vc\\include\\.*</Source>  
              </Exclude>  
            </Sources>  
  
            <!-- Match the company name property in the assembly: -->  
            <CompanyNames>  
              <Exclude>  
                <CompanyName>.*microsoft.*</CompanyName>  
              </Exclude>  
            </CompanyNames>  
  
            <!-- Match the public key token of a signed assembly: -->  
            <PublicKeyTokens>  
              <!-- Exclude Visual Studio extensions: -->  
              <Exclude>  
                <PublicKeyToken>^B77A5C561934E089$</PublicKeyToken>  
                <PublicKeyToken>^B03F5F7F11D50A3A$</PublicKeyToken>  
                <PublicKeyToken>^31BF3856AD364E35$</PublicKeyToken>  
                <PublicKeyToken>^89845DCD8080CC91$</PublicKeyToken>  
                <PublicKeyToken>^71E9BCE111E9429C$</PublicKeyToken>  
                <PublicKeyToken>^8F50407C4E9E73B6$</PublicKeyToken>  
                <PublicKeyToken>^E361AF139669C375$</PublicKeyToken>  
              </Exclude>  
            </PublicKeyTokens>  
  
            <!-- We recommend you do not change the following values: -->  
            <UseVerifiableInstrumentation>True</UseVerifiableInstrumentation>  
            <AllowLowIntegrityProcesses>True</AllowLowIntegrityProcesses>  
            <CollectFromChildProcesses>True</CollectFromChildProcesses>  
            <CollectAspDotNet>False</CollectAspDotNet>  
  
          </CodeCoverage>  
        </Configuration>  
      </DataCollector>  
    </DataCollectors>  
  </DataCollectionRunSettings>  
</RunSettings>  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Test edildiğini belirlemek ne kadar kodun için kod kapsamını kullanma](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)   
 [Kodunuza Birim Testi Uygulama](../test/unit-test-your-code.md)
