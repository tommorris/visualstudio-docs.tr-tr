---
title: "Birim testleri kullanarak Visual Studio'da yapılandırma bir *.runsettings* dosya | Microsoft Docs"
ms.date: 02/28/2018
ms.technology: vs-devops-test
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: c0808635d0cd471f0fdaeb00e970ffde94a279c6
ms.sourcegitcommit: 873c0e1a31def013bcca1b0caa0eb0249de89bec
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2018
---
# <a name="configure-unit-tests-by-using-a-runsettings-file"></a>Kullanarak birim testlerini yapılandırma bir *.runsettings* dosyası

Birim testleri Visual Studio kullanarak yapılandırılabilir bir *.runsettings* dosya. Örneğin, üzerinde testler, .NET Framework sürümünü burada test sonuçlarını teslim edilir veya test sırasında toplanan verileri çalıştırmak dizini değiştirebilirsiniz.

> [!NOTE]
> Uzantı '.runsettings' kullandığınız sürece dosya adı önemli değildir.

Özel bir yapılandırma gerektirmeyen, gerekmeyen bir *.runsettings* dosya. En yaygın kullanımı bir *.runsettings* dosyasıdır özelleştirmek için [kod kapsamı çözümlemeyi](../test/customizing-code-coverage-analysis.md).

## <a name="customize-tests"></a>Testlerini özelleştirme

1. Visual Studio çözümünüz için bir XML dosyası ekleyin ve ona yeniden adlandırın *test.runsettings*.

1. Aşağıdaki örnek XML'den dosya içeriğini değiştirin ve gerektiği gibi özelleştirin.

1. Üzerinde **Test** menüsünde seçin **Test ayarları** > **Test ayarları dosyasını seçin**.

Birden fazla oluşturabileceğiniz *.runsettings* dosya, çözümünüz ve etkinleştirme veya bunları farklı zamanlarda kullanarak devre dışı **Test ayarlarını** menüsü.

![Çalışma ayarları dosyası etkinleştirme](../test/media/runsettings-1.png)

## <a name="example-runsettings-file"></a>Örnek *.runsettings* dosyası

Aşağıdadır tipik bir *.runsettings* dosya. Her değerin bir varsayılanı olduğundan, dosyanın her bir öğesi isteğe bağlıdır.

```xml
<?xml version="1.0" encoding="utf-8"?>
<RunSettings>
  <!-- Configurations that affect the Test Framework -->
  <RunConfiguration>
    <MaxCpuCount>1</MaxCpuCount>
    <!-- Path relative to solution directory -->
    <ResultsDirectory>.\TestResults</ResultsDirectory>

    <!-- x86 or x64
      - You can also change it from menu Test, Test Settings, Default Processor Architecture -->
    <TargetPlatform>x86</TargetPlatform>

    <!-- Framework35 | [Framework40] | Framework45 -->
    <TargetFrameworkVersion>Framework40</TargetFrameworkVersion>

    <!-- Path to Test Adapters -->
    <TestAdaptersPaths>%SystemDrive%\Temp\foo;%SystemDrive%\Temp\bar</TestAdaptersPaths>
  </RunConfiguration>

  <!-- Configurations for data collectors -->
  <DataCollectionRunSettings>
    <DataCollectors>
      <DataCollector friendlyName="Code Coverage" uri="datacollector://Microsoft/CodeCoverage/2.0" assemblyQualifiedName="Microsoft.VisualStudio.Coverage.DynamicCoverageDataCollector, Microsoft.VisualStudio.TraceCollector, Version=11.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a">
        <Configuration>
          <CodeCoverage>
            <ModulePaths>
              <Exclude>
                <ModulePath>.*CPPUnitTestFramework.*</ModulePath>
              </Exclude>
            </ModulePaths>

            <!-- We recommend you do not change the following values: -->
            <UseVerifiableInstrumentation>True</UseVerifiableInstrumentation>
            <AllowLowIntegrityProcesses>True</AllowLowIntegrityProcesses>
            <CollectFromChildProcesses>True</CollectFromChildProcesses>
            <CollectAspDotNet>False</CollectAspDotNet>

          </CodeCoverage>
        </Configuration>
      </DataCollector>

      <!--Video data collector is only available with Visual Studio 2017 version 15.5 and higher -->
      <DataCollector uri="datacollector://microsoft/VideoRecorder/1.0" assemblyQualifiedName="Microsoft.VisualStudio.TestTools.DataCollection.VideoRecorder.VideoRecorderDataCollector, Microsoft.VisualStudio.TestTools.DataCollection.VideoRecorder, Version=15.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" friendlyName="Screen and Voice Recorder">
      </DataCollector>

    </DataCollectors>
  </DataCollectionRunSettings>

  <!-- Parameters used by tests at runtime -->
  <TestRunParameters>
    <Parameter name="webAppUrl" value="http://localhost" />
    <Parameter name="webAppUserName" value="Admin" />
    <Parameter name="webAppPassword" value="Password" />
  </TestRunParameters>

  <!-- Adapter Specific sections -->

  <!-- MSTest adapter -->
  <MSTest>
    <MapInconclusiveToFailed>True</MapInconclusiveToFailed>
    <CaptureTraceOutput>false</CaptureTraceOutput>
    <DeleteDeploymentDirectoryAfterTestRunIsComplete>False</DeleteDeploymentDirectoryAfterTestRunIsComplete>
    <DeploymentEnabled>False</DeploymentEnabled>
    <AssemblyResolution>
      <Directory Path="D:\myfolder\bin\" includeSubDirectories="false"/>
    </AssemblyResolution>
  </MSTest>

</RunSettings>
```

*.Runsettings* dosyası yapılandırmak için kullanılan aynı zamanda [kod kapsamı çözümlemeyi](../test/customizing-code-coverage-analysis.md).

Bu makalenin sonraki bölümlerinde dosya içeriği açıklar.

## <a name="edit-your-runsettings-file"></a>Düzenleme, *.runsettings* dosyası

Öğelerini bölümlerde ayrıntılı bir *.runsettings* dosya.

### <a name="test-run-configuration"></a>Test çalıştırma yapılandırması

|Düğüm|Varsayılan|Değerler|
|----------|-------------|------------|
|`ResultsDirectory`||Test sonuçları yerleştirildiği dizin.|
|`TargetFrameworkVersion`|Framework40|Framework35, Framework40, Framework45<br /><br /> Bu ayar, bulmak ve testler yürütmek için kullanılan birim test çerçevesi hangi sürümü belirtir. Birim test projesinin yapı özelliklerinde belirttiğiniz .NET platformu sürümünden farklı olabilir.|
|`TargetPlatform`|x86|x86, x64|
|`TreatTestAdapterErrorsAsWarnings`|false|yanlış, doğru|
|`TestAdaptersPaths`||Bir veya birden çok yol TestAdapters bulunduğu dizine|
|`MaxCpuCount`|1.|Bu çalışan birim testleri zaman denetimleri paralel test yürütmesi derecesini ayarlama, makinede kullanılabilir çekirdekleri kullanılarak. Test yürütme altyapısı, her kullanılabilir çekirdek ayrı bir işlem olarak başlatır ve her çekirdek ile testleri çalıştırmak için bir kapsayıcı sağlar. Bir kapsayıcı, bir derleme, DLL veya ilgili yapı olabilir. Test kapsayıcısı zamanlama birimidir. Her kapsayıcısında testleri test çerçevesi göre çalıştırılır. Birçok kapsayıcıları varsa, daha sonra bir kapsayıcıda testleri çalıştırma bitiş işlerken kendisine sonraki kullanılabilir kapsayıcı verilir.<br /><br /> MaxCpuCount olabilir:<br /><br /> 1 burada n < = n < = çekirdek sayısı: n işlemlerinin tasarrufundadır başlatılacak<br /><br /> n, burada n herhangi bir değer =: başlatılan işlem sayısı kadar kullanılabilir çekirdeğe makinedeki kadar olacaktır|

### <a name="diagnostic-data-adapters-data-collectors"></a>Tanılama Veri Bağdaştırıcıları (Veri Toplayıcıları)

`DataCollectors` Öğesi tanılama veri bağdaştırıcıları ayarlarını belirtir. Tanılama veri bağdaştırıcıları ortamı ve test altındaki uygulama hakkında ek bilgi toplayın. Her bağdaştırıcı varsayılan ayarlara sahiptir ve varsayılan değerleri kullanmak istemiyorsanız, ayarları sağlamak yeterlidir.

#### <a name="code-coverage-adapter"></a>Kod kapsamı bağdaştırıcısı

Kod kapsamı veri toplayıcısı uygulama kodu bölümlerinin testte uygulandığı bir günlük oluşturur. Kod kapsamı ayarlarını özelleştirme hakkında daha fazla bilgi için bkz: [kod kapsamı çözümlemeyi özelleştirme](../test/customizing-code-coverage-analysis.md).

#### <a name="video-data-collector"></a>Video veri toplayıcısı

Video veri toplayıcı testlerini çalıştırdığınızda, kaydı ekran yakalar. Bu kayıt, UI testleri sorun giderme için yararlıdır. Video veri toplayıcı sağlanmıştır **Visual Studio 2017 sürüm 15,5** ve daha yüksek.

Başka herhangi bir tür tanılama verisi bağdaştırıcısını özelleştirmek için test ayarları dosyası kullanmanız gerekir. Daha fazla bilgi için bkz: [Visual Studio testleri için Test ayarlarını belirtme](/devops-test-docs/test/specifying-test-settings-for-visual-studio-tests).

### <a name="testrunparameters"></a>TestRunParameters

TestRunParameters değişkenleri ve çalışma zamanında testleri için kullanılabilir olan değerler tanımlamak için bir yol sağlar. Bu değişkenler kullanarak erişilebilir [testiyse](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testcontext(v=vs.140).aspx) nesnesi.

```csharp
[TestMethod]
public void HomePageTest()
{
    string appURL = TestContext.Properties["webAppUrl"];
```

Testiyse kullanmak için özel ekleyin [testiyse](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testcontext(v=vs.140).aspx) alan ve ortak bir `TestContext` test sınıfınıza özelliği.

### <a name="mstest-run-settings"></a>MSTest Çalıştırma Ayarları

Bu ayarları sahip test yöntemleri çalıştıran test bağdaştırıcısı belirli `[TestMethod]` özniteliği.

|Yapılandırma|Varsayılan|Değerler|
|-------------------|-------------|------------|
|ForcedLegacyMode|false|Visual Studio 2012'de mstest'i bağdaştırıcı daha hızlı ve daha ölçeklenebilir yapmak için en iyi duruma getirilmiş. Testlerin çalışma sırası gibi bazı davranışlar Visual Studio'nun önceki sürümlerindekiyle aynı olmayabilir. Bu değeri ayarlayın `true` eski test bağdaştırıcısını kullanmak için.<br /><br /> Örneğin, varsa bu ayarı kullanabilirsiniz bir *app.config* birim testi için belirtilen dosya.<br /><br /> Daha yeni bağdaştırıcı kullanmanıza olanak vermek için testlerinizi yeniden düzenlemenizi öneririz.|
|IgnoreTestImpact|false|MSTest veya Microsoft Test Yöneticisi'nde çalıştırıldığında test etkisi özelliği son değişikliklerden etkilenen testleri önceliklendirir. Bu ayar özelliği devre dışı bırakır. Daha fazla bilgi için bkz: [nasıl yapılır: kod değişikliklerinden sonra çalıştırmak olması gerektiğini denetlemek için hangi testlerin verileri topla](http://msdn.microsoft.com/Library/2f921ea1-9bb0-4870-a30f-0521fc22cb47).|
|SettingsFile||Burada MS Test bağdaştırıcısı ile kullanmak için test ayarları dosyası belirtebilirsiniz. Ayrıca menüsünü kullanarak bir test ayarları dosyasını belirtebilirsiniz **Test**, **Test ayarlarını**, **Test ayarları dosyasını seçin**.<br /><br /> Bu değer belirtirseniz, de ayarlamalısınız **ForcedlegacyMode** için **doğru**.<br /><br /> `<RunSettings>   <MSTest>     <SettingsFile>my.testsettings</SettingsFile>      <ForcedLegacyMode>true</ForcedLegacyMode>    </MSTest> </RunSettings>`|
|KeepExecutorAliveAfterLegacyRun|false|Test çalıştırması tamamlandıktan sonra MSTest kapatılır. Testin bir parçası da sonlandırıldı olarak başlatılan bir işlem. Test yürütücüsünü canlı tutmak istiyorsanız bu yapılandırmayı doğru olarak etkinleştirin.<br /><br /> Örneğin, arasında kodlanmış UI testleri çalıştırma tarayıcı tutmak için bu ayarı kullanabilirsiniz.|
|DeploymentEnabled|true|Değeri false olarak ayarlarsanız, test yönteminize belirttiğiniz dağıtım öğeleri dağıtım dizinine kopyalanmaz.|
|CaptureTraceOutput|true|Trace.WriteLine kullanarak Test yönteminizden hata ayıklama izine yazabilirsiniz. Bu yapılandırmayı kullanarak bu hata ayıklama izlemelerini kapatabilirsiniz.|
|DeleteDeploymentDirectoryAfterTestRunIsComplete|true|Dağıtım Dizini'ni, bu değeri yanlış olarak ayarlayarak bir test çalıştırdıktan sonra koruyabilirsiniz.|
|MapInconclusiveToFailed|false|Bir test, yetersiz durum getirirse genellikle Test Gezgini'nde Atlandı durumuna eşlenir. Başarısız olarak gösterilecek yetersiz testleri istiyorsanız, bu yapılandırma kullanın.|
|InProcMode|false|MS Test bağdaştırıcısı olarak testlerinizin aynı işlemde çalıştırılmasını isterseniz bu değeri doğru olarak ayarlayın. Bu ayar, küçük bir performans kazancı sağlar. Ancak özel durum içeren bir test varsa, diğer testler devam etmez.|
|AssemblyResolution|false|Bulma ve birim testleri çalıştırırken ek derlemeler için yol belirtebilirsiniz. Örneğin, bu yollar test derleme ile aynı dizinde bulunan yok bağımlılık derlemeler için kullanın. Bir yol belirtmek için "Dizin yolu" öğesi kullanın. Yol, ortam değişkenleri içerebilir.<br /><br /> `<AssemblyResolution>  <Directory Path="D:\myfolder\bin\" includeSubDirectories="false"/> </AssemblyResolution>`|

## <a name="see-also"></a>Ayrıca bkz.

[Kod Kapsamı Çözümlemeyi Özelleştirme](../test/customizing-code-coverage-analysis.md)
