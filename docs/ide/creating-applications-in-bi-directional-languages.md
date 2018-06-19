---
title: Çift Yönlü Dillerde Uygulamalar Oluşturma
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Hebrew character display, creating applications
- bi-directional language support, about bi-directional language support
- Arabic language, creating applications
ms.assetid: b56f9795-ed8d-4452-9d49-8ca0b0145d86
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 576e1f715e1196e7e0b774698fe45b550a1313f8
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31924589"
---
# <a name="creating-applications-in-bi-directional-languages"></a>Çift yönlü dillerde uygulamalar oluşturma

Visual Studio sağ Arapça ve İbranice gibi sola, yazılan dillerde düzgün görünen metin uygulamaları oluşturmak için kullanabilirsiniz. Bazı özellikler için kolayca özellikleri ayarlayabilirsiniz. Diğer durumlarda, kodda özellikleri uygulamalıdır.

> [!NOTE]
> Girin ve çift yönlü diller görüntülemek için uygun dili ile yapılandırılmış Windows sürümü ile çalışmalısınız. Bu uygun dil paketi yüklü olan Windows İngilizce sürümünü veya Windows uygun şekilde yerelleştirilmiş sürümü olabilir.

## <a name="types-of-application-that-support-bi-directional-languages"></a>Çift yönlü dil desteği uygulama türleri

-  Windows uygulamaları. Çift yönlü metin, sağdan sola okuma sırası ve (windows, menüler, iletişim kutuları ve benzeri düzeni ters) yansıtma desteği içeren tam çift yönlü uygulamaları oluşturabilirsiniz. Yansıtma dışında bu özellikler varsayılan olarak veya özellik ayarları olarak kullanılabilir. Yansıtma kendiliğinden ileti kutuları gibi bazı özellikler desteklenir. Ancak, diğer durumlarda kodda yansıtma uygulamalıdır. Daha fazla bilgi için bkz: [Windows Forms uygulamaları için çift yönlü destek](http://msdn.microsoft.com/Library/7b622fa4-f390-4e4d-b624-83a1917cccf2).

-  Web uygulamaları. Web Hizmetleri desteği ve UTF-8 ve Unicode metin gönderme, çift yönlü dilleri içeren uygulamalar için uygun hale getirme alma. Bir Web uygulaması çift yönlü destek derecesini kullanıcının tarayıcısının bu çift yönlü özellikleri ne kadar iyi destekleyen bağımlı olduğu için web istemcisi uygulamalarını tarayıcılar kendi kullanıcı arabirimi için kullanır. Visual Studio'da, Arapça veya İbranice metni, sağdan sola okuma sırası, dosya kodlamasını ve yerel kültür ayarları desteği olan uygulamaları oluşturabilirsiniz. Daha fazla bilgi için bkz: [ASP.NET web uygulamaları için çift yönlü destek](http://msdn.microsoft.com/Library/5576f9b1-9b86-41ef-8354-092d366bcd03).

-  Konsol uygulamaları. Konsol uygulamaları metin çift yönlü dil desteği dahil etmeyin. Windows konsol uygulamaları ile nasıl çalıştığı bir sonuç budur.

## <a name="visual-studio-features-that-are-fully-supported"></a>Tam olarak desteklenen visual Studio özellikleri
 Visual Studio tasarım zamanında bu şekilde çift yönlü diller kullanabilirsiniz:

-   **Metin girişi** Visual Studio Unicode'u destekler, böylece eğer sisteminiz ayarlanmış uygun yerel ve giriş dili, Arapça veya İbranice metin girebilirsiniz. (Arapça Keşide ve Vurgu destekler.)

-   **Nesne adları** çözümleri, projeler, dosyalar, klasörler ve benzeri adları atamak için çift yönlü diller kullanabilirsiniz. Kodda, değişkenleri, sınıflar, nesne, öznitelikler, meta verileri ve diğer öğelerin adları için çift yönlü diller kullanabilirsiniz.

-   **Dosya kodlama** kaydedin ve bir dile özgü veya Unicode kodlama ile dosyaları açın. Daha fazla bilgi için bkz: [nasıl yapılır: kaydedin ve açık dosyaları kodlamayla](../ide/how-to-save-and-open-files-with-encoding.md).

## <a name="features-with-limited-or-no-support"></a>Sınırlı olan veya hiç destek özellikleri
 Diğer özellikler çift yönlü dil uygulamaları için ortak tam olarak Visual Studio veya bazı durumlarda hiç desteklenmez. Bu güncelleştirmeler şunlardır:

**Sağdan sola okuma sırası** varsayılan olarak, Visual Studio'da kullandığınız metin girişi denetimler soldan sağa okuma sırası kullanın. Çoğu durumda, standart Windows hareketleri okuma sırasını değiştirmek için kullanabilirsiniz. Örneğin, basabilirsiniz **Ctrl + RightShift** geçiş yapmak için **özellikleri** özellik değerleri için sağdan sola okuma sırası desteklemek için penceresi.

Ancak, sağdan sola okuma sırası Visual Studio'da her yerde desteklenmiyor. Özel durumlar şunlardır:

-   Her zaman onay kutularını, açılan listeleri ve diğer Visual Studio iletişim kutularındaki denetimler soldan sağa okuma düzenini kullanın.

-   Kod Düzenleyicisi (ve metin düzenleyici) sağdan sola okuma sırası desteklemiyor. Bir çift yönlü dil metin girebilirsiniz, ancak okuma sırası soldan sağa her zaman.

## <a name="naming-things-using-arabic-or-hebrew-text"></a>Arapça veya İbranice metin kullanarak nesneleri adlandırma
 Klasörleri, değişkenleri veya diğer nesnelerin adları atamak için Arapça veya İbranice metin kullanabilirsiniz. Arapça ile çalışırken, Keşide ve vurgu işaretleri dahil olmak üzere herhangi bir Arapça karakter kullanabilirsiniz.

 Aşağıdaki öğeleri Arapça veya İbranice kullanarak adlandırılabilir ve Visual Studio'da düzgün ele alınacaktır:

-   Çözüm, proje ve proje yola dahil herhangi bir klasör de dahil olmak üzere, dosya adları. **Çözüm Gezgini** çözüm ve öğe adları doğru bir şekilde görüntüler.

-   Dosya içerikleri. Açın ya da dosya Unicode kodlama veya seçili bir kod sayfası ile kaydedin.

    > [!NOTE]
    >  Kod Düzenleyicisi özel bir durumdur. Ayrıntılı bilgi için aşağıya bakın.

-   Veri öğeleri. **Sunucu Gezgini** bu öğeleri düzgün görüntülemek ve bunları düzenleme olanak sağlar.

-   Öğeleri Windows panoya kopyalandı.

-   Öznitelikler ve meta veriler.

-   Özellik değeri. Arapça veya İbranice metinde kullanabileceğiniz **özellikleri** penceresi. Pencere standart Windows tuş vuruşları kullanarak sağdan sola ve soldan sağa okuma düzeni arasında geçiş yapmanızı sağlar (**Ctrl + RightShift** sağdan sola için ve **Ctrl + LeftShift** için soldan sağa).

-   Kod ve metin. (Aynı zamanda olan metin düzenleyici) Kod düzenleyicisinde adı sınıfları, İşlevler, değişkenleri, özellikleri, dize değişmez değerleri, öznitelikleri ve benzeri Arapça veya İbranice kullanabilirsiniz. Ancak, düzenleyici sağdan sola okuma sırası desteklemiyor; metin her zaman sol kenar boşluğunda başlatır.

    > [!TIP]
    > Bunları, programlarına kodlamak yerine kaynak dosyalarında dize değişmez değerleri yerleştirmeniz önerilir. Daha fazla bilgi için bkz: [(.NET Framework) masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index).

    > [!NOTE]
    > Nasıl, bu dillerde adlandırılan nesnelere başvurmak için tutarlı olması gerekir. Örneğin, Arapça bir değişkeni adlandırırken Keşide kullanırsanız, her zaman bu değişkene başvururken Keşide kullanmalısınız veya hatalar neden.

-   Kod açıklamaları. Arapça veya İbranice yorumlar oluşturabilirsiniz. Açıklama Oluşturucu aracında bu diller de kullanabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

- [Windows Forms uygulamaları için çift yönlü destek](/dotnet/framework/winforms/advanced/bi-directional-support-for-windows-forms-applications)
- [ASP.NET web uygulamaları için çift yönlü destek](http://msdn.microsoft.com/Library/5576f9b1-9b86-41ef-8354-092d366bcd03)
- [Uygulamaları Genelleştirme](../ide/globalizing-applications.md)
- [Uygulamaları yerelleştirme](../ide/localizing-applications.md)