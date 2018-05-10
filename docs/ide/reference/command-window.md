---
title: Komut Penceresi
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.CommandWindow
helpviewer_keywords:
- IDE, Command window
- Mark mode in Command window
- Command window
- Command mode in Command window
- IDE Command window
ms.assetid: 48711628-1909-4713-a73e-d7b714c77f8a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6594b87ad313b7f452f579059af377e6128a887a
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="command-window"></a>Komut Penceresi
**Komutu** penceresi komutları veya diğer adlar doğrudan yürütmek için kullanılan [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamı (IDE). Hiçbir menüde menü komutları ve görünmez komutlar yürütebilir. Görüntülenecek **komutu** penceresinde, seçin **diğer pencereler** gelen **Görünüm** menü ve seçin **komut penceresi**.

## <a name="displaying-the-values-of-variables"></a>Değişkenlerin değerlerini görüntüleme
 Bir değişkenin değerini denetlemek için `varA`, kullanın [Yazdır komutu](../../ide/reference/print-command.md):

```cmd
>Debug.Print varA
```

 Soru işareti (?) için bir diğer ad olduğu `Debug.Print`, bu nedenle bu komut ayrıca yazılabilir:

```cmd
>? varA
```

 Bu komutu hem sürümlerini değişkenin değerini döndürür `varA`.

## <a name="entering-commands"></a>Komutları girme
 Büyüktür simgesi (`>`) komut penceresinde sol kenarı yeni satırlar için bir istem olarak görünür. Önceden düzenlenen komutları kaydırmak için yukarı ve aşağı ok tuşlarını kullanın.

|Görev|Çözüm|Örnek|
|----------|--------------|-------------|
|Bir ifade değerlendirin.|İfade bir soru işareti ile yazdığınızdan (`?`).|`? myvar`|
|Hemen bir penceresine dönün.|Girin `immed` büyüktür işareti (>) olmadan penceresine|`immed`|
|Hemen bir penceresinden komut penceresine geçin.|Girin `cmd` penceresine.|`>cmd`|

 Aşağıdaki kısayolları komut modundayken gezinmenize yardımcı olur.

|Eylem|İmleç konumu|KeyBinding|
|------------|---------------------|----------------|
|Önceden girilen komutların listesini geçiş yapın.|Giriş hattı|YUKARI OK &AMP; AŞAĞI OK|
|Pencereyi kaydırın.|Komut penceresi içeriği|CTRL + YUKARI OK|
|Pencere aşağı kaydırın.|Komut penceresi içeriği|Aşağı Ok veya CTRL + AŞAĞI OK|

> [!TIP]
> Kendisine kaydırma tümünü veya bir kısmını vurgulama ve ardından ENTER tuşuna basarak, giriş satırına tüm veya önceki bir komutun parçası kopyalayabilirsiniz.


## <a name="mark-mode"></a>İşaret modu
 İçinde herhangi bir önceki satırdaki tıklattığınızda **komutu** penceresinde, shift otomatik olarak işareti moduna. Bu, seçin, düzenlemek ve herhangi bir metin düzenleyicisinde olur ve geçerli satıra yapıştırmak gibi önceki komutların metin kopyalamak sağlar.

## <a name="the-equals--sign"></a>Eşittir (=) işareti
 Girmek için kullanılan penceresi `EvaluateStatement` komutu belirleyen bir eşittir işareti (=) bir karşılaştırma işleci veya atama işleci olarak yorumlanır.

 İçinde **komutu** penceresinde, bir eşittir işareti (=) bir karşılaştırma işleci yorumlanır. Atama İşleçleri kullanamazsınız **komutu** penceresi. Örneğin, bunu, değişkenlerin değerleri `varA` ve `varB` farklı sonra komut `>Debug.EvaluateStatement(varA=varB)` değerini döndürür `False`.

 İçinde **hemen** penceresinde, buna karşın bir eşittir işareti (=) atama işleci yorumlanır. Bunu, örneğin, komut `>Debug.EvaluateStatement(varA=varB)` değişkenine atar `varA` değişkenin değerini `varB`.

## <a name="parameters-switches-and-values"></a>Parametreler, anahtarları ve değerleri
 Bazı [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] komutları komutları gerekli ve isteğe bağlı bağımsız değişkenler, anahtarları ve değerleri. Belirli kurallar gibi komutları ile ilgilenirken uygulanır. Aşağıdaki terimler açıklamak için zengin bir komutu örneğidir.

```cmd
Edit.ReplaceInFiles /case /pattern:regex var[1-3]+ oldpar
```

 Bu örnekte,

-   `Edit.ReplaceInFiles` komut

-   `/case` ve `/pattern:regex` anahtarlara (eğik çizgi [/] karakteriyle başlayan)

-   `regex` değeri `/pattern` ; anahtar `/case` anahtar değere sahip değil

-   `var[1-3]+` ve `oldpar` parametreleri

    > [!NOTE]
    >  Komut, parametresi, anahtar veya boşluk içeren değer çift tırnak işaretleri iki tarafında olması gerekir.

Anahtarları ve parametreler konumunu serbestçe dışında komut satırında deyimleri [Kabuk](../../ide/reference/shell-command.md) alt anahtarları ve belirli bir sırada parametreler gerektirir komutu.

Bir komut tarafından desteklenen neredeyse her anahtar iki forms sahiptir: kısa (bir karakter) form ve uzun bir formu. Birden çok kısa biçimli anahtar bir gruba birleştirilebilir. Örneğin, `/p /g /m` dönüşümlü olarak ifade edilebilir `/pgm`.

Kısa biçimli anahtarları bir gruba birleştirilir ve bir değeri verildiğinde, bu değer her anahtar için geçerlidir. Örneğin, `/pgm:123` karşılık gelir `/p:123 /g:123 /m:123`. Herhangi bir grup anahtarlarında kabul etmiyor ise bir değer hata oluşur.

## <a name="escape-characters"></a>Çıkış karakterleri
 Aşağıdaki tam anlamıyla yerine bir denetim karakteri olarak yorumlanır hemen bir komut satırında bir şapka (^) karakteri karakter anlamına gelir. Bu anahtar adları dışında bir parametre veya anahtar değer düz tırnak işaretleri ("), boşluk, başında bir eğik çizgi, belirliyorsanız düzeltme işaretleri veya başka bir değişmez değer karakterler katıştırmak için kullanılabilir. Örneğin,

```cmd
>Edit.Find ^^t /regex
```

 İç veya dış tırnak işaretleri olup bir şapka aynı çalışır. Bir şapka satırında son karakter ise, yoksayılır. Burada gösterilen örnek düzeni için arama yapmayı gösteren "^ t".

## <a name="use-quotes-for-path-names-with-spaces"></a>Yol adları boşluk için tırnak işareti kullanın
 Örneğin, boşluk içermeyen bir yolu olan bir dosyayı açmak istiyorsanız yolu veya boşluk içeren yol kesimi çift tırnak konulmalıdır: **C:\\"Program Files"** veya **"C:\Program Files"**.

## <a name="see-also"></a>Ayrıca Bkz.

- [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)
- [Visual Studio Komutları](../../ide/reference/visual-studio-commands.md)