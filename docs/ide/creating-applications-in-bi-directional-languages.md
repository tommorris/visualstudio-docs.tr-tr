---
title: "Çift yönlü dillerde uygulamalar oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Hebrew character display, creating applications
- bi-directional language support, about bi-directional language support
- Arabic language, creating applications
ms.assetid: b56f9795-ed8d-4452-9d49-8ca0b0145d86
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: db7afbc68ab4e02803959dd0ff0b4de92233fece
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="creating-applications-in-bi-directional-languages"></a>Çift Yönlü Dillerde Uygulamalar Oluşturma
Visual Studio sağ Arapça ve İbranice gibi sola, yazılan dillerde düzgün görünen metin uygulamaları oluşturmak için kullanabilirsiniz. Bazı özellikler için kolayca özellikleri ayarlayabilirsiniz. Diğer durumlarda, kodda özellikleri uygulamalıdır.  
  
> [!NOTE]
>  Girin ve çift yönlü diller görüntülemek için uygun dili ile yapılandırılmış Windows sürümü ile çalışmalısınız. Bu uygun dil paketi yüklü olan Windows İngilizce sürümünü veya Windows uygun şekilde yerelleştirilmiş sürümü olabilir.  
  
## <a name="types-of-application-that-support-bi-directional-languages"></a>Uygulama bu destek çift yönlü diller türleri  
  
1.  Windows uygulamaları. Çift yönlü metin, sağdan sola okuma sırası ve (windows, menüler, iletişim kutuları ve benzeri düzeni ters) yansıtma desteği içeren tam çift yönlü uygulamaları oluşturabilirsiniz. Yansıtma dışında bu özellikler varsayılan olarak veya özellik ayarları olarak kullanılabilir. Yansıtma kendiliğinden ileti kutuları gibi bazı özellikler desteklenir. Ancak, diğer durumlarda kodda yansıtma uygulamalıdır. Daha fazla bilgi için bkz: [Windows Forms uygulamaları için çift yönlü destek](http://msdn.microsoft.com/Library/7b622fa4-f390-4e4d-b624-83a1917cccf2).  
  
2.  Web uygulamaları. Web Hizmetleri desteği ve UTF-8 ve Unicode metin gönderme, çift yönlü dilleri içeren uygulamalar için uygun hale getirme alma. Bir Web uygulaması çift yönlü destek derecesini kullanıcının tarayıcısının bu çift yönlü özellikleri ne kadar iyi destekleyen bağımlı olduğu için web istemcisi uygulamalarını tarayıcılar kendi kullanıcı arabirimi için kullanır. Visual Studio'da, Arapça veya İbranice metni, sağdan sola okuma sırası, dosya kodlamasını ve yerel kültür ayarları desteği olan uygulamaları oluşturabilirsiniz. Daha fazla bilgi için bkz: [ASP.NET Web uygulamaları için çift yönlü destek](http://msdn.microsoft.com/Library/5576f9b1-9b86-41ef-8354-092d366bcd03).  
  
3.  Konsol uygulamaları. Konsol uygulamaları metin çift yönlü dil desteği dahil etmeyin. Windows konsol uygulamaları ile nasıl çalıştığı bir sonuç budur.  
  
## <a name="visual-studio-features-that-are-fully-supported"></a>Tam olarak desteklenen visual Studio özellikleri  
 Visual Studio tasarım zamanında bu şekilde çift yönlü diller kullanabilirsiniz:  
  
-   **Metin girişi** Visual Studio Unicode'u destekler, böylece eğer sisteminiz ayarlanmış uygun yerel ve giriş dili, Arapça veya İbranice metin girebilirsiniz. (Arapça Keşide ve Vurgu destekler.)  
  
-   **Nesne adları** çözümleri, projeler, dosyalar, klasörler ve benzeri adları atamak için çift yönlü diller kullanabilirsiniz. Kodda, değişkenleri, sınıflar, nesne, öznitelikler, meta verileri ve diğer öğelerin adları için çift yönlü diller kullanabilirsiniz.  
  
-   **Dosya kodlama** kaydedin ve bir dile özgü veya Unicode kodlama ile dosyaları açın. Daha fazla bilgi için bkz: [nasıl yapılır: açık dosyaları kodlama ile kaydetme ve](../ide/how-to-save-and-open-files-with-encoding.md).  
  
## <a name="features-with-limited-or-no-support"></a>Sınırlı olan veya hiç destek özellikleri  
 Diğer özellikler çift yönlü dil uygulamaları için ortak tam olarak Visual Studio veya bazı durumlarda hiç desteklenmez. Bu güncelleştirmeler şunlardır:  
  
-   **Sağdan sola okuma sırası** varsayılan olarak, Visual Studio'da kullandığınız metin girişi denetimler soldan sağa okuma sırası kullanın. Çoğu durumda, standart Windows hareketleri okuma sırasını değiştirmek için kullanabilirsiniz. Örneğin, özellik değerleri için sağdan sola okuma sırası desteklemek için Özellikler penceresini geçiş yapmak için Ctrl + sağ Shift tuşlarına basabilirsiniz.  
  
     Ancak, sağdan sola okuma sırası Visual Studio'da her yerde desteklenmiyor. Özel durumlar şunlardır:  
  
    -   Her zaman onay kutularını, açılan listeleri ve diğer Visual Studio iletişim kutularındaki denetimler soldan sağa okuma düzenini kullanın.  
  
    -   Kod Düzenleyicisi (ve metin düzenleyici) sağdan sola okuma sırası desteklemiyor. Bir çift yönlü dil metin girebilirsiniz, ancak okuma sırası soldan sağa her zaman.  
  
## <a name="naming-things-using-arabic-or-hebrew-text"></a>Arapça kullanarak nesneleri adlandırma veya İbranice metin  
 Klasörleri, değişkenleri veya diğer nesnelerin adları atamak için Arapça veya İbranice metin kullanabilirsiniz. Arapça ile çalışırken, Keşide ve vurgu işaretleri dahil olmak üzere herhangi bir Arapça karakter kullanabilirsiniz.  
  
 Aşağıdaki öğeleri Arapça veya İbranice kullanarak adlandırılabilir ve Visual Studio'da düzgün ele alınacaktır:  
  
-   Çözüm, proje ve proje yola dahil herhangi bir klasör de dahil olmak üzere, dosya adları. Çözüm Gezgini çözüm ve öğe adları doğru görüntüler.  
  
-   Dosya içerikleri. Açın ya da dosya Unicode kodlama veya seçili bir kod sayfası ile kaydedin.  
  
    > [!NOTE]
    >  Kod Düzenleyicisi özel bir durumdur. Ayrıntılı bilgi için aşağıya bakın.  
  
-   Veri öğeleri. **Sunucu Gezgini** bu öğeleri düzgün görüntülemek ve bunları düzenleme olanak sağlar.  
  
-   Öğeleri Windows panoya kopyalandı.  
  
-   Öznitelikler ve meta veriler.  
  
-   Özellik değeri. Özellikler penceresinde Arapça veya İbranice metin kullanabilirsiniz. Pencere standart Windows tuş vuruşları (CTRL + RightShift için sağdan sola ve CTRL + LeftShift soldan sağa için) kullanarak sağdan sola ve soldan sağa okuma düzeni arasında geçiş yapmanızı sağlar.  
  
-   Kod ve metin. (Aynı zamanda olan metin düzenleyici) Kod düzenleyicisinde adı sınıfları, İşlevler, değişkenleri, özellikleri, dize değişmez değerleri, öznitelikleri ve benzeri Arapça veya İbranice kullanabilirsiniz. Ancak, düzenleyici sağdan sola okuma sırası desteklemiyor; metin her zaman sol kenar boşluğunda başlatır.  
  
    > [!TIP]
    >  Bunları, programlarına kodlamak yerine kaynak dosyalarında dize değişmez değerleri yerleştirmeniz önerilir. Daha fazla bilgi için bkz: [izlenecek yol: Windows Formları yerelleştirme](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5).  
  
    > [!NOTE]
    >  Nasıl, bu dillerde adlandırılan nesnelere başvurmak için tutarlı olması gerekir. Örneğin, Arapça bir değişkeni adlandırırken Keşide kullanırsanız, her zaman bu değişkene başvururken Keşide kullanmalısınız veya hatalar neden.  
  
-   Kod açıklamaları. Arapça veya İbranice yorumlar oluşturabilirsiniz. Açıklama Oluşturucu aracında bu diller de kullanabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çift yönlü destek Windows Forms uygulamaları](http://msdn.microsoft.com/Library/7b622fa4-f390-4e4d-b624-83a1917cccf2)   
 [ASP.NET Web uygulamaları için çift yönlü destek](http://msdn.microsoft.com/Library/5576f9b1-9b86-41ef-8354-092d366bcd03)   
 [Uygulamaları Genelleştirme](../ide/globalizing-applications.md)   
 [Uygulamaları Yerelleştirme](../ide/localizing-applications.md)