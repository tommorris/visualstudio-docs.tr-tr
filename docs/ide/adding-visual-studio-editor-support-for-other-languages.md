---
title: Visual Studio Düzenleyicisi diğer dilleri desteği ekleme
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- syntax colorization
- IntelliSense
- IDE, navigation
- documents [Visual Studio], navigation
- TextMate bundle
- TextMate language grammar
- language support
ms.assetid: d78c43ee-4ef2-42e5-984e-d137de4e7e92
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.workload:
- multiple
ms.openlocfilehash: 3e139fe1858772ed0505f774ce4c36e00bc059e0
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34746132"
---
# <a name="add-visual-studio-editor-support-for-other-languages"></a>Diğer diller için Visual Studio Düzenleyicisi desteği ekleme

Visual Studio düzenleyicisinde okuma ve farklı bir bilgisayara diller gezinme nasıl destekler ve diğer diller için Visual Studio Düzenleyicisi desteği eklemek için ne hakkında bilgi edinin.

## <a name="syntax-colorization-statement-completion-and-navigate-to-support"></a>Söz dizimi renklendirme, deyim tamamlama ve gitmek için destek

Visual Studio düzenleyicisinde söz dizimi renklendirme, deyim tamamlama ve gitmek için gibi özellikleri, daha fazla kolayca okumasına, oluşturmasına ve kodunuzu düzenleyin yardımcı olabilir. Aşağıdaki ekran görüntüsünde Perl komut dosyasını Visual Studio'da düzenleme bir örneği gösterir. Söz dizimi, otomatik olarak renklendirilir. Örneğin, kodda açıklamalar yeşil renkte kodudur siyah yolları kırmızı ve deyimleri mavi. Visual Studio düzenleyicisinde söz dizimi renklendirme desteklediği herhangi bir dil için otomatik olarak uygular. Ayrıca, bilinen dil anahtar sözcüğü veya nesne girmek başladığınızda, deyim tamamlama olası deyimleri ve nesnelerin bir listesini görüntüler. Deyim tamamlama kodu daha hızlı ve kolay bir şekilde oluşturmanıza yardımcı olabilir.

![Perl komut söz dizimi renklendirme](../ide/media/vside_perledit.png)

Visual Studio şu anda sağlar söz dizimi renklendirme ve temel deyim tamamlama kullanarak aşağıdaki diller için desteği [TextMate aynı](https://manual.macromates.com/en/language_grammars). Sık kullanılan dilinizi tabloda değilse, ancak, endişelenmeyin - ekleyebilirsiniz.

|||||||
|-|-|-|-|-|-|
|.Bat uzantılarını dener|F#|Java|Markdown|Rust|Visual Basic|
|Clojure|Git|JavaDoc|Objective-C|ShaderLab|C#|
|CMake|Modaya uygun|JSON|Perl|ShellScript|Visual C++|
|CoffeeScript|HTML|DAHA AZ|Python|SQL|VBNet|
|CSS|INI|LUA|R|SWIFT|XML|
|Docker|Jade|Marka|Ruby|TypeScript|YAML|

Söz dizimi renklendirme ve temel deyim tamamlama ek olarak, Visual Studio ayrıca adlı bir özelliği olan [gitmek için](https://blogs.msdn.microsoft.com/benwilli/2015/04/09/visual-studio-tip-3-use-navigate-to/). Bu özellik, hızlı bir şekilde kod dosyaları, dosya yolları ve kod simgeleri aramanıza olanak sağlar. Visual Studio aşağıdaki diller için gitmek için destek sağlar.

-   Git

-   Java

-   JavaScript

-   PHP

-   TypeScript

-   Visual Basic

-   Visual C++

-   C#

Bu dosya türlerini belirli bir dile henüz yüklenmemiştir desteği özellikleri açıklandığı önceki olsa bile sahip. Bazı diller için özelleştirilmiş desteğini yükleme IntelliSense gibi ek dil desteği veya ampuller gibi diğer Gelişmiş dil özellikleri sağlayabilir.

## <a name="add-support-for-non-supported-languages"></a>Desteklenmeyen dilleri desteği ekleme

Visual Studio 2015 güncelleştirme 1 ve sonraki sürümlerinde sağlamak Düzenleyicisi'nde dil desteği kullanılarak [TextMate aynı](https://manual.macromates.com/en/language_grammars). Sık kullanılan programlama diliniz şu anda Visual Studio düzenleyicisinde desteklenmiyorsa, ilk olarak, web arama - TextMate paket dil için zaten var olabilir. Ancak, bir bulamazsanız, Visual Studio 2015 güncelleştirme 1 veya daha sonra dil aynı ve kod parçacıkları için bir TextMate paket modeli oluşturarak destek kendiniz ekleyebilirsiniz.

Visual Studio aşağıdaki klasörde bulunan tüm yeni TextMate aynı ekleyin:

*%userprofile%\\.vs\Extensions*

Durumunuza uygun yoksa bu temel yolu altında aşağıdaki klasörlerde ekleyin:

|Klasör adı|Açıklama|
|-----------------|-----------------|
|\\*\<dil adı >*|Dil klasörü. Değiştir  *\<dil adı >* dil adı. Örneğin, *\Matlab*.|
|*\Syntaxes*|Dilbilgisi klasör. Dilbilgisi içeren *.json* dil için aşağıdaki gibi dosyalar *Matlab.json*.|
|*\Snippets*|Kod parçacıkları klasör. Dili için kod parçacıkları içerir.|

Windows, *% USERPROFILE %* yolunu Çözümler: *c:\Users\\\<kullanıcı adı >*. Uzantıları klasörünü, sisteminizde mevcut değilse, bunu oluşturmanız gerekir. Bu klasör zaten mevcutsa gizlenir.

TextMate aynı oluşturma hakkında daha fazla bilgi için bkz [TextMate - dil aynı giriş: kaynak kodu sözdizimi vurgulama ekleme HTML biçiminde katıştırılmış](https://developmentality.wordpress.com/2011/02/08/textmate-introduction-to-language-grammars/) ve [dil dilbilgisi ve özel oluşturma ile ilgili notlar Tema Textmate paket için](https://benparizek.com/notebook/notes-on-how-to-create-a-language-grammar-and-custom-theme-for-a-textmate-bundle).

## <a name="see-also"></a>Ayrıca bkz.

- [İzlenecek Yol: Kod parçacığı oluşturma](../ide/walkthrough-creating-a-code-snippet.md)
- [İzlenecek yol: Görüntü deyim tamamlama](../extensibility/walkthrough-displaying-statement-completion.md)