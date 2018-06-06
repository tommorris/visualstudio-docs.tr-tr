---
title: .Runsettings dosyasını ile birim testlerini yapılandırma
ms.date: 02/28/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: f0cb4989877445a0679a5682aaa17e4b7f759a33
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/06/2018
ms.locfileid: "34815983"
---
# <a name="configure-unit-tests-by-using-a-runsettings-file"></a>Kullanarak birim testlerini yapılandırma bir *.runsettings* dosyası

Birim testleri Visual Studio kullanarak yapılandırılabilir bir *.runsettings* dosya. Örneğin, üzerinde yapılan testler, dizin test sonuçlarını ya da bir test çalışması sırasında toplanan veriler için .NET Framework sürümünü değiştirebilirsiniz.

Çalıştırma ayarlarını dosyaları isteğe bağlıdır. Özel bir yapılandırma gerektirmeyen, gerekmeyen bir *.runsettings* dosya. En yaygın kullanımı bir *.runsettings* dosyasıdır özelleştirmek için [kod kapsamı çözümlemeyi](../test/customizing-code-coverage-analysis.md).

## <a name="specify-a-run-settings-file"></a>Bir çalıştırma ayarlarını belirtin

Çalışma ayarları dosyaları, komut satırından, IDE içinde ya da içinde çalışan testler yapılandırmak için kullanılabilir bir [iş akışı derleme](/vsts/pipelines/test/getting-started-with-continuous-testing?view=vsts) Visual Studio Team Services (VSTS) veya Team Foundation Server (TFS) kullanarak.

### <a name="specify-a-run-settings-file-in-the-ide"></a>IDE içinde bir çalıştırma ayarlarını belirtin

Seçin **Test** > **Test ayarları** > **Test ayarları dosyasını seçin** ve ardından *.runsettings*dosya. Dosya kasasındaki **Test ayarlarını** menü ve seçin veya bu seçimini kaldırın. Seçtiğiniz her seçili olsa da, çalışma ayarları dosyasının geçerli **kod kapsamını çözümleme**.

![Visual Studio'da Test ayarlarını Dosya menüsünü seçin](media/select-test-settings-file.png)

### <a name="specify-a-run-settings-file-at-the-command-line"></a>Bir komut satırından çalıştırma ayarlarını belirtin

Komut satırından testleri çalıştırmak için kullandığınız *vstest.console.exe* ve ayarlar dosyasını kullanarak belirttiğiniz **/Settings** parametresi.

1. Visual Studio Geliştirici Komut Satırını başlatın:

   Windows **Başlat** menüsünde seçin **Visual Studio 2017** > **VS 2017 için geliştirici komut istemi**.

2. Benzer şekilde bir komut girin:

   ```cmd
   vstest.console.exe MyTestAssembly.dll /EnableCodeCoverage /Settings:CodeCoverage.runsettings
   ```

## <a name="customize-tests"></a>Testlerini özelleştirme

Kullanarak testlerinizi özelleştirmek için bir *.runsettings* dosya, aşağıdaki adımları izleyin:

1. Visual Studio çözümünüz için bir XML dosyası ekleyin ve kaydedileceği *test.runsettings*.

   > [!TIP]
   > Bu uzantıyı kullanan sürece dosya adı önemli değildir *.runsettings*.

1. Aşağıdaki örnek XML'den dosya içeriğini değiştirin ve gerektiği gibi özelleştirin.

1. Üzerinde **Test** menüsünde seçin **Test ayarları** > **Test ayarları dosyasını seçin**. Gözat *.runsettings* oluşturduğunuz dosya ve ardından **Tamam**.

   > [!TIP]
   > Birden fazla oluşturabileceğiniz *.runsettings* dosya, çözümünüz ve gerektiği gibi etkin test ayarları dosyası olarak seçin.

## <a name="example-runsettings-file"></a>Örnek *.runsettings* dosyası

Aşağıdaki XML tipik bir içeriğini gösterir *.runsettings* dosya. Varsayılan değeri olduğundan dosyasının her öğesinin isteğe bağlıdır.

```xml
<?xml version="1.0" encoding="utf-8"?>
<RunSettings>
  <!-- Configurations that affect the Test Framework -->
  <RunConfiguration>
    <MaxCpuCount>1</MaxCpuCount>
    <!-- Path relative to solution directory -->
    <ResultsDirectory>.\TestResults</ResultsDirectory>

    <!-- x86 or x64 -->
    <!-- You can also change it from menu Test > Test Settings > Default Processor Architecture -->
    <TargetPlatform>x86</TargetPlatform>

    <!-- Framework35 | [Framework40] | Framework45 -->
    <TargetFrameworkVersion>Framework40</TargetFrameworkVersion>

    <!-- Path to Test Adapters -->
    <TestAdaptersPaths>%SystemDrive%\Temp\foo;%SystemDrive%\Temp\bar</TestAdaptersPaths>

    <!-- TestSessionTimeout is only available with Visual Studio 2017 version 15.5 and higher -->
    <!-- Specify timeout in milliseconds. A valid value should be greater than 0 -->
    <TestSessionTimeout>10000</TestSessionTimeout>
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

## <a name="elements-of-a-runsettings-file"></a>Öğeleri bir *.runsettings* dosyası

Öğelerini bölümlerde ayrıntılı bir *.runsettings* dosya.

### <a name="run-configuration"></a>Çalışma yapılandırması

```xml
<RunConfiguration>
    <MaxCpuCount>1</MaxCpuCount>
    <ResultsDirectory>.\TestResults</ResultsDirectory>
    <TargetPlatform>x86</TargetPlatform>
    <TargetFrameworkVersion>Framework40</TargetFrameworkVersion>
    <TestAdaptersPaths>%SystemDrive%\Temp\foo;%SystemDrive%\Temp\bar</TestAdaptersPaths>
    <TestSessionTimeout>10000</TestSessionTimeout>
</RunConfiguration>
```

**RunConfiguration** öğesi, aşağıdaki öğeleri içerebilir:

|Düğüm|Varsayılan|Değerler|
|----------|-------------|------------|
|**ResultsDirectory**||Test sonuçları yerleştirildiği dizin.|
|**targetFrameworkVersion**|Framework40|Framework35, Framework40, Framework45<br /><br />Bu ayar, bulmak ve testler yürütmek için kullanılan birim test çerçevesi hangi sürümü belirtir. Birim test projesinin yapı özelliklerinde belirttiğiniz .NET platformu sürümünden farklı olabilir.|
|**TargetPlatform**|x86|x86, x64|
|**TreatTestAdapterErrorsAsWarnings**|false|yanlış, doğru|
|**TestAdaptersPaths**||Bir veya birden çok yol TestAdapters bulunduğu dizine|
|**MaxCpuCount**|1.|Bu çalışan birim testleri zaman denetimleri paralel test yürütmesi derecesini ayarlama, makinede kullanılabilir çekirdekleri kullanılarak. Test yürütme altyapısı, her kullanılabilir çekirdek ayrı bir işlem olarak başlatır ve her çekirdek ile testleri çalıştırmak için bir kapsayıcı sağlar. Bir kapsayıcı, bir derleme, DLL veya ilgili yapı olabilir. Test kapsayıcısı zamanlama birimidir. Her kapsayıcısında testleri test çerçevesi göre çalıştırılır. Birçok kapsayıcıları varsa, daha sonra bir kapsayıcıda testleri çalıştırma bitiş işlerken bunlar sonraki kullanılabilir kapsayıcı verilir.<br /><br />MaxCpuCount olabilir:<br /><br />n, 1 burada < n = < çekirdek sayısı =: n işlemlerinin tasarrufundadır başlattı<br /><br />n, burada n herhangi bir değer =: başlatılan işlem sayısı kullanılabilir çekirdek sayısı kadar olabilir|
|**TestSessionTimeout**||Kullanıcıların belirli bir zaman aşımı aştığında bir test oturumu sonlandır olanak tanır. Ayar kaynakları da tüketilen zaman aşımı sağlar ve test oturumları bir süre için kısıtlanmıştır. Bulunan bir ayardır **Visual Studio 2017 sürüm 15,5** ve daha sonra.|

### <a name="diagnostic-data-adapters-data-collectors"></a>Tanılama veri bağdaştırıcıları (veri toplayıcıları)

**DataCollectors** öğesi tanılama veri bağdaştırıcıları ayarlarını belirtir. Tanılama veri bağdaştırıcıları ortamı ve test altındaki uygulama hakkında ek bilgi toplayın. Her bağdaştırıcı varsayılan ayarlara sahiptir ve varsayılan değerleri kullanmak istemiyorsanız, ayarları sağlamak yeterlidir.

#### <a name="code-coverage-adapter"></a>Kod kapsamı bağdaştırıcısı

```xml
<CodeCoverage>
    <ModulePaths>
        <Exclude>
            <ModulePath>.*CPPUnitTestFramework.*</ModulePath>
        </Exclude>
    </ModulePaths>

    <UseVerifiableInstrumentation>True</UseVerifiableInstrumentation>
    <AllowLowIntegrityProcesses>True</AllowLowIntegrityProcesses>
    <CollectFromChildProcesses>True</CollectFromChildProcesses>
    <CollectAspDotNet>False</CollectAspDotNet>
</CodeCoverage>
```

Kod kapsamı veri toplayıcısı uygulama kodu bölümlerinin testte uygulandığı bir günlük oluşturur. Kod kapsamı ayarlarını özelleştirme hakkında daha fazla bilgi için bkz: [kod kapsamı çözümlemeyi özelleştirme](../test/customizing-code-coverage-analysis.md).

#### <a name="video-data-collector"></a>Video veri toplayıcısı

Video veri toplayıcı testlerini çalıştırdığınızda, kaydı ekran yakalar. Bu kayıt, UI testleri sorun giderme için yararlıdır. Video veri toplayıcı kullanılabilir **Visual Studio 2017 sürüm 15,5** ve daha sonra.

Başka türde bir tanılama veri bağdaştırıcıları özelleştirmek için bir [test ayarları dosyası](../test/collect-diagnostic-information-using-test-settings.md).

### <a name="testrunparameters"></a>TestRunParameters

```xml
<TestRunParameters>
    <Parameter name="webAppUrl" value="http://localhost" />
    <Parameter name="webAppUserName" value="Admin" />
    <Parameter name="webAppPassword" value="Password" />
</TestRunParameters>
```

Test çalışması parametreleri değişkenleri ve çalışma zamanında testleri için kullanılabilir olan değerler tanımlamak için bir yol sağlar. Kullanarak parametreler erişim <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestContext.Properties%2A?displayProperty=nameWithType> özelliği:

```csharp
[TestMethod]
public void HomePageTest()
{
    string appURL = TestContext.Properties["webAppUrl"];
```

Test çalışması parametrelerini kullanmak için bir özel eklemek <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestContext> alan ve ortak bir <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestContext> test sınıfınıza özelliği.

### <a name="mstest-run-settings"></a>Mstest'i çalışma ayarları

```xml
<MSTest>
    <MapInconclusiveToFailed>True</MapInconclusiveToFailed>
    <CaptureTraceOutput>false</CaptureTraceOutput>
    <DeleteDeploymentDirectoryAfterTestRunIsComplete>False</DeleteDeploymentDirectoryAfterTestRunIsComplete>
    <DeploymentEnabled>False</DeploymentEnabled>
    <AssemblyResolution>
      <Directory Path="D:\myfolder\bin\" includeSubDirectories="false"/>
    </AssemblyResolution>
</MSTest
```

Bu ayarları sahip test yöntemleri çalıştıran test bağdaştırıcısı belirli <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> özniteliği.

|Yapılandırma|Varsayılan|Değerler|
|-------------------|-------------|------------|
|**ForcedLegacyMode**|false|Visual Studio 2012'de mstest'i bağdaştırıcı daha hızlı ve daha ölçeklenebilir yapmak için en iyi duruma getirilmiş. Testlerin çalışma sırası gibi bazı davranışlar Visual Studio'nun önceki sürümlerindekiyle aynı olmayabilir. Bu değer ayarlanırsa **true** eski test bağdaştırıcısını kullanmak için.<br /><br />Örneğin, varsa bu ayarı kullanabilirsiniz bir *app.config* birim testi için belirtilen dosya.<br /><br />Daha yeni bağdaştırıcı kullanmanıza olanak vermek için testlerinizi yeniden düzenlemenizi öneririz.|
|**IgnoreTestImpact**|false|MSTest veya Microsoft Test Yöneticisi'nde çalıştırıldığında test etkisi özelliği son değişikliklerden etkilenen testleri önceliklendirir. Bu ayar özelliği devre dışı bırakır. Daha fazla bilgi için bkz: [önceki yapıdan sonra hangi testlerin çalıştırılmalıdır](https://msdn.microsoft.com/library/dd286589).|
|**AyarlarDosyası**||Burada mstest'i bağdaştırıcısı ile kullanmak için test ayarları dosyasını belirtebilirsiniz. Seçerek test ayarları dosyasını belirtebilirsiniz **Test** > **Test ayarlarını** > **Test ayarları dosyasını seçin**.<br /><br />Bu değer belirtirseniz, de ayarlamalısınız **ForcedlegacyMode** için **doğru**.<br /><br />`<ForcedLegacyMode>true</ForcedLegacyMode>`|
|**KeepExecutorAliveAfterLegacyRun**|false|Test çalıştırması tamamlandıktan sonra MSTest kapatılır. Testin bir parçası da sonlandırıldı olarak başlatılan bir işlem. Test Yürütücü Canlı tutmak istiyorsanız, değer kümesine **doğru**. Örneğin, arasında kodlanmış UI testleri çalıştırma tarayıcı tutmak için bu ayarı kullanabilirsiniz.|
|**DeploymentEnabled**|true|Değeri ayarlarsanız verilen **yanlış**, test yönteminize belirttiğiniz dağıtım öğeleri olmayan dağıtım dizinine kopyalanır.|
|**CaptureTraceOutput**|true|Kullanarak, test yöntemi için hata ayıklama izleme yazabilirsiniz <xref:System.Diagnostics.Trace.WriteLine%2A?displayProperty=nameWithType>.|
|**DeleteDeploymentDirectoryAfterTestRunIsComplete**|true|Bir test çalışması sonra dağıtım dizini korumak için bu değeri ayarlamak **false**.|
|**MapInconclusiveToFailed**|false|Bir test yetersiz durumuyla tamamlarsa, atlanan durum eşlendi **Test Gezgini**. Başarısız olarak gösterilecek yetersiz testleri istiyorsanız değerine **doğru**.|
|**InProcMode**|false|Mstest'i bağdaştırıcısı ile aynı işlemde Çalıştırılacak testleri istiyorsanız, bu değer ayarlanırsa **doğru**. Bu ayar, küçük bir performans kazancı sağlar. Ancak, bir özel durum ile bir test bulunup bulunmadığını kalan testleri çalıştırma.|
|**AssemblyResolution**|false|Bulma ve birim testleri çalıştırırken ek derlemeler için yol belirtebilirsiniz. Örneğin, bu yollar test derleme ile aynı dizinde değil bağımlılık derlemeler için kullanın. Bir yol belirtmek için kullanın bir **dizin yolu** öğesi. Yol, ortam değişkenleri içerebilir.<br /><br />`<AssemblyResolution>  <Directory Path="D:\myfolder\bin\" includeSubDirectories="false"/> </AssemblyResolution>`|

## <a name="see-also"></a>Ayrıca bkz.

- [Kod kapsamı çözümlemeyi özelleştirme](../test/customizing-code-coverage-analysis.md)
- [Visual Studio Test görevinin (VSTS)](/vsts/pipelines/tasks/test/vstest?view=vsts)