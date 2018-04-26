---
title: Birim testi SSS Canlı
ms.date: 2017-10-03
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio ALM
- Live Unit Testing FAQ
author: rpetrusha
ms.author: ronpet
ms.workload:
- dotnet
ms.openlocfilehash: c49c23bc9ca77721ba6c39fb6c94a0994a70e7d9
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="live-unit-testing-frequently-asked-questions"></a>Sık sorulan sorular birim testi Canlı

## <a name="live-unit-testing-is-improved-and-enhanced-regularly-how-can-i-find-information-about-the-latest-new-features-and-enhancements"></a>Dinamik birim testi geliştirilmiş ve düzenli olarak geliştirilmiştir. Son yeni özellikler ve geliştirmeler hakkında bilgileri nasıl bulabilirim?

**Yanıt:**

Yeni özellikler ve canlı birim testi için Visual Studio 2017 sürüm 15.3 başlangıç yapılan geliştirmeler hakkında bilgi edinmek için [Canlı birim testi yenilikler](live-unit-testing-whats-new.md).

## <a name="what-test-frameworks-does-live-unit-testing-support-and-what-are-the-minimum-supported-versions"></a>Hangi test çerçevelerini Canlı birim testi desteği ve minimum desteklenen sürümleri nelerdir mu?

**Yanıt:**

Aşağıdaki tabloda listelenen üç popüler birim test çerçevelerini ile canlı birim testi çalışır. Ve çerçeveleri bağdaştırıcıları desteklenen minimum sürümü tabloda de listelenir. Birim testi çerçevelerini NuGet.org tüm kullanılabilir.

<table>
<tr>
   <th>Test çerçevesi</th>
   <th>Visual Studio bağdaştırıcısı en düşük sürüm</th>
   <th>Framework en düşük sürüm</th>
</tr>
<tr>
   <td>xUnit.net</td>
   <td> xunit.Runner.VisualStudio sürüm 2.2.0-beta3-build1187</td>
   <td>xunit 1.9.2</td>
</tr>
<tr>
   <td>NUnit</td>
   <td>NUnit3TestAdapter sürüm 3.5.1</td>
   <td>NUnit sürüm 3.5.0</td>
</tr>
<tr>
   <td>MSTest</td>
   <td>MSTest.TestAdapter 1.1.4-preview</td>
   <td>MSTest.TestFramework 1.0.5-preview</td>
</tr>
</table>

Eski mstest'i dayalı test varsa, bu başvuruyu projeleri `Microsoft.VisualStudio.QualityTools.UnitTestFramework` ve daha yeni mstest'i NuGet paketleri, Visual Studio 2017 sürüm 15.4 yükseltme taşımak istemiyorsanız.

Bazı durumlarda, açıkça Canlı çalışması birim testi için sırayla Çözümdeki projeler tarafından başvurulan NuGet paketlerini geri yüklemek gerekebilir. Açık bir yapı çözümü yaparak ya da paketlerin geri yükleyebilirsiniz (seçin **yapı**, **çözümü yeniden derle** en üst düzey Visual Studio menüsünde), ya da çözüm üzerinde sağ tıklanarak ve seçme **NuGet paketleri geri** yaşam birim testi etkinleştirmeden önce.

## <a name="does-live-unit-testing-work-with-net-core"></a>Birim testi Canlı .NET Core'u kullanmaya çalışıyor mu?

**Yanıt:**

Evet. Dinamik birim testi .NET Core ve .NET Framework ile çalışır. .NET Core desteği en son Visual Studio 2017 sürüm 15.3 eklendi. .NET Core Canlı birim testi desteği istiyorsanız bu Visual Studio sürümüne yükseltin.

## <a name="why-doesnt-live-unit-testing-work-when-i-turn-it-on"></a>Birim testi Canlı etkinleştirmeden zaman neden çalışmıyor?

**Yanıt:**

**Çıktı penceresi** (dinamik birim testi açılan seçildiğinde) neden Canlı birim testi çalışmadığını söyleyecektir. Dinamik birim testi aşağıdaki nedenlerden birinden dolayı çalışmayabilir:

- Çözümdeki projeler tarafından başvurulan NuGet paketleri geri değil, Canlı birim testi çalışmaz. Bu sorunu, açık bir yapı çözümü yapılması veya birim testi Canlı kapatmadan önce çözümde NuGet paketleri geri çözümlenmelidir.

- Mstest'i tabanlı testleri projelerinizde kullanıyorsanız, başvuru kaldırdığınızdan emin olun `Microsoft.VisualStudio.QualityTools.UnitTestFramework`ve en son mstest'i NuGet Paketlerine yönelik başvuruları ekleme `MSTest.TestAdapter` (1.1.11 en düşük sürümü gereklidir) ve `MSTest.TestFramework` (en düşük sürüm 1.1.11 gereklidir). Daha fazla bilgi için "Desteklenen test çerçevelerini" bölümüne bakın [kullanmak Canlı birim testi Visual Studio 2017 Enterprise Edition'da](live-unit-testing.md#supported-test-frameworks) makalesi.

- En az bir proje çözümünüzdeki NuGet başvuru veya xUnit NUnit, doğrudan başvuru olmalıdır veya mstest'i test çerçevesi. Bu projede de bir karşılık gelen Visual Studio test bağdaştırıcıları NuGet paketi başvuruda bulunmalıdır. Visual Studio test bağdaştırıcısı aracılığıyla da başvurulabilir bir `.runsettings` dosyası. `.runsettings` Dosyasını aşağıdaki örneğe benzer bir giriş olması gerekir:

   ```xml
    <RunSettings>
       <RunConfiguration>
          <TestAdaptersPaths>path-to-your-test-adapter</TestAdaptersPaths>
       </RunConfiguration>
    </RunSettings>
   ```

## <a name="why-does-live-unit-testing-show-incorrect-coverage-after-you-upgrade-the-test-adapter-referenced-in-your-visual-studio-projects-to-the-supported-version"></a>Neden desteklenen sürüm, Visual Studio projelerine başvuru test bağdaştırıcısı yükselttikten sonra birim testi Canlı yanlış kapsamı gösteriyor mu?

**Yanıt:**

- Birden çok proje çözümü başvurusu NuGet bağdaştırıcı paketini test ederseniz, bunların her birini desteklenen bir sürüme yükseltilmelidir.

- Test bağdaştırıcısı paketten içe MSBuild .props dosyasının doğru de güncelleştirildiğinden emin olun. NuGet Paket sürümü/yolu genellikle aşağıdaki gibi proje dosyanın en üstüne yakın bulunabilir içeri aktarmanın denetleyin:

   ```xml
    <Import Project="..\packages\xunit.runner.visualstudio.2.2.0\build\net20\xunit.runner.visualstudio.props" Condition="Exists('..\packages\xunit.runner.visualstudio.2.2.0\build\net20\xunit.runner.visualstudio.props')" />
   ```

## <a name="can-i-customize-my-live-unit-testing-builds"></a>My Canlı birim testi derlemeleri özelleştirebilir miyim?

**Yanıt:**

Çözümünüzü "Normal" izlenmiş olmayan derleme için gerekli olmayan alt yapısı (birim testi Canlı) oluşturmak için özel adımlar gerektirir sonra denetler, proje veya .targets dosyalarına kod ekleyebilirsiniz `BuildingForLiveUnitTesting` özelliği ve gerçekleştirir Özel ön/son adımlar oluşturun. (Yayımlama veya paketleri oluşturma gibi) belirli yapı adımları kaldırın veya bu proje özelliğine dayalı birim testi canlı bir yapı (Önkoşullar kopyalama gibi) yapı adımları eklemek için de seçebilirsiniz. Bu, normal yapınızın herhangi bir şekilde değiştirmez ve yalnızca birim testi Canlı derlemeleri etkiler.

Örneğin, normal bir derleme sırasında NuGet paketlerini üreten bir hedef olabilir. Yaptığınız her düzenlemeden sonra oluşturulacak NuGet paketlerini büyük olasılıkla istemezsiniz. Bu nedenle, hedefleyen birim testi Canlı derlemede aşağıdakine benzer yaparak devre dışı bırakabilirsiniz:  

```xml
<Target Name="GenerateNuGetPackages" BeforeTargets="AfterBuild" Condition="'$(BuildingForLiveUnitTesting)' != 'true'">
    <Exec Command='"$(MSBuildThisFileDirectory)..\tools\GenPac" '/>
</Target>
```

## <a name="error-messages-with-ltoutputpathgt-or-ltoutdirgt"></a>Hata iletileri ile &lt;OutputPath&gt; veya &lt;OutDir&gt;

**Neden alabilirim aşağıdaki hata Canlı birim testi my çözümü oluşturmak çalıştığında: ".. koşulsuz olarak ayarlamak için .appears `<OutputPath>` veya `<OutDir>`. Dinamik birim testi testleri çıkış derlemesinden yürütmez"?**

**Yanıt:**

Çözümünüz için yapılandırma işlemi koşulsuz olarak geçersiz kılmaları bu durum `<OutputPath>` veya `<OutDir>` bir alt olmaması `<BaseOutputPath>`. Ayrıca bu derleme yapıları altında bir klasör bırakılan emin olmak için geçersiz kılar olmadığından bu gibi durumlarda, Canlı birim testi çalışmaz `<BaseOutputPath>`. Düzenli bir yapı içinde kesilmesini, geçersiz kılmak için derleme yapıtları konumu geçersiz kılarsanız `<OutputPath>` göre koşullu `<BaseOutputPath>`.

Örneğin, yapı geçersiz kılar, `<OutputPath>` aşağıda gösterildiği gibi:

```xml 
<Project>
  <PropertyGroup>
    <OutputPath>$(SolutionDir)Artifacts\$(Configuration)\bin\$(MSBuildProjectName)</OutputPath>
  </PropertyGroup>
</Project>
```

ardından aşağıdaki ile değiştirebilirsiniz:

```xml 
<Project>
  <PropertyGroup>
    <BaseOutputPath Condition="'$(BaseOutputPath)' == ''">$(SolutionDir)Artifacts\$(Configuration)\bin\$(MSBuildProjectName)\</BaseOutputPath>
    <OutputPath Condition="'$(OutputPath)' == ''">$(BaseOutputPath)</OutputPath>
  </PropertyGroup>
</Project>
```
 
Bu sağlar `<OutputPath>` içinde kaynaklandığını `<BaseOutputPath>` klasör.

Geçersiz `<OutDir>` doğrudan yapı işleminizde; geçersiz kılma `<OutputPath>` yerine belirli bir konuma derleme yapıları bırakılamadı.
 
## <a name="setting-the-location-of-live-unit-testing-build-artifacts"></a>Birim testi dinamik derleme yapıları konumunu ayarlama

**Varsayılan konumu altında yerine belirli bir konuma gitmek için bir birim testi dinamik derleme yapıları istediğiniz `.vs` klasör. Nasıl değiştirebilir miyim?**

**Yanıt:**

Ayarlama `LiveUnitTesting_BuildRoot` istediğiniz Canlı birim testi bırakılmasına yapıları derleme yolu için kullanıcı düzeyinde ortam değişkeni. 

## <a name="how-is-running-tests-from-test-explorer-window-different-from-running-tests-in-live-unit-testing"></a>Nasıl testleri Test Gezgini penceresinden birim testine Canlı testleri çalıştırma farklı mı çalışıyor?

**Yanıt:**

Bazı farklar vardır:

- İzleme eklenmiş ikili dosyalar çalıştırılır Canlı birim testi çalıştırma veya Test Gezgini penceresi testlerden hata ayıklama normal ikili dosyaları, çalışır. İzleme eklenmiş ikili dosyalar hata ayıklama istiyorsanız, ekleme bir [Debugger.Launch](xref:System.Diagnostics.Debugger.Launch) yöntem çağrısı, test yönteminde neden olan her yöntemi (zaman canlı birim testi tarafından yürütülür dahil olmak üzere) yürütüldüğünde ve daha sonra başlatmak hata ayıklayıcı ekleme ve izleme eklenmiş ikili hata ayıklama. Ancak, Hedefimiz araçları çoğu kullanıcı senaryoları için saydam ve hata ayıklama gerekmez ikili dosyaları işaretlenir ' dir.

- Dinamik birim testi testleri çalıştırmak için yeni bir uygulama etki alanı oluşturmaz, ancak testleri Test Gezgini penceresinden Çalıştır yeni bir uygulama etki alanı oluşturun.

- Dinamik birim testi çalıştıran testleri her test derlemede ardışık olarak çalıştırırsanız, birden çok Test Gezgini penceresinden sınar ve seçtiğiniz ancak **paralel Testleri Çalıştır** düğmesi, bunların paralel olarak çalışır.

- Bulma ve canlı birim testi testlerinde yürütülmesi kullanan sürüm 2 `TestPlatform`, kullanırken Test Gezgini penceresi sürüm 1. Bir çoğu durumda, ancak fark değil. 

- Birim testi Canlı testleri birden çok iş parçacıklı grupta (MTA) çalıştırılır test Gezgini şu anda testleri bir tek iş parçacıklı grupta (STA) varsayılan olarak çalıştırır. Birim testi Canlı STA mstest'i testleri çalıştırmak için test yöntemi veya içeren sınıfıyla tasarlamanız `<STATestMethod>` veya `<STATestClass>` bulunabilir özniteliği `MSTest.STAExtensions 1.0.3-beta` NuGet paketi. Test yöntemi ile NUnit için işaretleme `<RequiresThread(ApartmentState.STA)>` özniteliği ve xUnit, ile `<STAFact>` özniteliği.

## <a name="how-do-i-exclude-tests-from-participating-in-live-unit-testing"></a>Testleri birim testine Canlı katılmasını nasıl bırakılsın mı?

**Yanıt:**

"Dahil ve hariç projeleri ve test yöntemleri" bölümüne bakın [kullanmak Canlı birim testi Visual Studio 2017 Enterprise Edition'da](live-unit-testing.md#including-and-excluding-test-projects-and-test-methods) için kullanıcıya özgü ayarı makalesine. Belirli bir belirli düzenleme oturumunun testleri kümesini çalıştırmak için veya kişisel tercihlerinize kalıcı hale getirmek için istediğinizde kullanışlıdır.
 
Çözüme özel ayarlarını uyguladığınız <xref:System.Diagnostics.CodeAnalysis.ExcludeFromCodeCoverageAttribute?displayProperty=fullName> programlı olarak yöntemler, özellikler, sınıfları veya yapıları Canlı birim testi tarafından izlenmiş gelen dışlanacak özniteliği. Ayrıca, aynı zamanda ayarlayabileceğiniz `<ExcludeFromCodeCoverage>` özelliğine `true` izlenmiş tüm proje dışlamak için proje dosyası. Dinamik birim testi değil izleme eklenmiş testleri hala çalışacak, ancak bunların kapsamı değil görselleştirilen.

Ayrıca kontrol edebilirsiniz olup olmadığını `Microsoft.CodeAnalysis.LiveUnitTesting.Runtime` geçerli uygulama etki alanında yüklenir ve oturum tabanlı testleri devre dışı bırakın. Örneğin, aşağıdaki xUnit ile benzer bir şey yapabilirsiniz:

```csharp
[ExcludeFromCodeCoverage]
public class SkipLiveFactAttribute : FactAttribute
{
   private static bool s_lutRuntimeLoaded = AppDomain.CurrentDomain.GetAssemblies().Any(a => a.GetName().Name ==
                                            "Microsoft.CodeAnalysis.LiveUnitTesting.Runtime");
   public override string Skip => s_lutRuntimeLoaded ? "Test excluded from Live Unit Testing" : "";
}

public class Class1
{
   [SkipLiveFact]
   public void F()
   {
      Assert.True(true);
   }
}
```

## <a name="why-are-win32-pe-headers-different-in-instrumented-assemblies-built-by-live-unit-testing"></a>Neden Win32 PE üstbilgileri Canlı birim testi tarafından oluşturulmuş Araçlı derlemeler farklı misiniz?

**Yanıt:**

Bu sorun düzeltilmiştir ve Visual Studio 2017 sürüm 15.3 yok. Visual Studio bu sürüme yükseltin.

Visual Studio 2017 daha eski sürümleri için aşağıdaki Win32 PE üstbilgisi verileri katıştırmak için başarısız olan dinamik birim testi derlemelerde sonuçlanabilir bilinen bir hata vardır:

- Sürüm dosyası (tarafından belirtilen @System.Reflection.AssemblyFileVersionAttribute kodu).

- Win32 simgesi (tarafından belirtilen `/win32icon:` komut satırında).

- Win32 bildirimi (tarafından belirtilen `/win32manifest:` komut satırında).

Bu değerleri kullanan testleri Canlı birim testi tarafından çalıştırıldığında başarısız olabilir.

## <a name="why-does-live-unit-testing-keep-building-my-solution-all-the-time-even-if-i-am-not-making-any-edits"></a>Neden birim canlı tut ı tüm düzenlemeleri değil olsa bile her zaman my çözümü oluşturma testi?

**Yanıt:**

Çözümünüzü oluşturma işlemi çözümünün parçası kaynak kodu görüntülenirse bu durum oluşabilir ve uygun girişleri ve çıkışları belirtilen yapı hedef dosyalarınızı sahip değil. MSBuild uygun güncel denetimleri gerçekleştirmek ve yeni bir yapı gerekip gerekmediğini belirlemek için hedefler girişleri ve çıkışları listesini verilmelidir.

Kaynak dosyalar değiştirilmiş algıladığında dinamik birim testi bir yapı başlatır. Çözümünüzü derleme kaynak dosyaları oluşturduğundan, Canlı birim testi sonsuz yapı döngüye alırsınız. Birim testi Canlı ikinci yapı (önceki derlemeden yeni oluşturulan kaynak dosyaların algıladıktan sonra) başlatıldığında girişleri ve çıkışları hedef ancak işaretli değilse girişleri ve çıkışları denetimleri belirteceğinden, döngü dışında çalışmamasına neden olur her şeyin güncel olduğundan.  

## <a name="how-does-live-unit-testing-work-with-the-lightweight-solution-load-feature"></a>Nasıl yapılır Canlı birim basit çözüm yükleme özelliğiyle iş testi?

**Yanıt:**

Dinamik birim testi şu anda de basit çözüm yükleme özelliğiyle işe yaramaz. Yalnızca en az bir testi projelerini yüklendikten sonra çalışır. Birim testi Canlı en az bir test bağdaştırıcısı (mstest'i, xUnit veya NUnit) başvuran test projeleri bağımlı olduğundan o zamana kadar çalışmaz yükleniyor.

> [!NOTE]
> Basit çözüm yük artık ve sonrasında 15,5 Visual Studio 2017 sürümde kullanılabilir değildir. Visual Studio 2017 içinde 15,5 ve sonraki sürümleri, içeren büyük çözümlerde kod yükü çok daha hızlı daha önce basit çözüm yükü olmadan bile yönetilen.

## <a name="why-does-live-unit-testing-does-not-capture-coverage-from-a-new-process-created-by-a-test"></a>Birim testi Canlı neden olmadığından bir test tarafından oluşturulan yeni bir işlem kapsamından yakalamaz?

**Yanıt:**

Bu bilinen bir sorundur ve Visual Studio 2017 bir sonraki güncelleştirmesinde düzeltilmesi.

## <a name="why-does-nothing-happen-after-i-include-or-exclude-tests-from-the-live-test-set"></a>Neden dahil etmek veya testleri Test Canlı kümeden hariç tut sonra hiçbir şey?

**Yanıt:**

Bu sorun düzeltilmiştir ve Visual Studio 2017 sürüm 15.3 yok. Visual Studio bu sürüme yükseltin.

Visual Studio 2017 daha eski sürümleri için bu bilinen bir sorundur. Bu sorunu çözmek için dahil veya testleri hariç sonra herhangi bir dosyaya bir düzenleme yapın gerekecektir. 

## <a name="live-unit-testing-and-editor-icons"></a>Birim testi ve düzenleyici simgeler Canlı

**Birim testi Canlı çıktı penceresinde iletileri dayalı test çalıştırması gibi görünüyor olsa bile Düzenleyicisi'nde hiçbir simge görmemin nedeni değil mi?**

**Yanıt:**

Üzerinde dinamik birim testi çalışıyor derlemeler için herhangi bir nedenle işaretlendiğine değil Bu olur. Örneğin, Canlı birim testi ayarlama projeleri ile uyumlu olmayan `<UseHostCompilerIfAvailable>false</UseHostCompilerIfAvailable>`. Bu durumda, yapı işleminizin ya da bu ayarını kaldırın veya ona değiştirmek için güncelleştirilmesi gerekiyor `true` Canlı çalışması birim testi için. 

## <a name="how-do-i-collect-more-detailed-logs-to-file-bug-reports"></a>Dosya hata raporları için nasıl daha ayrıntılı günlükleri toplamak?

**Yanıt:**

Ayrıntılı günlükleri toplamak gereken birkaç şey yapabilirsiniz:

- Git **Araçları**, **seçenekleri**, **Canlı birim testi** ve günlüğe kaydetme seçeneğini değiştirin **ayrıntılı**. Bu çıktı penceresinde gösterilecek ayrıntılı günlükleri neden olur.

- Ayarlama `LiveUnitTesting_BuildLog` kullanıcı ortam değişkenine MSBuild günlük yakalamak için kullanmak istediğiniz dosyanın adını. Birim testi Canlı yapılandırmalardan ayrıntılı MSBuild günlük iletilerini sonra bu dosyadan alınabilir.

- Ayarlama `LiveUnitTesting_TestPlatformLog` kullanıcı ortam değişkenine `1` Test Platform günlüğüne yakalamak için. Canlı birim testi çalışmalarını ayrıntılı Test Platform günlük iletilerden sonra alınabileceği `[Solution Root]\.vs\[Solution Name]\log\[VisualStudio Process ID]`.

- Adlı bir kullanıcı düzeyinde ortam değişkeni oluşturun `VS_UTE_DIAGNOSTICS` ve 1 olarak ayarlayın (veya herhangi bir değer) ve Visual Studio'yu yeniden başlatın. Artık günlüğüne çok sayıda görmelisiniz **çıktısı - testleri** Visual Studio sekmesindedir.

## <a name="see-also"></a>Ayrıca bkz.

[Canlı Birim Testi](live-unit-testing.md)

