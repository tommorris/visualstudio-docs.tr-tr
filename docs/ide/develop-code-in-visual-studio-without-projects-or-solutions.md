---
title: "Visual Studio projeleri veya çözümler olmadan kod geliştirme | Microsoft Docs"
ms.custom: 
ms.date: 02/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: article
helpviewer_keywords:
- open folder [Visual Studio]
- anycode [Visual Studio]
- projects and solutions, develop code without
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 40995be9ee5d5da5a3219dd8badcb13e4b3f6e62
ms.sourcegitcommit: d6327b978661c0a745bf4b59f32d8171607803a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2018
---
# <a name="develop-code-in-visual-studio-without-projects-or-solutions"></a>Visual Studio projeleri veya çözümler olmadan kod geliştirme

Visual Studio 2017 ', kod neredeyse tüm dizin tabanlı proje türünden Visual Studio'ya bir çözüm ya da proje dosyası gerek kalmadan açabilirsiniz. Bu, örneğin, kod projesi üzerinde Git bulabilir, kopyalamak ve ardından doğrudan Visual Studio'ya açın ve bir çözüm ya da proje oluşturmak zorunda kalmadan geliştirmeye başlamak anlamına gelir.  

Yalnızca, kodu düzenleyebilir ve bu derleme Visual Studio'da, kodunuzu (gitmek için kullanarak komut gibi) de gidebilirsiniz. Kod söz dizimi renklendirme ve çoğu durumda, görünür temel deyim tamamlama içerir ve hata ayıklama, kesme noktaları ile tamamlayın. Bazı diller daha da fazla işlevsellik içerir. Bkz: [taşınabilir, özel düzenleyici ayarları oluşturmak](create-portable-custom-editor-options.md) daha fazla bilgi için.  

## <a name="open-code-anywhere"></a>Herhangi bir yere açık kodu

Aşağıdaki yollarla Visual Studio'ya kod açabilirsiniz:  

- Visual Studio menü çubuğunda seçin **dosya**, **açık**, **klasörü**, kod konuma göz atın.  

- Kodu içeren bir klasör (sağ tıklatma) bağlam menüsünde seçin **Visual Studio'da Aç** komutu.  

- Seçin **Klasör Aç** Visual Studio Başlangıç sayfası bağlantısına.  

- Açık kod GitHub deposuna kopyalanabilir.  

### <a name="to-open-code-from-a-cloned-github-repo"></a>Kopyalanan bir GitHub deposuna kod açmak için

Aşağıdaki örnek, bir GitHub deposuna kopyalamak ve kendi kod Visual Studio'da açın gösterilmektedir. Bu yordamı takip etmek için GitHub hesabı ve Windows için Git sisteminize yüklenmiş olmalıdır. Bkz: [yeni bir GitHub hesabı için kaydolmadan](https://help.github.com/articles/signing-up-for-a-new-github-account/) ve [Windows için Git](https://git-for-windows.github.io/) daha fazla bilgi için.  

1. Github'da kopyalamak istediğiniz depoya gidin.  

1. Seçin **kopyalama veya indirme** düğmesine tıklayın ve ardından **Panoya Kopyala** GitHub depo için güvenli URL'yi kopyalamak için açılır menüde düğmesi.  

  ![GitHub kopya düğmesi](./media/VSIDE_Code_Clone.png)

    > [!NOTE]
    >  Masaüstünüzde projesini açın veya projenin .zip dosya indirme seçeneği de sahip olsa da, bu örnek güvenli URL yöntemini kullanarak depoyu kopyalama gösterilmektedir.

1. Visual Studio'da, **Takım Gezgini** sekmesini Takım Gezgini'ni açın.  

1. Takım Gezgini'nde altında **yerel Git depoları** bölümünde, seçin **kopya** komut ve GitHub sayfasının URL'sini metin kutusuna yapıştırın.  

  ![Proje kopyalama](./media/VSIDE_Code_Clone2.png)

1. Seçin **kopya** proje dosyalarını yerel bir Git deposuna kopyalamak için düğmesi. Depodaki boyutuna bağlı olarak, bu işlem birkaç dakika sürebilir.  

1. Takım Gezgini'nde, sisteminize depoyu klonlanmış sonra tercih **açık** yeni kopyalanmış depo bağlamını (sağ tıklatma) menüsünde komutu.  

  ![Kopyalanan deposu](./media/VSIDE_Code_Clone3.png)

1. Seçin **klasör görünümü göster** komut dosyaları Çözüm Gezgini'nde görüntülemek için  

  ![Klasör Görünümü Göster](./media/VSIDE_Code_Clone3_show.png)

  Şimdi kopyalanan depodaki dosya ve klasörleri bulun ve da görüntüleyebilir ve kod söz dizimi renklendirme ile tam Visual Studio kod düzenleyicisini ve diğer özellikleri arayabilirsiniz.

    ![Kopyalanan proje kod arama](./media/VSIDE_Code_Clone4.png)  

|         |         |
|---------|---------|
|  ![video kamera simgesine film](../install/media/video-icon.png "bir videoyu izleyin")  |    [Bir video izlemek](https://mva.microsoft.com/en-us/training-courses/getting-started-with-visual-studio-2017-17798?l=lp3TOKD6D_6711787171) nasıl kopyalamak ve kod'i GitHub deposuna Visual Studio'da açın. |

## <a name="debug-your-code"></a>Kodunuzdaki hataları ayıklamanıza

Visual Studio kodunuzda proje ya da çözüm olmadan ayıklayabilirsiniz. Bazı diller hata ayıklamak için geçerli bir belirtmeniz gerekebilir *başlatma dosyasını* kod projesinde, komut dosyası, yürütülebilir dosya veya proje gibi. Kodunuzdaki hataları ayıklamanıza visual Studio bu belirtilen kod önce çalıştırılır.  

Araç çubuğundaki Başlat düğmesi yanındaki aşağı açılan liste kutusunu tüm öğeleri bir klasörde özellikle Seç yanı sıra Visual Studio algılar Başlangıç öğeleri listeler.  

![Çalıştır düğmesi](./media/VSIDE_Code_Run_Button.png)  

Visual Studio projeleri otomatik olarak algılar ancak komut dosyaları (örneğin, Python ve JavaScript) açıkça listede görünür önce size bir başlangıç öğesi olarak seçilmesi gerekir. Ayrıca, MSBuild ve CMake, gibi bazı başlangıç öğelerini çalıştırmak düğmenin aşağı açılan listeden görüntülenen birden çok derleme yapılandırmaları olabilir.  

Visual Studio şu anda aşağıdaki diller için hata ayıklama destekler:  

- Node.js  

- Python  

- MSBuild tabanlı projeler (C#, VB, C++)  

- Herhangi bir yürütülebilir dosya PDB (Python hata ayıklayıcı) dosyaları.  

### <a name="to-debug-nodejs-and-python"></a>Node.js ve Python hata ayıklamak için:

1. Node.js veya Python araçlarını veya Visual Studio 2017 ve Node.js çalışma zamanı yükleyin.  

1. Çözüm Gezgini'nde bir JavaScript dosyası bağlam menüsünde seçin **başlangıç öğesi olarak ayarla** komutu.  

1. Seçin **F5** hata ayıklama başlamak için anahtar.  

### <a name="to-debug-msbuild-projects"></a>MSBuild projelerine hata ayıklamak için

1. Visual Studio menüsünde, **hata ayıklama**. Aşağı açılan menüsünde, projeyi seçin veya proje ve Çözüm Gezgini'nde başlangıç öğesi olarak görüntülenmesini istediğiniz dosyayı seçin.  

1. Seçin **F5** hata ayıklama başlamak için anahtar.  

### <a name="to-debug-executable-files"></a>Hata ayıklama yürütülebilir dosyaları için

1. Visual Studio menüsünde, **hata ayıklama**. Aşağı açılan menüsünde, projeyi seçin veya proje ve Çözüm Gezgini'nde başlangıç öğesi olarak görüntülenmesini istediğiniz dosyayı seçin.  

1. Seçin **F5** hata ayıklama başlamak için anahtar.  

## <a name="enable-custom-build-tools"></a>Özel derleme araçlarını etkinleştirme

Visual Studio, birçok farklı dillerde çalıştırmak bildiği, ancak her şeyi çalıştırılacağını bilmiyor. Visual Studio dilinizi çalıştırma biliyorsa kodu hemen çalıştırabilirsiniz. Kodunuzu çalıştırmak deneyin ancak Visual Studio'nun nasıl çalıştırılacağı bilmeniz değil, bir bilgi çubuğu bir dosyada tanımlamanızı ister, başlangıç öğesi olarak davranacak şekilde codebase.  

Visual Studio tanımıyor özel derleme araçları codebase kullanıyorsa, yine de daha sonra büyük olasılıkla çalıştırın ve bazı ek adımlar tamamlanana kadar Visual Studio kodda hata ayıklama mümkün olmaz. Geçerli bir yürütülebilir dosya türü, özel parametreler ve bağımsız değişkenler dil için gerekli yanı sıra bir derleyici gibi belirtmeniz gerekir. Bunu etkinleştirmek için Visual Studio sağlar *derleme görevleri*. Bir dil derlemek ve kendi kod çalıştırmak için gereken tüm öğeleri belirtmek için derleme görevi oluşturabilirsiniz.  

Neredeyse istediğiniz her şeyi yapabilirsiniz rasgele derleme görevleri de oluşturabilirsiniz. Örneğin, bir klasör içeriğini listele veya bir dosyayı yeniden adlandırmak için bir görev oluşturabilirsiniz. Ya da derleme gibi şeyler ve belirli bağımsız değişkenler kullanarak projenize yapı daha hedeflenen özel derleme görevleri oluşturabilirsiniz. Aşağıdaki adımlar, her iki türdeki yapı görevler oluşturma gösterir.  

#### <a name="to-create-an-arbitrary-build-task"></a>Rastgele derleme görevi oluşturmak için

1. Dosya veya klasör görev istediğiniz Çözüm Gezgini'nde ve dosyanın veya klasörün (sağ tıklatma) bağlam menüsü, projenin seçin seçin **yapılandırma görevleri**.  

  ![Görevleri yapılandırma](./media/VSIDE_Code_Config_Task.png)

  Seçme **yapılandırma görevleri** tasks.vs.json adlı bir dosyayı açar. Bu dosya yoksa, oluşturulur. Bu dosya seçilen dosya veya klasör için derleme görevleri içerir.  

  ![Tasks.vs.JSON dosyası](./media/VSIDE_Code_Tasks_JSON.png)

1. Aşağıdaki derleme görevi için tasks.vs.json ekleyin. Bu örnekte, dosyaları ve çıktı penceresinde seçili klasörünün alt klasörleri listeler "Listesi çıkışları" adlı bir basit görev ekleyeceğiz. (Yeni görev içinde varolan "görevler" dizi eklenmesi gerekir.)  

  ```xml
      {
        "taskName": "List outputs",
        "appliesTo": "*",
        "type": "command",
        "command": "${env.COMSPEC}",
        "args": [
          "dir ${outDir}"
        ]
      },
  ```
  Tam derleme görevi aşağıdaki gibi görünmelidir.  

  ![Rastgele derleme görevi](./media/VSIDE_Code_Tasks_ArbTask.png)

1. Projeyi kaydedin.  

1. Seçilen klasör için bağlam menüsünü açın. Bağlam menüsünün alt kısmında görüntülenir yeni rasgele derleme görevi görmeniz gerekir.  

  ![Rastgele derleme görevi komutu](./media/VSIDE_Code_Tasks_ArbTask2.png)

1. Yeni seçin **listesinde çıkışları** görevi çalıştırmak için komutu.  

### <a name="to-create-a-custom-build-task"></a>Özel derleme görevi oluşturmak için

Bu yordamda, yapı ve kodunuzu temizlemek amacıyla nMake kullanan iki özel derleme görevler ekleyeceğiz.  

1. Çözüm Gezgini'nde, daha sonra başlangıç öğesi olarak belirtmek istediğiniz projesinin bir dosya seçin. Dosyanın (sağ tıklatma) bağlam menüsünde, **yapılandırma görevleri**.  

  ![Özel derleme görevi komutu](./media/VSIDE_Code_Tasks_CustTask1.png)

1. Aşağıdaki yapı görevleri için tasks.vs.json ekleyin. Bu örnekte, iki görevi ekleyeceğiz: diğer adlı bir çağrılan "derleme görevleri dosyası projesi derlemek için nMake komutu kullanan derleme", derleme görevleri dosyası temiz hangi "temiz" bağımsız değişkeni nMake komutuyla çağırır. Bu görevleri içinde varolan "görevler" dizi eklenmesi gerekir. (Bunlar yalnızca örnek derleme görevleri olduğunu unutmayın. Bunları gerçekten çalışmaya içeren iş yükü gerek duyarsınız [nNake](/cpp/build/nmake-reference) , sisteminizde yüklü.)

  ```xml
  {
  "taskName": "makefile-build",
  "appliesTo": "makefile",
  "type": "command",
  "contextType": "build",
  "command": "nmake"
  },
  {
  "taskName": "makefile-clean",
  "appliesTo": "makefile",
  "type": "command",
  "contextType": "clean",
  "command": "nmake",
  "args": [
    "clean"
    ]
  },
  ```
  Tam özel derleme görevi aşağıdaki gibi görünmelidir.  

  ![Özel derleme görevi](./media/VSIDE_Code_Tasks_CustTask2.png)

1. Projeyi kaydedin.  

1. Seçilen dosya bağlam menüsünü açın. Yeni özel derleme görevleri ortasında bağlam menüsünde görüntülenmelidir.  

  ![Özel derleme görevi komutu](./media/VSIDE_Code_Tasks_CustTask3.png)

  > [!NOTE]
  > Komutları altında göründüğünü **yapılandırma görevleri** nedeniyle komutunu kendi `contextType` ayarları; "Oluştur" ve bağlam menüsünden ortasında yapı bölümdeki göründükleri şekilde derleme komutları "temiz".  

  Özel derleme komutları dosyayla ilişkili, dosyanın başlangıç öğesi olarak belirleyebilirsiniz.  

1. Dosyanın bağlam menüsünde, **başlangıç öğesi olarak ayarla**.  

  ![Özel derleme görevi komutu](./media/VSIDE_Code_Tasks_CustTask4.png)

1. Araç çubuğunda, Başlat düğmesi yanındaki açılan oka seçin. Başlangıç öğesi artık isteğe bağlı olarak görünür.  

  ![Özel derleme görevi komutu](./media/VSIDE_Code_Tasks_CustTask5.png)

Artık seçebilirsiniz **Başlat** düğmesini veya **F5** temelinizde çalıştırmak için anahtar. Düzenle ve Visual Studio codebase derleme araçlarını tanımıyor olsa bile temelinizde Visual Studio'da hata ayıklama. Yapı görev çıktısını görünür **çıkış** penceresi ve yapı hataları görünür **hata listesi**. Tasks.vs.json Visual Studio iç geliştirme döngüsü özel derleme araçlarını temelinizde tarafından kullanılan görev dosya tüm çiftler oluşturun.  

Özel derleme görevleri dosyaları tek tek veya belirli bir türde tüm dosyaları eklenebilir. Örneği için "Paketler geri yükleme" görev için NuGet paket dosyalarını yapılandırılabilir veya tüm kaynak dosyaları linter tüm .js dosyaları gibi statik çözümleme göreve sahip şekilde yapılandırılabilir.  

Visual Studio destekler VSCode `$variable` ortam değişkenleri yanı sıra tasks.vs.json kökünde değiştirme (gibi `$env.var`) veya anahtarlar.  

## <a name="specify-build-output"></a>Belirtin çıkış derleme

Projenizi derlenmesi gerekiyorsa adlı ek bir etiket ekleyebilirsiniz `output` tasks.vs.json dosyasına kayıt yapar. Aşağıda bir örnek vardır.  

`"output": "${workspaceRoot}\\bin\\hellomake.exe"`

Çıktı konumunu belirtme Visual Studio Proje derleme çıktı nerede bulacağını bildirir.  

## <a name="tasksvsjson-file-location"></a>Tasks.vs.JSON dosya konumu

Varsayılan olarak, tasks.vs.json dosya adlı gizli bir klasörde bulunan `.vs`. Visual Studio'da gizli dosyaları görüntülemek için seçin **tüm dosyaları göster** Çözüm Gezgini araç çubuğunda.

![Rastgele derleme görevi komutu](./media/VSIDE_Code_Tasks_FileLocation.png)

Kullanıcıların çoğunun genellikle kaynak denetimine iade istemediğiniz çünkü tasks.vs.json dosya gizlenir. Ancak, kaynak denetimine iade istiyorsanız, dosyayı burada da görünür olacak projenizi kök sürükleyin.  

Diğer .json dosyaları .vs klasörde mevcut olabilir, ancak (biri varsa) taşımanız gerekir yalnızca tasks.vs.json dosyasını ve launch.vs.json dosyasını olanlardır. Tasks.vs.json dosyasını Visual Studio'da derleme yapılandırırken launch.vs.json dosya Visual Studio hata ayıklayıcısı yapılandırır.  

## <a name="see-also"></a>Ayrıca bkz.

[Kod ve Metin Düzenleyici'de kod yazma](../ide/writing-code-in-the-code-and-text-editor.md)
