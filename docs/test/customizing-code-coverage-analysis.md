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
ms.openlocfilehash: 7b48fc77dd88cf327050c0bf8ba893f8d4a626fa
ms.sourcegitcommit: 498e39e89a89ad7bf9dcb0617424fff999b1c3b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/21/2018
ms.locfileid: "36303009"
---
# <a name="customize-code-coverage-analysis"></a>Kod kapsamı çözümlemeyi özelleştirme

Varsayılan olarak, kod kapsamı birim testleri sırasında yüklenen tüm çözüm derlemeleri çözümler. İyi çoğu zaman çalıştığından, bu varsayılan davranışı kullanmanızı öneririz. Daha fazla bilgi için bkz: [ne kadar kodun test belirlemek için kod kapsamı kullanmak](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md).

Sınama kodu gelen kod kapsamı sonuçları hariç ve yalnızca uygulama kodu eklemek için Ekle <xref:System.Diagnostics.CodeAnalysis.ExcludeFromCodeCoverageAttribute> özniteliği test sınıfı.

Çözümünüzü parçası olmayan derlemeleri eklemek için elde *.pdb* bu derlemeler için dosyaları ve bunları derleme aynı klasöre kopyalayın *.dll* dosyaları.

## <a name="run-settings-file"></a>Çalışma ayarları dosyası

[Ayarları dosyasını çalıştırıp](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md) birim test araçları tarafından kullanılan yapılandırma dosyası. Gelişmiş kod kapsamı ayarları belirtilir bir *.runsettings* dosya.

Kod kapsamı özelleştirmek için aşağıdaki adımları izleyin:

1. Çalışma ayarları dosyası çözümünüze ekleyin. İçinde **Çözüm Gezgini**, çözümünüzü kısayol menüsünden seçin **Ekle** > **yeni öğe**seçip **XML dosyası**. Dosya gibi bir adla kaydetme *CodeCoverage.runsettings*.

1. Bu makalenin sonunda örnek dosyasından içerik ekleyebilir ve sonra gereksinimlerinizi izleyen bölümlerde açıklandığı gibi özelleştirebilirsiniz.

1. Üzerinde çalıştırma ayarları dosyasını seçmek için **Test** menüsünde seçin **Test ayarları** > **Test ayarları dosyasını seçin**. Komut satırından veya bir iş akışındaki yapı testleri çalıştırmak için bir çalışma ayarları dosyası belirtmek için bkz: [kullanarak birim testlerini yapılandırma bir *.runsettings* dosya](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md#specify-a-run-settings-file).

   Seçtiğinizde, **kod kapsamını çözümleme**, yapılandırma bilgilerini çalıştırma ayarlarını dosyasından okunur.

   > [!TIP]
   > Testleri veya kodunuzun güncelleştirdiğinizde önceki kod kapsamı sonuçları ve kod renklendirme otomatik olarak gizli değil.

Özel ayarlar açın ve kapatın, seçimini kaldırın veya dosyayı seçmek için **Test** > **Test ayarlarını** menüsü.

![Özel ayarlar dosyasıyla test ayarları menüsü](../test/media/codecoverage-settingsfile.png)

### <a name="specify-symbol-search-paths"></a>Sembol arama yollarını belirtin

Kod kapsamı gerektirir simge dosyaları (*.pdb* dosyaları) derlemeler için. Çözümünüz tarafından oluşturulmuş derlemeler için Sembol dosyalarının yanı sıra ikili dosyaları genellikle bulunması ve kod kapsamı otomatik olarak çalışır. Ancak bazı durumlarda, kod kapsamı çözümlemenizde başvurulmuş derlemeleri eklemek isteyebilirsiniz. Böyle durumlarda, *.pdb* dosyaları için ikili dosyaları bitişik olabilir, ancak simge arama yolu belirtebilirsiniz *.runsettings* dosya.

```xml
<SymbolSearchPaths>
      <Path>\\mybuildshare\builds\ProjectX</Path>
      <!--More paths if required-->
</SymbolSearchPaths>
```

> [!NOTE]
> Sembol çözümleme zaman alabilir özellikle bir uzak dosya konumu birçok derlemeleri ile kullanırken. Bu nedenle, kopyalama göz önünde bulundurun *.pdb* aynı yerel bir konum olarak ikili dosyaları (*.dll* ve *.exe*) dosyaları.

### <a name="exclude-and-include"></a>Dışla ve Ekle

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

Varsa **INCLUDE** kod kapsamı işleme yüklenen ve kendisi için tüm derlemeleri içerir sonra boştur *.pdb* dosyaları bulunabilir. Kod kapsamı yan tümcesinde eşleşen öğeleri içermez bir **hariç** listesi.

**Dahil** önce işlenen **hariç**.

### <a name="regular-expressions"></a>Normal ifadeler

Dahil ve hariç düğümler normal ifadeler kullanır. Daha fazla bilgi için bkz: [Visual Studio'da normal ifadeleri kullanma](../ide/using-regular-expressions-in-visual-studio.md). Normal ifadeler joker karakter ile aynı değil. Özellikle:

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
> Kod kapsamı çözümlemeyi atlanmayan veya eşleşmeyen parantez gibi normal bir ifade bir hata varsa çalıştırılmaz.

### <a name="other-ways-to-include-or-exclude-elements"></a>Öğeleri içerecek veya dışlayacak diğer yollar

- **ModulePath** -derleme dosyası yolu tarafından belirtilen derlemelere'ile eşleşir.

- **Şirket adı** -eşleşen derlemeleri tarafından **şirket** özniteliği.

- **PublicKeyToken** -eşleşmeleri imzalı derlemeler tarafından ortak anahtar belirteci.

- **Kaynak** -bunlar tanımlı kaynak dosya yolu adıyla eşleşen öğeleri.

- **Öznitelik** -belirli bir öznitelik bağlı öğeleri eşleşir. Özniteliğin tam adını belirtin ve adının sonunda "özniteliği" içerir.

- **İşlev** -tam adıyla yordamları, İşlevler veya yöntemler eşleşir. İşlev adı ile eşleşmesi için normal ifade işlevinin ad alanı, sınıf adı, yöntem adı ve parametre listesine dahil olmak üzere tam adı eşleşmelidir. Örneğin:

   ```csharp
   Fabrikam.Math.LocalMath.SquareRoot(double);
   ```

   ```cpp
   Fabrikam::Math::LocalMath::SquareRoot(double)
   ```

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

## <a name="sample-runsettings-file"></a>Örnek .runsettings dosyası

Bu kodu kopyalayın ve bunu gereksinimlerinize uyacak şekilde düzenleyin.

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

- [Çalışma ayarları dosyasını kullanarak birim testlerini yapılandırma](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md)
- [Ne kadar kodun test belirlemek için kod kapsamı kullanın](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)
- [Birim testi kodunuz](../test/unit-test-your-code.md)