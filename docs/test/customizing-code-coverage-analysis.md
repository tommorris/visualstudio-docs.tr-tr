---
title: Visual Studio'da kod kapsamı çözümlemeyi özelleştirme
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: c9b51137c6b66fe2895bcc0e70e3ffab8ebd637e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="customize-code-coverage-analysis"></a>Kod kapsamı çözümlemeyi özelleştirme

Varsayılan olarak, Visual Studio kod kapsamı aracı birim testleri sırasında yüklenen tüm çözüm derlemeleri çözümler. Çoğu zaman iyi çalıştığı için bu varsayılanı korumanız önerilir. Daha fazla bilgi için bkz: [kullanarak kod kapsamı belirleme ne kadar kodun için test](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md).

Kod kapsamı davranışını özelleştirmeden önce bazı alternatifleri düşünün:

- *Sınama kodu gelen kod kapsamı sonuçları hariç ve yalnızca uygulama kodunun dahil etmek istediğiniz.*

     Ekleme `ExcludeFromCodeCoverage Attribute` test sınıfınıza.

- *Çözümüme parçası olmayan derlemeleri eklemek istiyorsunuz.*

     Bu derlemeler için .pdb dosyalarını alın ve bunları derleme .dll dosyaları gibi aynı klasöre kopyalayın.

Kod kapsamı davranışını özelleştirmek için kopyalama [bu konunun sonundaki örnek](#sample) ve dosya uzantısını kullanarak çözümünüze ekleyin *.runsettings*. Kendi gereksinimlerinize ve ardından Düzenle **Test** menüsünde seçin **Test ayarları**, **Test Ayarları Seç** dosya. Bu makalenin sonraki bölümlerinde, bu yordamı daha ayrıntılı açıklanır.

## <a name="the-run-settings-file"></a>Çalışma ayarları dosyası

Gelişmiş kod kapsamı ayarları belirtilir bir *.runsettings* dosya. Çalışma ayarları, birim sınama araçları tarafından kullanılan yapılandırma dosyasını dosyasıdır. Kopyaladığınız öneririz [bu konunun sonundaki örnek](#sample) ve kendi gereksinimlerinize uyacak şekilde düzenleyin.

Kod kapsamı özelleştirmek için bir çalışma ayarları dosyası çözümünüze ekleyin:

1. Uzantısı ile bir çözüm öğesi olarak bir .xml dosyasına eklemek *.runsettings*:

     Çözüm Gezgini'nde, çözüm kısayol menüsünden seçin **Ekle** > **yeni öğe**seçip **XML dosyası**. Dosya gibi biten bir adla kaydetme *CodeCoverage.runsettings*.

2. Bu makalenin sonunda örneğindeki içeriği ekleyin ve sonra gereksinimlerinizi izleyen bölümlerde açıklandığı gibi özelleştirin.

3. Üzerinde **Test** menüsünde seçin **Test ayarları** > **Test ayarları dosyasını seçin** ve dosyayı seçin.

4. Şimdi çalıştırdığınızda **kod kapsamını çözümleme**, çalışma ayarları dosyası davranışını denetler. Kod kapsamı yeniden çalıştırmalısınız unutmayın. Testleri veya kodunuzun güncelleştirdiğinizde önceki kapsamı sonuçları ve kod renklendirme otomatik olarak gizli değil.

5. Özel ayarlar açın ve kapatın, seçimini kaldırın veya dosyayı seçmek için **Test** > **Test ayarlarını** menüsü.

 ![Özel ayarlar dosyasıyla test ayarları menüsü](../test/media/codecoverage-settingsfile.png)

Birim testleri diğer yönlerini aynı çalışma ayarları dosyasında yapılandırılabilir. Daha fazla bilgi için bkz: [Birim Test kodunuzu](../test/unit-test-your-code.md).

### <a name="specifying-symbol-search-paths"></a>Simge arama yolu belirtme

Kod kapsamı bulunan derlemeler için simgeleri (.pdb dosyaları) gerektirir. Çözümünüz tarafından oluşturulmuş derlemeler için Sembol dosyalarının yanı sıra ikili dosyaları genellikle bulunması ve kod kapsamı otomatik olarak çalışır. Ancak bazı durumlarda, kod kapsamı çözümlemenizde başvurulmuş derlemeleri eklemek isteyebilirsiniz. Bu gibi durumlarda .pdb dosyaları ikili bitişik olmayabilir, ancak .runsettings dosyasında simge arama yolu belirtebilirsiniz.

```xml
<SymbolSearchPaths>
      <Path>\\mybuildshare\builds\ProjectX</Path>
      <!--More paths if required-->
</SymbolSearchPaths>
```

> [!WARNING]
> Sembol çözümleme zaman alabilir özellikle bir uzak dosya konumu birçok derlemeleri ile kullanırken. Bu nedenle, ikili (.dll ve .exe) dosyaları ile aynı yerel konuma uzak .pdb dosyalarını kopyalamayı düşünün.

### <a name="excluding-and-including"></a>Dahil ve hariç

Belirtilen derleme kod kapsamını çözümleme dışı bırakabilirsiniz. Örneğin:

```xml
<ModulePaths>
  <Exclude>
   <ModulePath>Fabrikam.Math.UnitTest.dll</ModulePath>
   <!-- Add more ModulePath nodes here. -->
  </Exclude>
</ModulePaths>
```

Alternatif olarak, hangi derlemelerin dahil edileceğini belirtebilirsiniz. Bu yaklaşımın daha fazla derlemeleri çözümü eklediğinizde dezavantajı vardır, listeye eklemeyi unutmamalısınız:

```xml
<ModulePaths>
  <Include>
   <ModulePath>Fabrikam.Math.dll</ModulePath>
   <!-- Add more ModulePath nodes here. -->
  </Include>
</ModulePaths>
```

Varsa `<Include>` kod kapsamı işleme, yüklenir ve .pdb dosyaları bulunabilir tüm derlemelerini içerir sonra boştur. Kod kapsamı yan tümcesinde eşleşen öğeleri içermez bir `<Exclude>` listesi.

`Include` önce işlenen `Exclude`.

### <a name="regular-expressions"></a>Normal ifadeler

Dahil ve hariç düğümler normal ifadeler kullanır. Daha fazla bilgi için bkz: [Visual Studio'da normal ifadeler kullanarak](../ide/using-regular-expressions-in-visual-studio.md). Normal ifadeler joker karakterler ile aynı değildir. Özellikle:

- **. \***  herhangi bir karakter dizesi ile eşleşir

- **\\.** eşleşen bir nokta ".")

- **\\( \\)** eşleşen ayraç "(")

- **\\\\** bir dosya yolu ayırıcısı eşleşen "\\"

- **^** başlatma dizesinin eşleşir

- **$** Dize sonu ile eşleşir

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
> Atlatılamayan ve eşleşmeyen parantezler gibi normal ifadede bir hata varsa kod kapsamı çözümleme çalışmaz.

### <a name="other-ways-to-include-or-exclude-elements"></a>Öğeleri içerecek veya dışlayacak diğer yollar

Bkz: [bu konunun sonundaki örnek](#sample) örnekleri için.

- `ModulePath` -Derlemeleri tarafından derleme dosya yolu belirtilmelidir.

- `CompanyName` -Şirket özniteliği tarafından derlemeleri eşleşir.

- `PublicKeyToken` -eşleşmeleri imzalı derlemeler tarafından ortak anahtar belirteci. Örneğin, tüm Visual Studio bileşenleri ve uzantıları eşleşen `<PublicKeyToken>^B03F5F7F11D50A3A$</PublicKeyToken>`.

- `Source` -öğeleri bunlar tanımlı kaynak dosya yolu adıyla eşleşir.

- `Attribute` -belirli bir öznitelik bağlı öğeleri eşleşir. Adın sonunda "Öznitelik" dahil özniteliğin tam adını belirtin.

- `Function` -tam adıyla yordamları, İşlevler veya yöntemler eşleşir.

**İşlev adı eşleştirme**

Normal ifade işlevinin ad alanı, sınıf adı, yöntem adı ve parametre listesine dahil olmak üzere tam adı eşleşmelidir. Örneğin,

- C# veya Visual Basic: `Fabrikam.Math.LocalMath.SquareRoot(double)`

- C++:  `Fabrikam::Math::LocalMath::SquareRoot(double)`

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

## <a name="how-to-specify-run-settings-files-while-running-tests"></a>Testleri çalıştırırken çalıştırma ayarlarını dosyaları belirtme

### <a name="to-customize-run-settings-in-visual-studio-tests"></a>Visual Studio testleri çalıştırma ayarlarını özelleştirmek için

Seçin **Test** > **Test ayarları** > **Test ayarları dosyasını seçin** seçip *.runsettings* dosya. Dosya, Test Ayarları menüsünde görünür ve seçebilir veya iptal edebilirsiniz. Kullandığınız her seçili olsa da, çalışma ayarları dosyanız geçerlidir **kod kapsamını çözümleme**.

### <a name="to-customize-run-settings-in-a-command-line-test"></a>Komut satırı test çalıştırma ayarlarını özelleştirmek için

Komut satırından testleri çalıştırmak için kullandığınız *vstest.console.exe*. Ayarlar dosyası, bu yardımcı programın bir parametresidir.

1. Visual Studio Geliştirici Komut Satırını başlatın:

    Windows **Başlat** menüsünde seçin **Visual Studio 2017** > **VS 2017 için geliştirici komut istemi**.

2. Şu komutu çalıştırın:

    `vstest.console.exe MyTestAssembly.dll /EnableCodeCoverage /Settings:CodeCoverage.runsettings`

### <a name="to-customize-run-settings-in-a-build-definition"></a>Bir yapı tanımında ayarları çalıştırmayı özelleştirmek için

Bir takım yapısından kod kapsama verisi elde edebilirsiniz.

![Bir derleme tanımınız runsettings belirtme](../test/media/codecoverage-buildrunsettings.png)

1. Çalışma ayarları dosyanız işaretli olduğundan emin olun.

2. Takım Gezgini'nde Aç **derlemeler**ve ardından eklemek veya derleme tanımı düzenleyin.

3. Üzerinde **işlem** sayfasında **otomatikleştirilmiş testler** > **Test kaynak** > **çalıştırma ayarları**. Seçin *.runsettings* dosya.

   > [!TIP]
   > Varsa **Test derleme** yerine görünür **Test kaynak**, ve yalnızca seçebilirsiniz *.testsettings* dosyaları, ayarlamak **Test Çalıştırıcısı** özelliği aşağıdaki gibi. Altında **otomatikleştirilmiş testler**seçin **Test derleme**ve ardından **[...]**  satırın sonundaki. İçinde **Ekle/Düzenle testi** iletişim kutusu, kümesi **Test Çalıştırıcısı** için **Visual Studio Test Çalıştırıcısı**.

Sonuçlar yapı raporunun özet bölümünde görünürdür.

##  <a name="sample"></a> Örnek .runsettings dosyasını

Bu kodu kopyalayın ve kendi gereksinimlerinize göre düzenleyin.

(Çalıştırma ayarları dosyası diğer kullanımlar için bkz: [çalıştırma ayarları dosyasını kullanarak birim testlerini yapılandırma](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md).)

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

## <a name="see-also"></a>Ayrıca bkz.

- [Ne Kadar Kodun Test Edildiğini Belirlemek için Kod Kapsamını Kullanma](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)
- [Kodunuza Birim Testi Uygulama](../test/unit-test-your-code.md)