---
title: EditorConfig
description: Mac için Visual Studio stillerde kodlama tutarlı proje etkinleştirmek için bir editorconfig dosyası kullanma
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.topic: article
ms.technology: vs-ide-install
ms.assetid: 26A0DE31-2FBF-4E1B-99FB-083111AA1680
ms.openlocfilehash: 553a8ceeae16b660115ea3c8e32e544e903a72af
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="creating-and-editing-a-custom-editorconfig-file"></a>Oluşturma ve özel EditorConfig dosya düzenleme

Mac için Visual Studio'da eklediğiniz bir [EditorConfig](http://editorconfig.org/) dosyası projeye ya da tutarlı kodlama zorlamak için codebase stiller herkesin codebase çalışır. EditorConfig dosyasında bildirilen ayarları Düzenleyici ayarları genel Visual Studio metin önceliklidir. Projenizi içinde EditorConfig kullanarak veya codebase, kodlama stili, Tercihler ve projeniz için uyarılar ayarlamanıza olanak tanır. Bu proje için kodlama uygulamalarını uyması Mac kullanıcıları için tüm Visual Studio için kolaylaştırır.

[EditorConfig](http://editorconfig.org/) dosyaları, Visual Studio 2017 dahil olmak üzere birçok IDE ve kod düzenleyicilerini üzerinde desteklenir. 

## <a name="supported-settings"></a>Desteklenen ayarları

Visual Studio düzenleyicisinde çekirdek kümesini destekler [EditorConfig özellikleri](http://editorconfig.org/#supported-properties):

- `indent_style`
- `indent_size`
- `tab_width`
- `end_of_line`
- `charset`
- `trim_trailing_whitespace`
- `insert_final_newline`
- `root`

EditorConfig de destekler [stili kod biçimlendirme](https://docs.microsoft.com/visualstudio/ide/editorconfig-code-style-settings-reference) C#.

## <a name="add-an-editorconfig-file-to-a-project"></a>Projeye bir EditorConfig dosyası ekleme

### <a name="adding-a-new-editorconfig-file"></a>Yeni bir EditorConfig dosyası ekleme

1. Mac için Visual Studio projenizi açın Dosyaları eklemek istediğiniz proje düğümünü seçin.

2. Seçili proje düğümle Git **Dosya > yeni dosya...** açmak için menü çubuğunda **yeni dosya** iletişim.

3. Seçin **çeşitli > boş metin dosyası** ve verin **adı** `.editorconfig`. Tuşuna **yeni** dosyası oluşturun ve düzenleyicide açın:

    ![Yeni dosya iletişim kutusu](media/editorconfig-image1.png)

4. Dosyayı düzenleyin. Örneğin:

    ```EditorConfig
    # This file is the top-most EditorConfig file
    root = true

    # All Files
    [*]
    indent_style = space
    indent_size = 8
    insert_final_newline = false
    trim_trailing_whitespace = false

    [*.cs]
    csharp_new_line_before_open_brace = none
    ```

4. Dosya ekleme, ayarlarınızı otomatik olarak güncelleştirilmez. Ayarlardan yansıtacak şekilde `.editorconfig` dosya, proje düğümüne seçip **Düzenle > biçimi > biçimi belge** menü çubuğundan:

    ![Biçim belge menü öğesi](media/editorconfig-image2.png)

### <a name="adding-an-existing-editorconfig-file"></a>Var olan bir EditorConfig dosyasını ekleme

Bir proje ile çalışıyorsanız veya çözüm zaten içeren bir `.editorconfig` dosya, ayarları uygulamak için gerçekleştirmeniz gereken bir şey yok. Herhangi bir yeni satırları kod göre EditorConfig ayarları biçimlendirilir. Mac uyar için Visual Studio unutmamalısınız `.editorconfig` dosyaları çözüm düzeyinde değil göründükleri olgu nedeniyle çözüm panelinde itibaren dosyaları `.` macOS içinde gizli dosyalardır.

Var olan yeniden isteyebilirsiniz `.editorconfig` projenizdeki dosya. Varolan bir dosyayı eklemek için önce aşağıdaki komutu girerek Finder gizli dosyaların görüntülenmesini yapmanız **Terminal**:

```
$ defaults write com.apple.Finder AppleShowAllFiles true
$ killall Finder
```

Bir kez `.editorconfig` dosyası görünür, proje düğümüne sürükleyin. Aşağıdaki iletişim kutusuyla sunulduğunda seçin **dosyasını dizinine kopyalayın** seçeneğini ve **Tamam**:

![Biçim belge menü öğesi](media/editorconfig-image3.png)

Ayarlardan yansıtacak şekilde `.editorconfig` dosya, proje düğümüne seçip **Düzenle > biçimi > biçimi belge** menü çubuğundan.

## <a name="editing-an-editorconfig-file"></a>EditorConfig dosya düzenleme

EditorConfig dosyaları basit dosya düzeni açıklanan bir önceki örnekte kullanarak aşağıdaki ayarları belirtmek için kullanın:


```EditorConfig
# This file is the top-most EditorConfig file
root = true

# All Files
[*]
indent_style = space
indent_size = 4
insert_final_newline = false
trim_trailing_whitespace = false

[*.cs]
csharp_new_line_before_open_brace = none
```

Ayarı `root` için `true` bu dosyayı en üstteki dosyası codebase ve daha olarak işaretleyecektir `.editorconfig` proje dosyalarında yoksayılacaktır açıklandığı gibi [EditorConfig ayarlarını geçersiz kıl](#override-editorconfig-settings) bölümü.

Her bölüm kare gösterilir (**[]**) küme ayraçları ve aşağıdaki özellikleri ilgilidir dosya türleri hakkında bilgileri belirtir.

Yukarıdaki örnekte, bazı ayarları projedeki tüm dosyalar uygulanır ve diğerleri yalnızca C# dosyasına eklenir. Aşağıdaki ekran görüntüleri önce ve sonra Göster `.editorconfig` ayarları uygulandı:

**Önce**:

![Editorconfig ayarları uygulanmadan önce](media/editorconfig-image4.png)

**Sonra**:

![editorconfig ayarları uygulandıktan sonra](media/editorconfig-image5.png)

Kullanılabilir EditorConfig ayarları hakkında daha fazla bilgi için bkz: [EditorConfig kuralı ayarlarını kodlama .NET](https://docs.microsoft.com/visualstudio/ide/editorconfig-code-style-settings-reference) makale ve [desteklenen özellikler](http://editorconfig.org/#supported-properties) resmi belge bölüm.

## <a name="override-editorconfig-settings"></a>EditorConfig ayarları geçersiz kılar

Birden fazla olması mümkündür `.editorconfig` her çözüm dosyasında. Visual Studio Mac okuma için `.editorconfig` çözümdeki yukarıdan dosyaları üstten ekleme ve bu ayarları geçersiz kılma gider. Ayarları buna `.editorconfig` _yakın_ düzenlediğiniz dosyanın önceliğe sahip olur. 

Emin olmak istiyorsanız _hiçbir_ ayarlarından herhangi üst düzey `.editorconfig` dosyaları, bu codebase kısmına uygulanır, ekleme `root=true` en düşük düzeyli özelliğine `.editorconfig` dosyası:

```EditorConfig
# top-most EditorConfig file
root = true
```