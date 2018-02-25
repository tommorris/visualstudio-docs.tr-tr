---
title: "Yapı özelleştirebilir ve görevleri tasks.vs.json ve launch.vs.json kullanarak Visual Studio'da hata ayıklama | Microsoft Docs"
ms.date: 02/21/2018
ms.technology: vs-ide-general
ms.topic: article
helpviewer_keywords:
- NMAKE [Visual Studio]
- makefiles [Visual Studio]
- customize codebases [Visual Studio]
- tasks.vs.json file [Visual Studio]
- launch.vs.json file [Visual Studio]
- vsworkspacesettings.json file [Visual Studio]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 5d40bd35d893afeb8e76e18d46185b3d63add1c5
ms.sourcegitcommit: 3abca1c733af876c8146daa43a62e829833be280
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="customize-build-and-debug-tasks-for-open-folder-development"></a>Yapı özelleştirebilir ve görevler "Klasör Aç" geliştirme için hata ayıklama

Visual Studio birçok farklı dillerde çalıştırma bilir ve olarak kullanılabilecek kod temeli, ancak her şeyi çalıştırılacağını bilmiyor. Varsa, [kod klasörünü açılır](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md) da Visual Studio ve Visual Studio bilir nasıl kodunuzu çalıştırmak, herhangi bir ek yapılandırma hemen çalıştırabilirsiniz.

Visual Studio tanımıyor özel derleme araçları codebase kullanıyorsa, çalıştırmak ve Visual Studio kodda hata ayıklama için bazı yapılandırma ayrıntılarını sağlamanız gerekir. Visual Studio kodunuzu tanımlayarak nasıl oluşturulacağını istemeniz *derleme görevleri*. Bir tane oluşturabilirsiniz veya daha fazla dil derlemek ve kendi kod çalıştırmak için gereken tüm öğeleri belirtmek için görevler oluşturabilirsiniz. Neredeyse istediğiniz her şeyi yapabilirsiniz rasgele görevleri de oluşturabilirsiniz. Örneğin, bir klasör içeriğini listele veya bir dosyayı yeniden adlandırmak için bir görev oluşturabilirsiniz.

Özelleştirme aşağıdakileri kullanarak, daha az proje codebase *.json* dosyaları:

|Dosya adı|Amaç|
|-|-|
|*tasks.vs.json*|Özel derleme komutları ve derleyici anahtarları ve isteğe bağlı (olmayan ilgili derleme) belirtin görevler.<br>Üzerinden erişilen **Çözüm Gezgini** bağlam menüsü öğesini **yapılandırma görevleri**.|
|*launch.vs.json*|Hata ayıklama için komut satırı bağımsız değişkenleri belirtin.<br>Üzerinden erişilen **Çözüm Gezgini** bağlam menüsü öğesini **hata ayıklama ve başlatma ayarları**.|
|*VSWorkspaceSettings.json*|Görevleri etkileyebilir ve başlatma genel ayarlar. Örneğin, tanımlama `envVars` içinde *VSWorkspaceSettings.json* dışarıdan komutları çalıştırmak için belirtilen ortam değişkenlerini ekler.<br>Bu dosyayı el ile oluşturun.|

Bunlar *.json* dosyaları adlı gizli bir klasörde bulunan *.vs* temelinizde kök klasöründe. *Tasks.vs.json* ve *launch.vs.json* dosyaları oluşturulur Visual Studio tarafından gerektiği ölçüde temeline göre ya da seçtiğinizde **yapılandırma görevleri** veya **hata ayıklama ve başlatma ayarları** bir dosya veya klasörde **Çözüm Gezgini**. Bunlar *.json* dosyaları, kullanıcıların kaynak denetimine denetlemek genellikle istemediğiniz çünkü gizlidir. Ancak, kaynak denetimine denetlemek istiyorsanız, dosyaları burada görünür kod temeliniz kök sürükleyin.

> [!TIP]
> Visual Studio'da gizli dosyaları görüntülemek için seçin **tüm dosyaları göster** Çözüm Gezgini araç çubuğunda.

## <a name="define-tasks-with-tasksvsjson"></a>Tasks.vs.json görevlerle tanımlayın

Yapı komut dosyaları veya diğer dış işlemleri doğrudan IDE'de görevler olarak çalıştırarak geçerli çalışma alanınızda sahip dosyalar üzerinde otomatik hale getirebilirsiniz. Bir dosya veya klasöre sağ tıklayıp seçerek yeni bir görev yapılandırabilirsiniz **yapılandırma görevleri**.

![Görevler menüsü yapılandırın](../ide/media/customize-configure-tasks-menu.png)

Bu oluşturur (veya açar) *tasks.vs.json* dosyasını *.vs* klasör. Bu dosyada bir derleme görevi ya da rasgele görev tanımlayabilir ve ondan verdiğiniz adı kullanarak çağırma **Çözüm Gezgini** bağlam menüsü.

Özel görevler, belirli dosyaları veya belirli bir türde tüm dosyaları eklenebilir. Örneği için "Paketler geri yükleme" görev için NuGet paket dosyalarını yapılandırılabilir veya tüm linter gibi bir statik çözümleme görev için tüm kaynak dosyaları yapılandırılabilir *.js* dosyaları.

### <a name="define-custom-build-tasks"></a>Özel derleme görevleri tanımlama

Ardından temelinizde Visual Studio tanımıyor özel derleme araçları kullanıyorsa, çalıştırmak ve bazı yapılandırma adımları tamamlanana kadar Visual Studio kodda hata ayıklama olamaz. Visual Studio sağlar *derleme görevleri* nasıl oluşturulacağını Visual Studio anlayabilirsiniz burada yeniden oluşturun ve kodunuzu temizleme. *Tasks.vs.json* Visual Studio iç geliştirme döngüsü özel derleme araçlarını temelinizde tarafından kullanılan görev dosya tüm çiftler oluşturun.

Adlı bir tek C# dosyasından oluşur codebase göz önünde bulundurun *hello.cs*. Bu tür bir codebase için derleme görevleri dosyası şuna benzeyebilir:

```makefile
build: directory hello.exe

hello.exe: hello.cs
    csc -debug hello.cs /out:bin\hello.exe

clean:
    del bin\hello.exe bin\hello.pdb

rebuild: clean build

directory: bin

bin:
    md bin
```

Yapı, temiz ve yeniden hedefleri içeren bu tür bir derleme görevleri dosyası için aşağıdaki tanımlayabilirsiniz *tasks.vs.json* dosya. Oluşturma, yeniden oluşturma ve NMAKE derleme aracını kullanarak codebase Temizleme için üç derleme görevleri içerir.

```json
{
  "version": "0.2.1",
  "outDir": "\"${workspaceRoot}\\bin\"",
  "tasks": [
    {
      "taskName": "makefile-build",
      "appliesTo": "makefile",
      "type": "launch",
      "contextType": "build",
      "command": "nmake",
      "args": [ "build" ],
      "envVars": {
        "VSCMD_START_DIR": "\"${workspaceRoot}\""
      }
    },
    {
      "taskName": "makefile-clean",
      "appliesTo": "makefile",
      "type": "launch",
      "contextType": "clean",
      "command": "nmake",
      "args": [ "clean" ],
      "envVars": {
        "VSCMD_START_DIR": "\"${workspaceRoot}\""
      }
    },
    {
      "taskName": "makefile-rebuild",
      "appliesTo": "makefile",
      "type": "launch",
      "contextType": "rebuild",
      "command": "nmake",
      "args": [ "rebuild" ],
      "envVars": {
        "VSCMD_START_DIR": "\"${workspaceRoot}\""
      }
    }
  ]
}
```

Derleme görevleri tanımladıktan sonra *tasks.vs.json*, ek bağlam menüsü öğelerine, ilgili dosyaları eklenir **Çözüm Gezgini**. Bu örnek için **yapı**, **yeniden**, ve **temiz** seçenekleri herhangi bağlam menüsüne eklenen *derleme görevleri dosyası* dosyaları.

![derleme görevleri dosyası bağlam menüsü yapı ile yeniden oluşturma ve temizleme](media/customize-build-rebuild-clean.png)

> [!NOTE]
> Altında bağlam menüsündeki komutlar görünür **yapılandırma görevleri** nedeniyle komutunu kendi `contextType` ayarlar. bağlam menüsü ortasında yapı bölümdeki göründükleri şekilde "Oluştur", "yeniden" ve "temiz" yapı komutlarını verilmiştir.

Bu seçeneklerden birini seçtiğinizde, görevi yürütür. Çıktı görünür **çıkış** penceresi ve yapı hataları görünür **hata listesi**.

### <a name="define-arbitrary-tasks"></a>Rastgele görevleri tanımlama

Rastgele görevlerinde tanımlayabilirsiniz *tasks.vs.json* neredeyse istediğiniz her şeyi dosyaya,. Örneğin, şu anda seçili dosyasında adını görüntülemek için bir görev tanımlayabilirsiniz **çıkış** penceresinde veya belirtilen dizindeki dosyaların listesi.

Aşağıdaki örnekte gösterildiği bir *tasks.vs.json* tek bir görev tanımlayan dosyası. Çağrıldığında, görevi şu anda seçili filename görüntüler *.js* dosya.

```json
{
  "version": "0.2.1",
  "tasks": [
    {
      "taskName": "Echo filename",
      "appliesTo": "*.js",
      "type": "default",
      "command": "${env.COMSPEC}",
      "args": [ "echo ${file}" ]
    }
  ]
}
```

- `taskName` görünen adı bağlam menüsünde belirtir.
- `appliesTo` komut gerçekleştirilebilir hangi dosyaların belirtir.
- `command` Özelliği çağrılacak komutu belirtir. Bu örnekte, `COMSPEC` komut satırı yorumlayıcı genellikle tanımlamak için kullanılan ortam değişkeni *cmd.exe*.
- `args` Özelliği, çağrılan komut geçirilecek bağımsız değişkenler belirtir.
- `${file}` Makrosu alır seçili dosyasında **Çözüm Gezgini**.

Kaydettikten sonra *tasks.vs.json*, üzerlerinde sağ *.js* dosya klasöründe ve seçin **Yankı filename**. Dosya adı görüntülenir **çıkış** penceresi.

> [!NOTE]
> Kod temeliniz içermiyorsa, bir *tasks.vs.json* dosyası oluşturabilmeniz seçerek **yapılandırma görevleri** bir dosyaya sağ tıklayın veya bağlam menüsünden **Çözüm Gezgini**.

Alt klasörleri ve dosyaları listeleyen bir görevi sonraki örnek tanımlar *bin* dizin.

```json
{
  "version": "0.2.1",
  "outDir": "\"${workspaceRoot}\\bin\"",
  "tasks": [
    {
      "taskName": "List Outputs",
      "appliesTo": "*",
      "type": "default",
      "command": "${env.COMSPEC}",
      "args": [ "dir ${outDir}" ]
    }
  ]
}
```

- `${outDir}` ilk özel bir makro önce tanımlanan `tasks` bloğu. Ardından çağrılır `args` özelliği.

Bu görev tüm dosyalara uygulanır. Herhangi bir dosyada bağlam menüsünde açtığınızda **Çözüm Gezgini**, görevin adı **listesi çıkışları** menüsünün alt kısmında görüntülenir. Seçtiğinizde **listesi çıkışları**, içeriğini *bin* dizin içinde listelenen **çıkış** Visual Studio'daki.

![Bağlam menüsü rasgele görevi](../ide/media/customize-arbitrary-task-menu.png)

### <a name="settings-scope"></a>Ayarları kapsamı

Birden çok *tasks.vs.json* dosyaları, kök ve alt dizinleri bir codebase bulunabilir. Bu tasarım codebase farklı dizinlerde farklı bir davranışı sağlamak esneklik sağlar. Visual Studio toplayan veya codebase boyunca dosyaları aşağıdaki sırayla öncelik ayarları geçersiz kılar:

- Kök klasör ayarları dosyalarında *.vs* dizini.
- Burada bir ayar hesaplanır dizin.
- Kök dizin kadar bu süreç boyunca tüm geçerli dizinin üst dizini.
- Kök dizindeki dosyaların ayarlar.

Bu toplama kuralları için geçerli *tasks.vs.json* ve *VSWorkspaceSettings.json* dosyaları. Diğer dosyasındaki ayarları nasıl toplanır hakkında daha fazla bilgi için bu makalede bu dosya için karşılık gelen bölümüne bakın.

### <a name="properties-for-tasksvsjson"></a>Tasks.vs.json özellikleri

Bu bölümde, belirtebilirsiniz özelliklerden bazıları açıklanmaktadır *tasks.vs.json*.

#### <a name="appliesto"></a>appliesTo

Görevler için herhangi bir dosya veya klasör adını belirterek oluşturabileceğiniz `appliesTo` alan, örneğin `"appliesTo": "hello.js"`. Aşağıdaki dosya maskeleri değerleri olarak kullanılabilir:

|||
|-|-|
|`"*"`| Görev tüm dosyalara ve klasörlere çalışma alanında kullanılabilir|
|`"*/"`| Görev çalışma alanındaki tüm klasörler için kullanılabilir|
|`"*.js"`| Görev çalışma alanında uzantısı .js sahip tüm dosyaları için kullanılabilir|
|`"/*.js"`| Görev çalışma kök uzantısı .js sahip tüm dosyaları için kullanılabilir|
|`"src/*/"`| Görev için "src" klasörünün tüm alt klasörleri kullanılabilir|
|`"makefile"`| Görev çalışma alanındaki tüm derleme görevleri dosyaları için kullanılabilir|
|`"/makefile"`| görev yalnızca çalışma kök derleme görevleri dosyası kullanılabilir|

#### <a name="macros-for-tasksvsjson"></a>Tasks.vs.json makroları

|||
|-|-|
|`${env.<VARIABLE>}`| herhangi bir ortam değişkeni (örneğin, ${env. belirtir YOL}, ${env.COMSPEC} vb.) için geliştirici komut istemi ayarlayın. Daha fazla bilgi için bkz: [Visual Studio için geliştirici komut istemi](/dotnet/framework/tools/developer-command-prompt-for-vs).|
|`${workspaceRoot}`| Çalışma klasörü (örneğin, "C:\sources\hello") için tam yolu|
|`${file}`| Dosya veya klasör (örneğin, "C:\sources\hello\src\hello.js") karşı bu görevi çalıştırmak için seçili tam yolu|
|`${relativeFile}`| Göreli yol dosya veya klasöre (örneğin, "src\hello.js")|
|`${fileBasename}`| Yolu ya da (örneğin, "hello") uzantısı olmadan dosya adı|
|`${fileDirname}`| Dosya adı (örneğin, "C:\sources\hello\src") hariç olmak üzere dosyanın tam yolu|
|`${fileExtname}`| Seçilen dosya (örneğin, ".js") uzantısı|

## <a name="configure-debugging-with-launchvsjson"></a>Launch.vs.JSON ile hata ayıklama yapılandırın

1. Yapılandırmak için hata ayıklama için buna codebase **Çözüm Gezgini** seçin **hata ayıklama ve başlatma ayarları** yürütülebilir dosyasının menü öğesini sağ tıklatın veya bağlam menüsünde.

   ![Hata ayıklama ve başlatma ayarları bağlam menüsü](media/customize-debug-launch-menu.png)

1. İçinde **bir hata ayıklayıcısı seçin** iletişim kutusu, bir seçenek belirleyin ve ardından **seçin** düğmesi.

   ![Hata ayıklayıcı iletişim kutusu seç](media/customize-select-a-debugger.png)

   Varsa *launch.vs.json* dosya zaten yoksa, oluşturulur.

   ```json
   {
     "version": "0.2.1",
     "defaults": {},
     "configurations": [
       {
         "type": "default",
         "project": "bin\\hello.exe",
         "name": "hello.exe"
       }
     ]
   }
   ```

1. Ardından, yürütülebilir dosyaya sağ tıklayın **Çözüm Gezgini**ve seçin **başlangıç öğesi olarak ayarla**.

   Yürütülebilir dosya temelinizde ve hata ayıklama için başlangıç öğesi olarak tasarlanmış **Başlat** , yürütülebilir dosyanın adını yansıtacak şekilde düğmenin başlık değişir.

   ![Özelleştirilmiş Başlat düğmesi](media/customize-start-button.png)

   Seçtiğinizde **F5**, hata ayıklayıcı başlatır ve herhangi bir kesme noktası durur, zaten ayarlayın. Tüm bilinen hata ayıklayıcı windows kullanılabilir ve işlev.

### <a name="specify-arguments-for-debugging"></a>Hata ayıklama için bağımsız değişkenleri belirtin

İçinde hata ayıklama için geçirmek için komut satırı bağımsız değişkenleri belirtebilirsiniz *launch.vs.json* dosya. Bağımsız değişkenleri eklemek `args` dizisi, aşağıdaki örnekte gösterildiği gibi:

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
    {
      "type": "default",
      "project": "bin\\hello.exe",
      "name": "hello.exe"
    },
    {
      "type": "default",
      "project": "bin\\hello.exe",
      "name": "hello.exe a1",
      "args": [ "a1" ]
    }
  ]
}
```

Bu dosyayı kaydettiğinizde, yeni yapılandırma adı hata ayıklama hedefi aşağı açılan listesinde görünür ve hata ayıklayıcısı başlayacak şekilde seçebilirsiniz. Dilediğiniz gibi birçok hata ayıklama yapılandırmaları oluşturabilirsiniz.

![Hata ayıklama yapılandırmaları aşağı açılan liste](media/customize-debug-configurations.png)

> [!NOTE]
> `configurations` Dizi özelliğinde *launch.vs.json* iki dosya konumlardan okuma&mdash;codebase için kök dizini ve *.vs* dizini. Bir çakışma varsa, öncelik değerine verilir *.vs\launch.vs.json*.

## <a name="define-workspace-settings-in-vsworkspacesettingsjson"></a>Çalışma alanı ayarları içinde VSWorkspaceSettings.json tanımlayın

Görevleri etkileyebilir ve başlatılmasına genel ayarları belirtebilirsiniz *VSWorkspaceSettings.json* dosya. Örneğin, tanımlarsanız `envVars` içinde *VSWorkspaceSettings.json*, Visual Studio harici olarak çalışan komutlar için belirtilen ortam değişkenlerini ekler. Bu dosyayı kullanmak için onu el ile oluşturmanız gerekir.

## <a name="additional-settings-files"></a>Ek ayarları dosyaları

Üç ek olarak *.json* dosyaları, bu konuda açıklanan Visual Studio ayrıca okur ayarları bazı ek dosyalardan varsa bunlar temelinizde bulunuyor.

### <a name="vscodesettingsjson"></a>.vscode\settings.json

Visual Studio adlı dosyadan sınırlı ayarları okur *settings.json*, adlı bir dizinde ise *.vscode*. Bu işlev için sağlanan, olarak kullanılabilecek kod temeli Visual Studio kodda önceden geliştirilmiştir. Şu anda yalnızca ayarının okuma *.vscode\settings.json* olan `files.exclude`, dosyaları görsel olarak Çözüm Gezgini ve bazı arama araçlarından filtreleri.

Herhangi bir sayıda olabilir *.vscode\settings.json* temelinizde dosyaları. Bu dosyadan okunan ayarları üst dizinine uygulanan *.vscode* ve tüm alt dizinlerinin.

### <a name="gitignore"></a>.gitignore

*.gitignore* dosyaları Git yoksaymak için hangi dosyaların bildirmek için kullanılır; diğer bir deyişle, dosyaları ve dizinleri iade etmek istemediğiniz. *.gitignore* ayarları codebase tüm geliştiricilere paylaşılabilir böylece dosyaları codebase genellikle birlikte parçası olarak. Visual Studio okur düzenleri *.gitignore* dosyaları öğeleri filtrelemek için görsel olarak ve bazı arama araçları.

Ayarları okumak *.gitignore* dosya üst dizinini ve tüm alt dizinler için uygulanır.

## <a name="see-also"></a>Ayrıca bkz.

- [Projeleri veya çözümler olmadan kod geliştirme](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md)
- [C++ için açık klasörü projeler](/cpp/ide/non-msbuild-projects)
- [C++'ta CMake projeleri](/cpp/ide/cmake-tools-for-visual-cpp)
- [NMAKE başvurusu](/cpp/build/nmake-reference)
- [Kod ve Metin Düzenleyici'de kod yazma](../ide/writing-code-in-the-code-and-text-editor.md)