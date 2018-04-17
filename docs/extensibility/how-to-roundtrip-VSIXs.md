---
title: 'Nasıl yapılır: Visual Studio için gidiş dönüş uzantıları | Microsoft Docs'
ms.custom: ''
ms.date: 06/25/2017
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 2d6cf53c-011e-4c9e-9935-417edca8c486
author: willbrown
ms.author: willbrown
manager: justinclareburt
ms.workload:
- willbrown
ms.openlocfilehash: 9d8d0dc2e5c8c95b5f2502ef5a48e6f97c26e289
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-make-extensions-compatible-with-visual-studio-2017-and-visual-studio-2015"></a>Nasıl yapılır: uzantıları Visual Studio 2017 ve Visual Studio 2015 ile uyumlu hale getirin

Bu belgede genişletilebilirlik projeleri Visual Studio 2015 ve Visual Studio 2017 gidiş dönüş nasıl oluşturulacağı açıklanmaktadır. Bu yükseltme işlemini tamamladıktan sonra proje açabilir, yapı, yükleyin ve Visual Studio 2015 ve Visual Studio 2017 çalışır olacaktır.  Bir başvuru olarak, Visual Studio 2015 ve Visual Studio 2017 arasındaki gidiş için bazı uzantılar bulunabilir [burada](https://github.com/Microsoft/VSSDK-Extensibility-Samples) Microsoft'un genişletilebilirlik örneklerde.

Yalnızca Visual Studio 2017 oluşturmak istiyor, ancak Visual Studio 2015 ve Visual Studio 2017 çalıştırmak için VSIX çıkış yapmak istiyorsanız, ardından [uzantısı geçiş belge](how-to-migrate-extensibility-projects-to-visual-studio-2017.md).

>**Not:** sürümleri arasında Visual Studio'da değişiklikler nedeniyle, başka bir sürümünde çalışan bazı şeyleri çalışmaz. Erişmeye çalıştığınız özellikler her iki sürümde de kullanılabilir uzantısına sahip olacaktır emin olun veya beklenmeyen sonuçlar.

Anahat gidiş bir VSIX için bu belgedeki tamamlamak adımları şöyledir:

1. Doğru NuGet paketlerini içeri aktarın.
2. Uzantı bildirimi güncelleştirin:
    * Yükleme hedef
    * Önkoşullar
3. CSProj güncelleştirin:
    * Güncelleştirme `<MinimumVisualStudioVersion>`.
    * Ekleme `<VsixType>` özelliği.
    * Hata ayıklama özellik ekleme `($DevEnvDir)` 3 kez.
    * Derleme araçları ve hedefleri içe aktarmak için koşulları ekleyin.

4. Derleme ve Test

## <a name="environment-setup"></a>Ortam Kurulumu

Bu belge aşağıdaki makinenize yüklü olduğunu varsayar:

* Visual Studio 2015 VS yüklü SDK'sı
* Visual Studio 2017 yüklü genişletilebilirlik iş yükü ile

## <a name="recommended-approach"></a>Önerilen yaklaşım

Visual Studio 2017 yerine Visual Studio 2015 ile bu yükseltme işlemini başlatmak için önerilir. Visual Studio 2015'te geliştirme ana faydası, Visual Studio 2015'te kullanılamaz derlemeleri başvurmadığından emin olmaktır. Visual Studio 2017 geliştirme bunu yaparsanız, yalnızca Visual Studio 2017 mevcut bir derleme bağımlılığını yapabilecek riski yoktur.

## <a name="ensure-there-is-no-reference-to-projectjson"></a>Project.json hiçbir başvuru olduğundan emin olun.

Bu belgenin sonraki bölümlerinde biz koşullu alma deyimlerinde *.csproj dosyanıza ekleyin.  NuGet başvurularını project.json depolanıyorsa çalışmaz. Bu nedenle, tüm NuGet başvurularını packages.config dosyasına taşımak için önerilir.
Projeniz project.json dosyası içeriyorsa:

* Project.json içinde başvuruları bir not alın.
* Çözüm Gezgini'nde, proje project.json dosyadan silin.
    * Bu project.json dosyası silecek ve bu projeden kaldırmak.
* NuGet başvurularını projeye geri ekleyin.
    * Çözüm üzerinde sağ tıklatın ve seçin **çözüm için NuGet paketlerini Yönet...**
    * Visual Studio otomatik olarak packages.config dosyasına sizin için oluşturur

>**Not:** projenizi EnvDTE paketler içeriyorsa, bunlar sağ tıklayarak eklenmesi gerekebilir **başvuruları** seçme **başvuru ekleme** ve uygun başvurusu ekleniyor.  NuGet paketlerini kullanarak projenize oluşturmaya çalışırken hatalar oluşturabilir.

## <a name="adding-appropriate-build-tools"></a>Uygun derleme araçları ekleme

Biz emin olmak için bize oluşturmak ve uygun şekilde hata ayıklamak sağlayacak derleme araçları eklemeniz gerekir. Microsoft, bu çağrılan Microsoft.VisualStudio.Sdk.BuildTasks için derlemeyi oluşturmuştur.

Derleme ve Visual Studio 2015 ve 2017 VSIXv3 dağıtmak için aşağıdaki NuGet paketlerini gerektirir:

Sürüm | Yerleşik araçları
--- | ---
Visual Studio 2015 | Microsoft.VisualStudio.Sdk.BuildTasks.14.0
Visual Studio 2017 | Microsoft.VSSDK.BuildTool

Bunu yapmak için:

* Microsoft.VisualStudio.Sdk.BuildTasks.14.0 NuGet paketini projenize ekleyin.
* Projeniz Microsoft.VSSDK.BuildTools içermiyorsa ekleyin.
* Microsoft.VSSDK.BuildTools sürüm 15.x olduğundan emin olun veya daha büyük.

## <a name="update-extension-manifest"></a>Uzantı bildirimi güncelleştir

### <a name="1-installation-targets"></a>1. Yükleme hedefleri

Visual Studio bir VSIX oluşturmak için hedeflemek için hangi sürümlerinin bildirmeniz gerekir.  Genellikle, bu başvuruları sürüm 14.0 (Visual Studio 2015) veya sürüm 15.0 (Visual Studio 2017) ' dir.  Örneğimizde, her iki sürümünü de hedeflemek ihtiyacımız böylece her ikisi için bir uzantı yükleyecek bir VSIX yapı istiyoruz.  Derleme ve 14.0'den önceki sürümlerinde yüklemek için VSIX istiyorsanız, bu önceki sürüm numarası ayarlayarak yapılabilir; Ancak, 10.0 ve önceki sürümü artık desteklenmiyor.

* Source.extension.vsixmanifest dosyasını Visual Studio'da açın.
* Açık **yükleme hedefleri** sekmesi.
* Değişiklik **sürüm aralığı** için [14,0, 16.0).  ' [', Önceki 14,0 ve tüm sürümleri dahil etmek için Visual Studio söyler.  ')' 15.0 kadar ancak sürüm 16,0 dahil değil'in tüm sürümleri dahil etmek için Visual Studio söyler.
* Tüm değişiklikleri kaydedin ve Visual Studio tüm örneklerini kapatın.

![Yükleme hedefleri görüntüsü](media/visual-studio-installation-targets-example.png)

### <a name="2-adding-prerequisites-to-the-extensionvsixmanifest-file"></a>2. Önkoşullar extension.vsixmanifest dosyasına ekleme

Önkoşullar, Visual Studio 2017 ile yeni bir özelliktir.  Bu durumda, Visual Studio çekirdek Düzenleyicisi bir önkoşul olarak ihtiyacımız var. Visual Studio 2015 VSIX Tasarımcısı yeni işlemedi bu yana `Prerequisites` bölümü, bu bölümünde el ile XML kodunu düzenle gerekir.  Alternatif olarak, Visual Studio 2017 açın ve güncelleştirilmiş bildirim tasarımcısını önkoşulları eklemek için kullanın.

Bunu el ile yapmak için:

* Dosya Gezgini'nde proje dizinine gidin.
* Açık `extension.vsixmanifest` dosyasını bir metin düzenleyicisiyle.
* Aşağıdaki etiketi ekleyin:

```xml
<Prerequisites>
    <Prerequisite Id="Microsoft.VisualStudio.Component.CoreEditor" Version="[15.0,16.0)" DisplayName="Visual Studio core editor" />
</Prerequisites>
```

* Dosyayı kaydedin ve kapatın.

>**Not:** bunu Visual Studio 2017 VSIX tasarımcısında ile gerçekleştirmek seçerseniz, tüm Visual Studio 2017 sürümleriyle uyumlu olduğundan emin olmak için önkoşul sürümü el ile düzenlemeniz gerekir.  Tasarımcı en düşük sürüm geçerli Visual Studio (örneğin, 15.0.26208.0) sürümü olarak ekleyecek olmasıdır.  Ancak, diğer kullanıcıların önceki bir sürümü olduğundan, bu bu el ile düzenleme istersiniz 15.0 için.

Bu noktada, bildirim dosyası aşağıdakine benzer görünmelidir:

![Önkoşullar örneği](media/visual-studio-prerequisites-example.png)

## <a name="modify-the-project-file-myprojectcsproj"></a>Proje dosyası (myproject.csproj) değiştirme

Bu adımı yaparken açık bir değiştirilmiş .csproj başvuru olması önerilir.  Çeşitli örnekler bulabilirsiniz [burada](https://github.com/Microsoft/VSSDK-Extensibility-Samples).  Herhangi bir genişletilebilirlik örnek seçin, başvuru .csproj dosyasını bulun ve aşağıdaki adımları çalıştırın:

* Dosya Gezgini'nde proje dizinine gidin.
* Myproject.csproj dosyasını bir metin düzenleyicisiyle açın.

### <a name="1-update-the-minimumvisualstudioversion"></a>1. Güncelleştirme MinimumVisualStudioVersion

* Minimum visual studio sürümü kümesine `$(VisualStudioVersion)` ve bir koşul deyimi ekleyin.  Bunlar yoksa bu etiketler ekleyin.  Etiketler aşağıdaki gibi ayarlandığından emin olun:

```xml
<VisualStudioVersion Condition="'$(VisualStudioVersion)' == ''">14.0</VisualStudioVersion>
<MinimumVisualStudioVersion>$(VisualStudioVersion)</MinimumVisualStudioVersion>
```

### <a name="2-add-the-vsixtype-property"></a>2. VsixType özellik ekleme

* Bu etiket ekleme `<VsixType>v3</VsixType>` özelliği gruba.

>**Not:** bu eklemek için önerilen aşağıda `<OutputType></OutputType>` etiketi.

### <a name="3-add-the-debugging-properties"></a>3. Hata ayıklama özellikleri ekleyin

* Aşağıdaki özellik grubu ekleyin:

```xml
<PropertyGroup>
    <StartAction>Program</StartAction>
    <StartPrograms>$(DevEnvDir)devenv.exe</StartPrograms>
    <StartArguments>/rootsuffix Exp</StartArguments>
</PropertyGroup>
```

* Aşağıdaki tüm örneklerini silmek .csproj dosya ve herhangi. csproj.user dosyaları:

```xml
<StartAction>Program</StartAction>
<StartPrograms>$(ProgramFiles)\Microsoft Visual Studio 14.0\Common7\IDE\devenv.exe</StartPrograms>
<StartArguments>/rootsuffix Exp</StartArguments>
```

### <a name="4-add-conditions-to-the-build-tools-imports"></a>4. Derleme araçları içeri aktarmalar için koşulları ekleme

* İçin ek koşullu ifadeler eklemek `<import>` Microsoft.VSSDK.BuildTools başvuru yapıyor etiketler.  Ekleyerek bunu `'$(VisualStudioVersion)' != '14.0' And` ön koşul deyimi kısmında.  Bu ifadeler, üstbilgi ve altbilgi csproj dosyasının görünür.

Örneğin:

```xml
<Import Project="packages\Microsoft.VSSDK.BuildTools.15.0.26201…" Condition="'$(VisualStudioVersion)' != '14.0' And Exists(…" />
```

* İçin ek koşullu ifadeler eklemek `<import>` bir Microsoft.VisualStudio.Sdk.BuildTasks.14.0 sahip etiketler.  Ekleyerek bunu `'$(VisualStudioVersion)' == '14.0' And` ön koşul deyimi kısmında. Bu ifadeler, üstbilgi ve altbilgi csproj dosyasının görünür.

Örneğin:

```xml
<Import Project="packages\Microsoft.VisualStudio.Sdk.BuildTasks.14.0.14.0…" Condition="'$(VisualStudioVersion)' == '14.0' And Exists(…" />
```

* İçin ek koşullu ifadeler eklemek `<Error>` Microsoft.VSSDK.BuildTools başvuru yapıyor etiketler.  Ekleyerek bunu `'$(VisualStudioVersion)' != '14.0' And` ön koşul deyimi kısmında. Bu deyimler csproj dosya altbilgisinde görünür.

Örneğin:

```xml
<Error Condition="'$(VisualStudioVersion)' != '14.0' And Exists('packages\Microsoft.VSSDK.BuildTools.15.0.26201…" />
```

* İçin ek koşullu ifadeler eklemek `<Error>` bir Microsoft.VisualStudio.Sdk.BuildTasks.14.0 sahip etiketler.  Ekleyerek bunu `'$(VisualStudioVersion)' == '14.0' And` ön koşul deyimi kısmında. Bu deyimler csproj dosya altbilgisinde görünür.

Örneğin:

```xml
<Error Condition="'$(VisualStudioVersion)' == '14.0' And Exists('packages\Microsoft.VisualStudio.Sdk.BuildTasks.14.0.14.0…" />
```

* Csproj dosyayı kaydedin ve kapatın.

## <a name="test-the-extension-installs-in-visual-studio-2015-and-visual-studio-2017"></a>Visual Studio 2015 ve Visual Studio 2017 uzantısı yüklemelerini test

Bu noktada, projeniz Visual Studio 2015 ve Visual Studio 2017'yükleyebilirsiniz VSIXv3 oluşturmak hazır olmanız gerekir.

* Visual Studio 2015'te projenizi açın
* Projenizi derleme ve onaylayın bir VSIX doğru derlemeler çıkışı
* Proje dizinine gidin
* Açık depo -> hata ayıklama klasörü
* VSIX dosyasına çift tıklayın ve uzantınızın Visual Studio 2015 ve Visual Studio 2017 yükleyin
* Araçlar -> Uzantılar ve güncelleştirmeler "Yüklü" bölümündeki uzantı gördüğünüzden emin olun.
* Çalıştır/çalışır durumda olduğunu denetlemek için uzantı kullanma girişimi

![Bir VSIX bulma](media/finding-a-VSIX-example.png)

>**Not:** projeniz Visual Studio'nun Kapat iletisi "dosya açılırken" zorla ile asılı kalırsa, proje dizinine gidin, gizli klasörlere Göster ve .vs klasörü silin.
