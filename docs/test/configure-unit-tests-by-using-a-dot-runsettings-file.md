---
title: ".Runsettings dosyasını kullanarak birim testlerini yapılandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: 1925152f830d9969c8650fe698be6ebc70e65cf2
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
---
# <a name="configure-unit-tests-by-using-a-runsettings-file"></a>.runsettings dosyasını kullanarak birim testlerini yapılandırma

Birim testleri Visual Studio kullanarak yapılandırılabilir bir \*.runsettings dosyasını. ('.Runsettings' uzantısını kullanan sağlanan dosya adı, önemli değildir.) Örneğin, üzerinde testler çalışır, .NET Framework sürümünü burada test sonuçlarını teslim edilir ve test sırasında toplanan verileri çalıştırmak dizini değiştirebilirsiniz.

Özel bir yapılandırma gerektirmeyen, gerekmeyen bir \*.runsettings dosyasını. En yaygın kullanımı bir \*.runsettings dosyasıdır özelleştirmek için [kod kapsamı](../test/customizing-code-coverage-analysis.md).

## <a name="customizing-tests-with-a-runsettings-file"></a>Bir .runsettings dosyası ile testleri özelleştirme

1. Visual Studio çözümünüz için bir XML dosyası ekleyin ve test.runsettings için yeniden adlandırın. (Dosya adı önemli değildir, ancak uzantı .runsettings olmalıdır.)

1. Aşağıdaki örnek XML'den dosya içeriğini değiştirin ve gerektiği gibi özelleştirin.

1. Üzerinde **Test** menüsünde seçin **Test ayarları** > **Test ayarları dosyasını seçin**.

Birden fazla oluşturabileceğiniz \*.runsettings dosya, çözümünüz ve etkinleştirme veya bunları farklı zamanlarda kullanarak devre dışı **Test ayarlarını** menüsü.

![Çalışma ayarları dosyası etkinleştirme](../test/media/runsettings-1.png "RunSettings-1")

## <a name="example-runsettings-file"></a>Örnek .runsettings dosyasını

Aşağıdadır tipik bir \*.runsettings dosyasını. Her değerin bir varsayılanı olduğundan, dosyanın her bir öğesi isteğe bağlıdır.

```xml
<?xml version="1.0" encoding="utf-8"?>  
<RunSettings>  
  <!-- Configurations that affect the Test Framework -->  
  <RunConfiguration>  
    <MaxCpuCount>1</MaxCpuCount>  
    <!-- Path relative to solution directory -->  
    <ResultsDirectory>.\TestResults</ResultsDirectory>  
  
    <!-- [x86] | x64    
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
  
.Runsettings dosyasını da yapılandırmak için kullanılan [kod kapsamı](../test/customizing-code-coverage-analysis.md).  
  
Bu konunun geri kalanı dosya içeriğini açıklamaktadır.  

## <a name="edit-your-runsettings-file"></a>.runsettings dosyanızı düzenleme

.Runsettings dosyası aşağıdaki öğelere sahiptir.

### <a name="test-run-configuration"></a>Test çalıştırma yapılandırması

|Düğüm|Varsayılan|Değerler|  
|----------|-------------|------------|  
|`ResultsDirectory`||Test sonuçlarının yerleştirileceği dizin.|  
|`TargetFrameworkVersion`|Framework40|Framework35, Framework40, Framework45<br /><br /> Bu birim test çerçevesinin hangi sürümünün testlerini bulmak ve yürütmek için kullanıldığını belirtir. Birim test projesinin yapı özelliklerinde belirttiğiniz .NET platformu sürümünden farklı olabilir.|  
|`TargetPlatform`|x86|x86, x64|  
|`TreatTestAdapterErrorsAsWarnings`|false|yanlış, doğru|  
|`TestAdaptersPaths`||Bir veya birden çok yol TestAdapters bulunduğu dizine|  
|`MaxCpuCount`|1.|Bu denetimler birim çalıştırırken paralel test yürütmesi derecesini, makinede kullanılabilir çekirdekleri kullanılarak test eder.  Test yürütme altyapısı, her kullanılabilir çekirdek ayrı bir işlem olarak başlar ve her çekirdek ile bir derlemeyi, DLL ya da ilgili yapı gibi çalışması için testleri bir kapsayıcı sağlar.  Test kapsayıcısı zamanlama birimidir.  Her kapsayıcısında testleri test çerçevesi göre çalıştırılır.  Birçok kapsayıcıları varsa, daha sonra bir kapsayıcıda testleri çalıştırma bitiş işlerken kendisine sonraki kullanılabilir kapsayıcı verilir.<br /><br /> MaxCpuCount olabilir:<br /><br /> 1 burada n < = n < = çekirdek sayısı: n işlemlerinin tasarrufundadır başlatılacak<br /><br /> n, burada n herhangi bir değer =: başlatılan işlem sayısı kadar kullanılabilir çekirdeğe makinedeki kadar olacaktır|  
  
### <a name="diagnostic-data-adapters-data-collectors"></a>Tanılama Veri Bağdaştırıcıları (Veri Toplayıcıları)

`DataCollectors` Öğesi tanılama veri bağdaştırıcıları ayarlarını belirtir. Tanılama veri bağdaştırıcıları, test uygulanmakta olan uygulama ve ortam hakkında ek bilgi toplamak için kullanılır. Her bağdaştırıcı varsayılan ayarlara sahiptir ve varsayılan değerleri kullanmak istemiyorsanız, ayarları sağlamak yeterlidir.

#### <a name="code-coverage-adapter"></a>Kod kapsamı bağdaştırıcısı

Kod kapsamı veri toplayıcısı uygulama kodu bölümlerinin testte uygulandığı bir günlük oluşturur. Kod kapsamı ayarlarını özelleştirme hakkında daha fazla bilgi için bkz: [kod kapsamı çözümlemeyi özelleştirme](../test/customizing-code-coverage-analysis.md).

### <a name="testrunparameters"></a>TestRunParameters

TestRunParameters değişkenleri ve çalışma zamanında testleri için kullanılabilir olan değerler tanımlamak için bir yol sağlar.  

### <a name="mstest-run-settings"></a>MSTest Çalıştırma Ayarları

Bu ayarları sahip test yöntemleri çalıştıran test bağdaştırıcısı belirli `[TestMethod]` özniteliği.  

|Yapılandırma|Varsayılan|Değerler|  
|-------------------|-------------|------------|  
|ForcedLegacyMode|false|Visual Studio 2012'de, MSTest bağdaştırıcısı daha hızlı ve daha ölçeklenebilir olması için iyileştirilmiştir. Testlerin çalışma sırası gibi bazı davranışlar Visual Studio'nun önceki sürümlerindekiyle aynı olmayabilir. Bu değeri ayarlayın `true` eski test bağdaştırıcısını kullanmak için.<br /><br /> Örneğin, birim testi için belirtilen bir app.config dosyanız varsa bunu kullanabilirsiniz.<br /><br /> Daha yeni bağdaştırıcı kullanmanıza olanak vermek için testlerinizi yeniden düzenlemenizi öneririz.|  
|IgnoreTestImpact|false|MSTest veya Microsoft Test Yöneticisi'nde çalıştırıldığında test etkisi özelliği son değişikliklerden etkilenen testleri önceliklendirir. Bu ayar özelliği devre dışı bırakır. Daha fazla bilgi için bkz: [nasıl yapılır: kod değişikliklerinden sonra çalıştırmak olması gerektiğini denetlemek için hangi testlerin verileri topla](http://msdn.microsoft.com/Library/2f921ea1-9bb0-4870-a30f-0521fc22cb47).|  
|SettingsFile||Burada MS Test bağdaştırıcısı ile kullanmak için test ayarları dosyası belirtebilirsiniz. Ayrıca menüsünü kullanarak bir test ayarları dosyasını belirtebilirsiniz **Test**, **Test ayarlarını**, **Test ayarları dosyasını seçin**.<br /><br /> Bu değer belirtirseniz, de ayarlamalısınız **ForcedlegacyMode** için **doğru**.<br /><br /> `<RunSettings>   <MSTest>     <SettingsFile>my.testsettings</SettingsFile>      <ForcedLegacyMode>true</ForcedLegacyMode>    </MSTest> </RunSettings>`|  
|KeepExecutorAliveAfterLegacyRun|false|Test çalıştırması tamamlandıktan sonra MSTest kapatılır. Testin bir parçası olarak başlatılan tüm işlemler de şu anda bitirilecek. Test yürütücüsünü canlı tutmak istiyorsanız bu yapılandırmayı doğru olarak etkinleştirin.<br /><br /> Örneğin, tarayıcının kodlanmış UI testleri arasında çalışmasını sürdürmek için bunu kullanabilirsiniz.|  
|DeploymentEnabled|true|Bunu yanlış olarak ayarlarsanız, test yönteminizde belirttiğiniz dağıtım öğeleri dağıtım dizinine kopyalanmaz.|  
|CaptureTraceOutput|true|Trace.WriteLine kullanarak Test yönteminizden hata ayıklama izine yazabilirsiniz. Bu yapılandırmayı kullanarak bu hata ayıklama izlemelerini kapatabilirsiniz.|  
|DeleteDeploymentDirectoryAfterTestRunIsComplete|true|Dağıtım Dizini'ni, bu değeri yanlış olarak ayarlayarak bir test çalıştırdıktan sonra koruyabilirsiniz.|  
|MapInconclusiveToFailed|false|Bir test, yetersiz durum getirirse genellikle Test Gezgini'nde Atlandı durumuna eşlenir. Yetersiz testlerin Başarısız olarak gösterilmesini istiyorsanız bu yapılandırmayı kullanın.|  
|InProcMode|false|MS Test bağdaştırıcısı olarak testlerinizin aynı işlemde çalıştırılmasını isterseniz bu değeri doğru olarak ayarlayın. Bu ayar, küçük bir performans kazancı sağlar. Ancak özel durum içeren bir test varsa, diğer testler devam etmez.|  
|AssemblyResolution|false|Bulma ve birim testleri çalıştırırken ek derlemeler için yol belirtebilirsiniz.  Örneğin, bu yollar test derleme ile aynı dizinde bulunan yok bağımlılık derlemeler için kullanın.  Bir yol belirtmek için "Dizin yolu" öğesi kullanın.  Yol, ortam değişkenleri içerebilir.<br /><br /> `<AssemblyResolution>  <Directory Path>"D:\myfolder\bin\" includeSubDirectories="false"/> </AssemblyResolution>`|  

## <a name="see-also"></a>Ayrıca bkz.

[Kod Kapsamı Çözümlemeyi Özelleştirme](../test/customizing-code-coverage-analysis.md)  
