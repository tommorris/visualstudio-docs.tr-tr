---
title: "Visual Studio'da Python projeleri için özel menü komutlarını tanımlama | Microsoft Docs"
description: "Visual Studio'da Python proje bağlam menüsü özel komutları eklemek için proje ve hedefleri dosyaların nasıl düzenleneceğini gösterir. Komut, çalıştırılabilir program, komut dosyaları, modüller, satır içi kod parçacıkları ve PIP çağırabilirsiniz."
ms.custom: 
ms.date: 02/02/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: 
ms.topic: article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 1fa4c68b1d7dc89452376d6efc47e047f75d52d6
ms.sourcegitcommit: 06cdc1651aa7f45e03d260080da5a623d6258661
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2018
---
# <a name="defining-custom-commands-for-python-projects"></a>Özel komutlar Python projeleri için tanımlama

Python projelerinizi çalışma sürecinde, bulabilirsiniz kendiniz özel komut dosyaları veya modüllerini çalıştırmak için bir komut penceresi Geçiş PIP komutları çalıştırmak veya diğer bir rastgele aracını çalıştırın. İş akışınızı artırmak için özel komutlar ekleyebilirsiniz **Python** Python proje bağlam menüsünde alt. Bu komutları bir konsol penceresi veya Visual Studio çıktı penceresinde çalıştırabilirsiniz. Visual Studio hataları ve Uyarıları komutun çıktısından ayrıştırmayı istemek için normal ifadeler de kullanabilirsiniz.

Varsayılan olarak, yalnızca tek menüye içeren **çalıştırmak Pylint** komutu:

![Python alt bir projenin bağlam menüsünde varsayılan görünümünü](media/custom-commands-default-menu.png)

Özel komutlar aynı bu bağlam menüsünde görüntülenir. Özel komutlar burada bunlar, tek tek projesi için geçerli bir proje dosyası doğrudan eklenir. Özel komutlar da tanımlayabilirsiniz bir `.targets` kolayca birden çok proje dosyalarını aktarılabilen dosya.

Visual Studio'da belirli Python proje şablonları zaten kullanarak kendi özel komutlar ekleme kendi `.targets` dosya. Örneğin, iki komut Bottle Web projesi ve Flask Web projesi şablonları ekleyin **başlangıç sunucu** ve **başlangıç hata ayıklama sunucusunun**. Django Web projesi şablonunu aynı komutlar artı oldukça birkaç daha fazlasını ekler:

![Python alt bir Django projesinin bağlam menüsünden görünümü](media/custom-commands-django-menu.png)

Her özel komut Python dosyası, bir Python modülü, satır içi Python kodu, rasgele bir yürütülebilir dosya veya bir PIP komutu başvurabilir. Ayrıca, nasıl ve nerede komutu çalıştırır belirtebilirsiniz.

> [!Tip]
> Proje dosyası bir metin düzenleyicisinde değişiklik olduğunda, bu değişiklikleri uygulamak için Visual Studio'da projeyi yeniden yüklemek gereklidir. Örneğin, bu komutları projenin bağlam menüsünde görünmesi için özel komut tanımları ekledikten sonra bir projeyi yeniden yüklemelisiniz.
>
> Bildiğiniz gibi Visual Studio Proje dosyasını doğrudan düzenlemek için bir yol sağlar. İlk proje dosyasını sağ tıklatın ve seçin **projeyi**, daha sonra tekrar sağ tıklayın ve seçin **(proje adı) düzenleme** projeyi Visual Studio düzenleyicisinde açın. Ardından yapabilir ve düzenlemeleri kaydetmek, projeye bir kez daha sağ tıklayın ve seçin **projeyi yeniden yükle**, hangi da sizden Düzenleyicisi proje dosyasında kapatmayı onaylamak için.
>
> Ancak, özel bir komut geliştirirken, bu tıklama can sıkıcı olabilir. Daha verimli bir iş akışı için Visual Studio Proje yüklenecek ve açmak için ayrıca `'.pyproj` ayrı bir düzenleyicide tamamen (başka bir örneği Visual Studio, Visual Studio Code, Not Defteri, vb. gibi.) dosyası. Düzenleyici ve Visual Studio anahtara değişiklikleri kaydettiğinizde, Visual Studio değişiklikleri algılar ve projeyi yeniden yüklemek üzere getirip getirmemeyi sorar ("(ad) proje ortamı dışında değiştirildi."). Seçin **yeniden** ve değişikliklerinizi tek bir adımda hemen uygulanır.

## <a name="walkthrough-add-a-command-to-a-project-file"></a>İzlenecek yol: Proje dosyası için bir komut ekleme

Özel komutlar ile tanımak için bu bölümde Python.exe'yi kullanarak doğrudan bir projenin başlangıç dosyasını çalıştıran basit bir örnek anlatılmaktadır. (Bu tür bir komut etkili bir şekilde kullanarak aynıdır **hata ayıklama > hata ayıklama olmadan Başlat**.)

1. "" Python uygulama"şablonu ile Python-CustomCommands" adlı yeni bir proje oluşturun. (Bkz [hızlı başlangıç: bir şablondan bir Python projesi oluşturma](quickstart-02-project-from-template.md) , zaten işlemle bilmiyorsanız yönergeler için.)

1. İçinde `Python_CustomCommands.py`, aşağıdaki kodu ekleyip `print("Hello custom commands")`.

1. ' Nde projeye sağ **Çözüm Gezgini**seçin **Python**ve alt menüde görünür yalnızca komutu olduğuna dikkat edin **çalıştırmak PyLint**. Özel komutlar, bu aynı alt menüsünde görüntülenir.

1. Önerildiği gibi giriş, açık `Python-CustomCommands.pyproj` ayrı bir metin düzenleyicisinde. Kapatma içindeki yalnızca dosyanın sonuna şu satırları ekleyin `</Project>` ve dosyayı kaydedin.

    ```xml
    <PropertyGroup>
      <PythonCommands>
        $(PythonCommands);
      </PythonCommands>
    </PropertyGroup>
    ```

1. Visual Studio'ya geri geçiş yapın ve seçin **yeniden** zaman, sizden dosya değişikliği hakkında. Ardından denetleyin **Python** yeniden görüp menü **çalıştırmak PyLint** olmasına rağmen yalnızca eklediğiniz satırları varsayılan çoğaltıldığından var. gösterilen tek öğe `<PythonCommands>` PyLint içeren özellik grubu komutu.

1. Proje dosyası ile düzenleyiciye geçin ve aşağıdakileri ekleyin `<Target>` sonra tanımı `<PropertyGroup>`. Bu makalenin sonraki bölümlerinde açıklandığı gibi bu `Target` öğesi tanımlar başlangıç ("StartupFile" özelliği tarafından tanımlanan) dosyası kullanarak çalıştırmak için özel bir komut `python.exe` bir konsol penceresinde. Öznitelik `ExecuteIn="consolepause"` kapatmadan önce bir tuşa basın bekler bir konsol kullanır.

    ```xml
    <Target Name="Example_RunStartupFile" Label="Run startup file" Returns="@(Commands)">
      <CreatePythonCommandItem
        TargetType="script"
        Target="$(StartupFile)"
        Arguments=""
        WorkingDirectory="$(MSBuildProjectDirectory)"
        ExecuteIn="consolepause">
        <Output TaskParameter="Command" ItemName="Commands" />
      </CreatePythonCommandItem>
    </Target>
    ```

1. Hedefin değeri eklemek `Name` özniteliğini `<PythonCommands>` öğesi kod gibi tanıyarak daha önce eklenen özellik grubu. Hedef adını bu listeye eklemek olduğu ona ekler **Python** menüsü.

    ```xml
      <PythonCommands>
        $(PythonCommands);
        Example_RunStartupFile
      </PythonCommands>
    ```

    İçinde tanımlanan önce görünmesi komutunuzu isteyip istemediğinizi `$(PythonCommands)`, önce bu belirtece yerleştirmek.

1. Proje dosyasını kaydedin, Visual Studio'ya geçin ve istendiğinde projeyi yeniden yükleyin. Ardından "Python-CustomCommands" projesine sağ tıklatın ve **Python**. Görmeniz gerekir bir **başlangıç dosyasını çalıştırıp** menüsündeki öğesi. Menü öğesi görmüyorsanız adına eklenen denetleyin `<PythonCommands>` öğesi. Ayrıca bkz. [sorun giderme](#troubleshooting) bu makalenin ilerisinde yer.

    ![Python bağlam menüdeki görünen özel komutu](media/custom-commands-walkthrough-menu-item.png)

1. Seçin **başlangıç dosyasını çalıştırıp** komutunu ve "Merhaba özel komutlar ve ardından" metnini "devam etmek için tüm tuşuna basın. görünür bir komut penceresi görmeniz gerekir biçimindeki telefon numarasıdır. .".  Pencereyi kapatmak için bir tuşa basın.

    ![Bir konsol penceresi özel komut çıktısında](media/custom-commands-walkthrough-console.png)

1. Proje dosyası ile Düzenleyiciye dönmek ve değerini değiştirmek `ExecuteIn` özniteliğini `output`. Dosyayı kaydedin, Visual Studio'ya geçiş, projeyi yeniden yükleyin ve komutu yeniden çağırma. Bkz: program, çıktı görünür Visual Studio'nun bu saati **çıkış** penceresi:

    ![Çıktı penceresinde özel komut çıktısı](media/custom-commands-walkthrough-output-window.png)

1. Daha fazla komut eklemek için uygun bir tanımlamak `<Target>` her komut öğesi Ekle hedef adını `<PythonCommands>` özellik grubu ve Visual Studio'da projeyi yeniden yükle.

>[!Tip]
> Kullanır gibi özellikleri, proje bir komutunu Çağır varsa `($StartupFile)`ve belirteci tanımsız olduğundan komut başarısız olursa, Visual Studio devre dışı bırakır komutu projeyi yeniden yüklemek kadar. Hala bu gibi durumlarda projeyi yeniden yüklemek gereken şekilde özelliği tanımlarsınız projeye değişiklikler, ancak, bu komutları durumunu yenilemez.

## <a name="command-target-structure"></a>Komut hedefi yapısı

Genel biçiminde `<Target>` öğesi aşağıdaki sözde kodda gösterilir:

```xml
<Target Name="Name1" Label="Display Name" Returns="@(Commands)">
    <CreatePythonCommandItem Target="filename, module name, or code"
        TargetType="executable/script/module/code/pip"
        Arguments="..."
        ExecuteIn="console/consolepause/output/repl[:Display name]/none"
        WorkingDirectory="..."
        ErrorRegex="..."
        WarningRegex="..."
        RequiredPackages="...;..."
        Environment="...">

      <!-- Output always appears in this form, with these exact attributes -->
      <Output TaskParameter="Command" ItemName="Commands" />
    </CreatePythonCommandItem>
  </Target>
```

Proje özellikleri veya öznitelik değerlerini ortam değişkenleri için ad içinde kullanın bir `$()` belirteci gibi `$(StartupFile)` ve `$(MSBuildProjectDirectory)`. Daha fazla bilgi için bkz: [MSBuild özellikleri](../msbuild/msbuild-properties.md).

### <a name="target-attributes"></a>Hedef öznitelikleri

| Öznitelik | Gerekli | Açıklama |
| --- | --- | --- |
| Ad | Evet | Visual Studio projesi içindeki komut tanımlayıcısı. Bu ad eklenmeli `<PythonCommands>` komutu Python menüdeki görünmesi için özellik grubu. |
| Etiketle | Evet | Python alt menüsünde görünür UI görünen adı. |
| Döndürür | Evet | İçermelidir `@(Commands)`, hedef bir komut olarak tanımlar. |

### <a name="createpythoncommanditem-attributes"></a>CreatePythonCommandItem attributes

Tüm öznitelik değerleri büyük/küçük harfe duyarsızdır.

| Öznitelik | Gerekli | Açıklama |
| --- | --- | --- |
| TargetType | Evet | Hangi hedef öznitelik içerir ve bağımsız değişkenler özniteliği ile birlikte nasıl kullanıldığını belirtir:<ul><li>**yürütülebilir**: bağımsız değişken değeri doğrudan komut satırında girdiyseniz gibi ekleme hedef adlı yürütülebilir dosyayı çalıştırmak. Değer bağımsız değişkenler olmadan yalnızca bir program adı içermelidir.</li><li>**komut dosyası**: çalıştırmak `python.exe` ile hedef dosya adını, ardından bağımsız değişkenleri değere sahip.</li><li>**Modül**: çalıştırmak `python -m` bağımsız değişkenleri değere sahip ve ardından hedef, modül adı ve ardından.</li><li>**kod**: hedef bulunan satır içi kod çalıştırın. Bağımsız değişken değeri yoksayılır.</li><li>**PIP**: çalıştırmak `pip` ExecuteIn ", ancak, PIP varsayar çıktısını almak için" ayarlanmış komut bağımsız değişkenleri tarafından; ardından hedefi içinde olduğu `install` komut ve hedef olarak paket adını kullanır.</li></ul> |
| Hedef | Evet | Dosya adı, modül adı, kod veya TargetType bağlı olarak kullanılacak PIP komutu. |
| Arguments | İsteğe Bağlı | Bir dize bağımsız değişkenleri, hedef vermek için (varsa) belirtir. TargetType olduğunda unutmayın `script`, bağımsız değişkenler Python programına verilmedi `python.exe`. İçin göz ardı `code` TargetType. |
| ExecuteIn | Evet | Komutu çalıştırmak üzere ortam belirtir:<ul><li>**Konsol**: (varsayılan), hedef ve bağımsız değişkenler doğrudan komut satırında girilirse gibi çalışır. Hedef çalıştığından, sonra otomatik olarak kapatılır sırasında bir komut penceresi görünür.</li><li>**consolepause**: aynı bir konsol ancak bekler keypress için pencereyi önce.</li><li>**Çıktı**: çalıştırır hedef ve Visual Studio çıktı penceresinde sonuçlarını görüntüler. TargetType "PIP" ise, Visual Studio Paket adı olarak hedef kullanır ve bağımsız değişkenleri ekler.</li><li>**REPL**: çalıştırır hedef [Python etkileşimli pencere](interactive-repl.md); penceresinin başlık için kullanılan isteğe bağlı görünen adı.</li><li>**Hiçbiri**: konsolu ile aynı şekilde davranır.</li></ul>|
| Başlangıç | İsteğe Bağlı | Komutu çalıştırmak için klasör. |
| ErrorRegex<br>WarningRegEx | İsteğe Bağlı | Yalnızca ExecuteIn olduğunda kullanılan `output`. Her iki değerin ile Visual Studio komut çıktısı hataları ve Uyarıları, hata listesi penceresini göster ayrıştırmak için normal bir ifadeyi belirtin. Belirtilmezse, komut hata listesi penceresini etkilemez. Bekliyor hangi Visual Studio hakkında daha fazla bilgi için bkz: [adlandırılmış yakalama grupları](#named-capture-groups-for-regular-expression). |
| RequiredPackages | İsteğe Bağlı | Bir paket için gereksinimleri listesi ile aynı biçimi kullanarak komutu [requirements.txt](https://pip.readthedocs.io/en/1.1/requirements.html) (pip.readthedocs.io). **Çalıştırmak PyLint** komutu, örneğin belirtir `pylint>=1.0.0`. Komutu çalıştırmadan önce Visual Studio listedeki tüm paketleri yüklü olup olmadığını denetler. Visual Studio PIP herhangi eksik paketleri yüklemek için kullanır. |
| Ortam | İsteğe Bağlı | Komutu çalıştırmadan önce tanımlamak için ortam değişkenleri dizesi. Her bir değişken adı biçiminde kullanan noktalı virgülle ayırarak birden çok değişkenleriyle = değer. Birden çok değere sahip bir değişken tek veya çift tırnak içine olarak yer almalıdır ' NAME = VALUE1; VALUE2'. |

#### <a name="named-capture-groups-for-regular-expressions"></a>Normal ifadeler için adlandırılmış yakalama grupları

Visual Studio, hata ve uyarıların bir komutun çıktısından ayrıştırılırken bekliyor normal ifadelerde `ErrorRegex` ve `WarningRegex` adlandırılmış gruplar aşağıdaki değerleri kullanın:

- `(?<message>...)`: Hata metni
- `(?<code>...)`: Hata kodu
- `(?<filename>...)`: Bildirilen hata için dosyasının adı
- `(?<line>...)`: Kendisi için hata bildirdi dosya konumu satır sayısı.
- `(?<column>...)`: Kendisi için hata bildirdi dosya konumu sütun sayısı.

Örneğin, PyLint aşağıdaki biçimde uyarılar üretir:

```output
************* Module hello
C:  1, 0: Missing module docstring (missing-docstring)
```

Bu tür uyarılar doğru bilgileri ayıklamak ve bunları göstermek Visual Studio izin vermek için **hata listesi** penceresinde `WarningRegex` değerini **çalıştırmak Pylint** komut aşağıdaki gibidir:

```regex
^(?<filename>.+?)\((?<line>\d+),(?<column>\d+)\): warning (?<msg_id>.+?): (?<message>.+?)$]]
```

(Unutmayın `msg_id` değeri gerçekte olmalıdır `code`, bkz: [sorunu 3680](https://github.com/Microsoft/PTVS/issues/3680).)

## <a name="creating-a-targets-file-with-custom-commands"></a>Bir .targets dosyasında özel komutları ile oluşturma

Özel komutlar proje dosyasında tanımlama yalnızca bu proje dosyası için kullanılabilir hale getirir. Birden çok proje dosyasında komutlarını kullanmak için bunun yerine tanımladığınız `<PythonCommands>` özellik grubunu ve tüm, `<Target>` öğelerinde bir `.targets` dosyası. Bu dosya daha sonra her bir proje dosyalarına alın.

`.targets` Dosya şu şekilde biçimlendirilmiş:

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <PropertyGroup>
    <PythonCommands>
      $(PythonCommands);
      <!-- Additional command names -->
    </PythonCommands>
  </PropertyGroup>

  <Target Name="..." Label="..." Returns="@(Commands)">
    <!-- CreatePythonCommandItem and Output elements... -->
  </Target>

  <!-- Any number of additional Target elements-->
</Project>
```

Yüklemek için bir `.targets` dosya bir projeye, yerleştirin bir `<Import Project="(path)">` öğe içinde herhangi bir yere `<Project>` öğesi. Örneğin, adlı bir dosyanız varsa `CustomCommands.targets` içinde bir `targets` alt projenizdeki şu kodu kullanın:

```xml
<Import Project="targets/CustomCommands.targets"/>
```

> [!Note]
> Değiştirdiğiniz her `.targets` dosyası, yeniden yüklemek için ihtiyacınız *çözüm* proje kendisi yalnızca bir proje içerir.

## <a name="example-commands"></a>Örnek komutlar

### <a name="run-pylint-module-target"></a>Çalışma PyLint (modül hedefi)

Aşağıdaki kodda gösterildiği `Microsoft.PythonTools.targets` dosyası:

```xml
<PropertyGroup>
  <PythonCommands>$(PythonCommands);PythonRunPyLintCommand</PythonCommands>
  <PyLintWarningRegex>
    <![CDATA[^(?<filename>.+?)\((?<line>\d+),(?<column>\d+)\): warning (?<msg_id>.+?): (?<message>.+?)$]]>
  </PyLintWarningRegex>
</PropertyGroup>

<Target Name="PythonRunPyLintCommand"
        Label="resource:Microsoft.PythonTools.Common;Microsoft.PythonTools.Common.Strings;RunPyLintLabel"
        Returns="@(Commands)">
  <CreatePythonCommandItem Target="pylint.lint"
                           TargetType="module"
                           Arguments="&quot;--msg-template={abspath}({line},{column}): warning {msg_id}: {msg} [{C}:{symbol}]&quot; -r n @(Compile, ' ')"
                           WorkingDirectory="$(MSBuildProjectDirectory)"
                           ExecuteIn="output"
                           RequiredPackages="pylint&gt;=1.0.0"
                           WarningRegex="$(PyLintWarningRegex)">
    <Output TaskParameter="Command" ItemName="Commands" />
  </CreatePythonCommandItem>
</Target>
```

### <a name="run-pip-install-with-a-specific-package-pip-target"></a>Belirli bir paket (PIP hedef) ile pip yüklemeyi çalıştırması

Şu komutu çalıştırır `pip install my-package` çıktı penceresinde. Böyle bir komuta ne zaman gibi kullanabilir bir paket geliştirme ve test etme, yükleme. Hedef paket adı içerdiğini unutmayın yerine `install` kullanırken varsayılır komutu `ExecuteIn="output"`.

```xml
<PropertyGroup>
  <PythonCommands>$(PythonCommands);InstallMyPackage</PythonCommands>
</PropertyGroup>

<Target Name="InstallMyPackage" Label="pip install my-package" Returns="@(Commands)">
  <CreatePythonCommandItem Target="my-package" TargetType="pip" Arguments=""
    WorkingDirectory="$(MSBuildProjectDirectory)" ExecuteIn="output">
    <Output TaskParameter="Command" ItemName="Commands" />
  </CreatePythonCommandItem>
</Target>
```

### <a name="show-outdated-pip-packages-pip-target"></a>Eski Göster PIP paketleri (PIP hedef)

```xml
<PropertyGroup>
  <PythonCommands>$(PythonCommands);ShowOutdatedPackages</PythonCommands>
</PropertyGroup>

<Target Name="ShowOutdatedPackages" Label="Show outdated pip packages" Returns="@(Commands)">
  <CreatePythonCommandItem Target="list" TargetType="pip" Arguments="-o --format columns"
    WorkingDirectory="$(MSBuildProjectDirectory)" ExecuteIn="consolepause">
    <Output TaskParameter="Command" ItemName="Commands" />
  </CreatePythonCommandItem>
</Target>
```

### <a name="run-an-executable-with-consolepause"></a>Consolepause ile yürütülebilir bir dosyayı çalıştırmayı

Aşağıdaki komut yalnızca çalışır `where` proje klasöründe başlangıç Python dosyaları göstermek için:

```xml
<PropertyGroup>
  <PythonCommands>$(PythonCommands);ShowAllPythonFilesInProject</PythonCommands>
</PropertyGroup>

<Target Name="ShowAllPythonFilesInProject" Label="Show Python files in project" Returns="@(Commands)">
  <CreatePythonCommandItem Target="where" TargetType="executable" Arguments="/r . *.py"
    WorkingDirectory="$(MSBuildProjectDirectory)" ExecuteIn="output">
    <Output TaskParameter="Command" ItemName="Commands" />
  </CreatePythonCommandItem>
</Target>
```

### <a name="run-server-and-run-debug-server-commands"></a>Sunucu ve çalışma hata ayıklama server komutlarını çalıştırın

Keşfetmek için nasıl **başlangıç sunucu** ve **başlangıç hata ayıklama sunucusunun** web projeleri tanımlanan için komutları inceleyin [Microsoft.PythonTools.Web.targets](https://github.com/Microsoft/PTVS/blob/master/Python/Product/BuildTasks/Microsoft.PythonTools.Web.targets) (GitHub).

### <a name="install-package-for-development"></a>Geliştirme için paketini yükle

```xml
<PropertyGroup>
  <PythonCommands>PipInstallDevCommand;$(PythonCommands);</PythonCommands>
</PropertyGroup>

<Target Name="PipInstallDevCommand" Label="Install package for development" Returns="@(Commands)">
    <CreatePythonCommandItem Target="pip" TargetType="module" Arguments="install --editable $(ProjectDir)"
        WorkingDirectory="$(WorkingDirectory)" ExecuteIn="Repl:Install package for development">
      <Output TaskParameter="Command" ItemName="Commands" />
    </CreatePythonCommandItem>
  </Target>
```

*Gelen [fxthomas/Example.pyproj.xml](https://gist.github.com/fxthomas/5c601e3e0c1a091bcf56aed0f2960cfa) (GitHub) izniyle kullanılır.*

### <a name="generate-windows-installer"></a>Windows Installer oluştur

```xml
<PropertyGroup>
  <PythonCommands>$(PythonCommands);BdistWinInstCommand;</PythonCommands>
</PropertyGroup>

<Target Name="BdistWinInstCommand" Label="Generate Windows Installer" Returns="@(Commands)">
    <CreatePythonCommandItem Target="$(ProjectDir)setup.py" TargetType="script"
        Arguments="bdist_wininst --user-access-control=force --title &quot;$(InstallerTitle)&quot; --dist-dir=&quot;$(DistributionOutputDir)&quot;"
        WorkingDirectory="$(WorkingDirectory)" RequiredPackages="setuptools"
        ExecuteIn="Repl:Generate Windows Installer">
      <Output TaskParameter="Command" ItemName="Commands" />
    </CreatePythonCommandItem>
  </Target>
```

*Gelen [fxthomas/Example.pyproj.xml](https://gist.github.com/fxthomas/5c601e3e0c1a091bcf56aed0f2960cfa) (GitHub) izniyle kullanılır.*

### <a name="generate-wheel-package"></a>Tekerlek paketi oluştur

```xml
<PropertyGroup>
  <PythonCommands>$(PythonCommands);BdistWheelCommand;</PythonCommands>
</PropertyGroup>

<Target Name="BdistWheelCommand" Label="Generate Wheel Package" Returns="@(Commands)">

  <CreatePythonCommandItem Target="$(ProjectDir)setup.py" TargetType="script"
      Arguments="bdist_wheel --dist-dir=&quot;$(DistributionOutputDir)&quot;"
      WorkingDirectory="$(WorkingDirectory)" RequiredPackages="wheel;setuptools"
      ExecuteIn="Repl:Generate Wheel Package">
    <Output TaskParameter="Command" ItemName="Commands" />
  </CreatePythonCommandItem>
</Target>
```

*Gelen [fxthomas/Example.pyproj.xml](https://gist.github.com/fxthomas/5c601e3e0c1a091bcf56aed0f2960cfa) (GitHub) izniyle kullanılır.*

## <a name="troubleshooting"></a>Sorun giderme

### <a name="message-the-project-file-could-not-be-loaded"></a>İleti: "proje dosyası yüklenemedi"

Proje dosyasında sözdizimi hataları sahip olduğunu gösterir. Bir satır sayısı ile ilgili hata iletisi içerir ve karakterin konumu.

### <a name="console-window-closes-immediately-after-command-is-run"></a>Hemen komutu çalıştırdıktan sonra konsol penceresini kapatır

Kullanım `ExecuteIn="consolepause"` yerine `ExecuteIn="console"`.

### <a name="command-does-not-appear-on-the-menu"></a>Komut menüsünde görünmüyor

Komutu dahil onay `<PythonCommands>` özellik grubu ve komut listesi adı belirtilen adıyla eşleşen `<Target>` öğesi.

Örneğin, aşağıdaki öğeler, hedef "ExampleCommand" adı "Örnek" adlı özellik grubundaki eşleşmiyor. Visual Studio komut yok görünmesi "Örnek" adlı bir komut bulmaz. Komut listesinde "ExampleCommand" kullanabilir veya hedef adını yalnızca "Örnek" değiştirin.

```xml
  <PropertyGroup>
    <PythonCommands>$(PythonCommands);Example</PythonCommands>
  </PropertyGroup>
  <Target Name="ExampleCommand" Label="Example Command" Returns="@(Commands)">
    <!-- ... -->
  </Target>
```

### <a name="message-an-error-occurred-while-running-command-name-failed-to-get-command-target-name-from-project"></a>İleti: (Komut adı) çalıştırılırken bir hata oluştu. Projeden komutu (hedef-name) alınamadı.

Belirten içeriğini `<Target>` veya `<CreatePythonCommandItem>` öğeleri yanlış. Olası nedenler şunlardır:

- Gerekli `Target` özniteliği boştur.
- Gerekli `TargetType` özniteliği boş veya tanınmayan bir değer içeriyor.
- Gerekli `ExecuteIn` özniteliği boş veya tanınmayan bir değer içeriyor.
- `ErrorRegex` veya `WarningRegex` ayarlamadan belirtildi `ExecuteIn="output"`.
- Tanınmayan öznitelikleri öğe yok. Örneğin, kullanmış `Argumnets` (yanlış yazılmış) yerine `Arguments`.

Öznitelik değerleri tanımlı olmayan bir özelliğe başvurursanız boş olabilir. Örneğin, belirteç kullanırsanız, `$(StartupFile)` ancak herhangi bir başlatma dosyası proje tanımlanan sonra belirteç çözümler için boş bir dize. Böyle durumlarda, varsayılan değer tanımlamak isteyebilirsiniz. Örneğin, **Server'i** ve **Run hata ayıklama sunucusu** komutları Bottle, Flask, tanımlanan ve Django proje şablonları varsayılan `manage.py` sunucu başlangıç dosyasını aksi belirtmediyseniz Proje Özellikleri'nde.

### <a name="visual-studio-hangs-and-crashes-when-running-the-command"></a>Visual Studio kilitleniyor ve komutunu çalıştırarak çöküyor

Bir konsol komutu çalıştırmak büyük olasılıkla denediğiniz `ExecuteIn="output"`, Visual Studio çıkış çözümlenemedi çalışılırken; bu durumda kilitlenebilir. Bunun yerine `ExecuteIn="console"` kullanın. (Bkz [3682 sorun](https://github.com/Microsoft/PTVS/issues/3681).)

### <a name="executable-command-is-not-recognized-as-an-internal-or-external-command-operate-program-or-batch-file"></a>Yürütülebilir "tanınmıyor bir iç ya da dış komut, program veya toplu iş dosyasını çalıştırmak"

Kullanırken `TargetType="executable"`, değer `Target` olmalıdır *yalnızca* "python" veya "Python.exe'yi" yalnızca gibi tüm bağımsız değişkenler olmadan program adı. Herhangi bir bağımsız değişkeni için taşıma `Arguments` özniteliği.
