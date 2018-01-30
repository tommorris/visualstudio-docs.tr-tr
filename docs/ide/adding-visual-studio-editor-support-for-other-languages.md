---
title: "Visual Studio Düzenleyicisi diğer dilleri desteği ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- syntax colorization
- IntelliSense
- IDE, navigation
- documents [Visual Studio], navigation
- TextMate bundle
- TextMate language grammar
- language support
ms.assetid: d78c43ee-4ef2-42e5-984e-d137de4e7e92
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology:
- vs-ide-general
ms.workload:
- multiple
ms.openlocfilehash: 3dd53222baf58b0c609967bc86e3051c428073e1
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="adding-visual-studio-editor-support-for-other-languages"></a>Visual Studio Düzenleyicisi diğer dilleri desteği ekleme
Visual Studio düzenleyicisinde okuma ve farklı bir bilgisayara diller gezinme nasıl destekler ve diğer diller için Visual Studio Düzenleyicisi desteği eklemek için ne hakkında bilgi edinin.  
  
## <a name="syntax-colorization-statement-completion-and-navigate-to-support"></a>Söz dizimi renklendirme, deyim tamamlama ve gitmek için destek  
 Visual Studio düzenleyicisinde söz dizimi renklendirme, deyim tamamlama ve gitmek için gibi özellikleri, daha fazla kolayca okumasına, oluşturmasına ve kodunuzu düzenleyin yardımcı olabilir. Aşağıdaki ekran görüntüsünde Perl komut dosyasını Visual Studio'da düzenleme bir örneği gösterir. Söz dizimi, otomatik olarak renklendirilir. Örneğin, kodda açıklamalar yeşil renkte kodudur siyah yolları kırmızı ve deyimleri mavi. Visual Studio düzenleyicisinde söz dizimi renklendirme desteklediği herhangi bir dil için otomatik olarak uygular. Ayrıca, bilinen dil anahtar sözcüğü veya nesne girmek başladığınızda, deyim tamamlama olası deyimleri ve nesnelerin bir listesini görüntüler. Deyim tamamlama kodu daha hızlı ve kolay bir şekilde oluşturmanıza yardımcı olabilir.  
  
 ![Perl komut söz dizimi renklendirme](../ide/media/vside_perledit.png "VSIDE_PerlEdit")  
  
 Visual Studio şu anda sağlar söz dizimi renklendirme ve temel deyim tamamlama kullanarak aşağıdaki diller için desteği [TextMate aynı](https://manual.macromates.com/en/language_grammars). Sık kullanılan dilinizi tabloda değilse, ancak, endişelenmeyin - ekleyebilirsiniz.  
  
|||||||  
|-|-|-|-|-|-|  
|.Bat uzantılarını dener|F#|Java|Markdown|Rust|Visual Basic|  
|Clojure|Git|JavaDoc|Objective-C|ShaderLab|C#|  
|CMake|Modaya uygun|JSON|Perl|ShellScript|Visual C++|  
|CoffeeScript|HTML|DAHA AZ|Python|SQL|VBNet|  
|CSS|INI|LUA|R|Swift|XML|  
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
  
## <a name="adding-support-for-non-supported-languages"></a>Desteklenmeyen dilleri desteği ekleme  
 Visual Studio 2015 güncelleştirme 1 ve sonraki sürümlerinde sağlamak Düzenleyicisi'nde dil desteği kullanılarak [TextMate aynı](https://manual.macromates.com/en/language_grammars). Sık kullanılan programlama diliniz şu anda Visual Studio düzenleyicisinde desteklenmiyorsa, ilk olarak, web arama - TextMate paket dil için zaten var olabilir. Ancak, bir bulamazsanız, Visual Studio 2015 güncelleştirme 1 veya daha sonra dil aynı ve kod parçacıkları için bir TextMate paket modeli oluşturarak destek kendiniz ekleyebilirsiniz.  
  
 Visual Studio aşağıdaki klasörde bulunan tüm yeni TextMate aynı ekleyin:  
  
 %userprofile%\\.vs\Extensions  
  
 Durumunuza uygun yoksa bu temel yolu altında aşağıdaki klasörlerde ekleyin:  
  
|Klasör adı|Açıklama|  
|-----------------|-----------------|  
|\\*\<dil adı >*|Dil klasörü. Değiştir  *\<dil adı >* dil adı. Örneğin, **\Matlab**.|  
|\Syntaxes|Dilbilgisi klasör. Dil için dilbilgisi .json dosyaları gibi içeren **Matlab.json**.|  
|\Snippets|Kod parçacıkları klasör. Dili için kod parçacıkları içerir.|  
  
 Windows, % USERPROFILE % yolunu Çözümler: c:\Users\\*\<kullanıcı adı >*. Uzantıları klasörünü, sisteminizde mevcut değilse, bunu oluşturmanız gerekir. Bu klasör zaten mevcutsa gizlenir.  
  
 TextMate aynı oluşturma hakkında daha fazla bilgi için bkz [TextMate - dil aynı giriş: kaynak kodu sözdizimi vurgulama ekleme HTML biçiminde katıştırılmış](https://developmentality.wordpress.com/2011/02/08/textmate-introduction-to-language-grammars/) ve [dil dilbilgisi ve özel oluşturma ile ilgili notlar Tema Textmate paket için](https://benparizek.com/notebook/notes-on-how-to-create-a-language-grammar-and-custom-theme-for-a-textmate-bundle).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio 2013 gidin geliştirmeleri](https://blogs.msdn.microsoft.com/mvpawardprogram/2013/10/22/visual-studio-2013-navigate-to-improvements/)   
 [İzlenecek yol: kod parçacığı oluşturma](../ide/walkthrough-creating-a-code-snippet.md)   
 [İzlenecek Yol: Deyim Tamamlamayı Görüntüleme](../extensibility/walkthrough-displaying-statement-completion.md)