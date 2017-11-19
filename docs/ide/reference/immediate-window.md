---
title: Komut penceresi | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: VB
f1_keywords: VS.ImmediateWindow
helpviewer_keywords:
- design-time expression evaluation
- Immediate window
- first-chance exception notifications
ms.assetid: d33e7937-73f3-4c69-9df0-777a8713c6f2
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 81856823b511fc89f5f156915f843d4b0202e907
ms.sourcegitcommit: c0422a3d594ea5ae8fc03f1aee684b04f417522e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2017
---
# <a name="immediate-window"></a>Komut Penceresi
**Hemen** penceresi, hata ayıklama ve ifadeler değerlendirmek, deyimlerini yürütmek, değişken değerleri yazdırma ve benzeri için kullanılır. Hesaplanan veya hata ayıklama sırasında geliştirme dili tarafından yürütülen için ifadeler girin imkan tanır. Görüntülenecek **hemen** penceresinde, düzenlemek için bir proje açın ve ardından **Windows** gelen **hata ayıklama** menü ve seçin **hemen**, veya CTRL + ALT + g tuşlarına basın.  
  
 Bu pencereyi sorunu kişiye kullanabilirsiniz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] komutları. Kullanılabilir komutlar dahil `EvaluateStatement`, değişkenleri için değerleri atamak için kullanılabilir. **Hemen** penceresinde IntelliSense de destekler.  
  
## <a name="displaying-the-values-of-variables"></a>Değişkenlerin değerlerini görüntüleme  
 Bu pencere uygulama hata ayıklama sırasında özellikle yararlı olabilir. Örneğin, bir değişkenin değerini denetlemek için `varA`, kullanabileceğiniz [Yazdır komutu](../../ide/reference/print-command.md):  
  
```  
>Debug.Print varA  
```  
  
 Soru işareti (?) için bir diğer ad olduğu `Debug.Print`, bu nedenle bu komut ayrıca yazılabilir:  
  
```  
>? varA  
```  
  
 Bu komutu hem sürümlerini değişkenin değerini döndürür `varA`.  
  
> [!NOTE]
>  Sorun için bir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] komutunu **hemen** penceresinde komutu ile yazdığınızdan gerekir büyüktür işareti (>). Birden çok komut girmek için geçiş **komutu** penceresi.  
  
## <a name="design-time-expression-evaluation"></a>Tasarım zamanı ifade değerlendirmesi  
 Kullanabileceğiniz **hemen** bir işlevi veya alt yordama tasarım zamanında yürütmek için penceresi.  
  
#### <a name="to-execute-a-function-at-design-time"></a>Tasarım zamanında bir işlevi yürütmek için  
  
1.  Aşağıdaki kodu kopyalayın bir [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] konsol uygulaması:  
  
    ```vb
    Module Module1  
  
        Sub Main()  
            MyFunction(5)  
        End Sub  
  
        Function MyFunction(ByVal input as Integer) As Integer  
            Return input * 2  
        End Function  
  
    End Module  
    ```  
  
2.  Üzerinde **hata ayıklama** menüsünde tıklatın **Windows**ve ardından **hemen**.  
  
3.  Tür `?MyFunction(2)` içinde **hemen** penceresi ve Enter tuşuna basın.  
  
     **Hemen** penceresi çalışacağı `MyFunction` ve görüntüleme `4`.  
  
İşlev veya alt yordama bir kesme noktası içeriyorsa, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] yürütme uygun noktada çalışmamasına neden olur. Hata ayıklayıcı windows sonra programın durumunu incelemek için de kullanabilirsiniz. Daha fazla bilgi için bkz: [izlenecek yol: tasarım zamanında hata ayıklama](../../debugger/walkthrough-debugging-at-design-time.md).  
  
Tasarım zamanı ifade değerlendirmesi bir yürütme ortamı kurma başlangıç gerektiren proje türleri kullanamazsınız dahil olmak üzere [!INCLUDE[trprVSTOshort](../../ide/reference/includes/trprvstoshort_md.md)] projeleri, Web projeleri, akıllı aygıt projeleri ve SQL projeleri.  
  
### <a name="design-time-expression-evaluation-in-multi-project-solutions"></a>Birden çok proje çözümü içinde Tasarım zamanı ifade değerlendirmesi  
 Tasarım zamanı ifade değerlendirmesi bağlamının kurarken [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Çözüm Gezgini'nde şu anda seçili proje başvurur. Çözüm Gezgini'nde proje seçtiyseniz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] başlangıç projesi karşı işlevin değerlendirileceği dener. Geçerli bağlamda işlevi değerlendirilemez, bir hata iletisi alırsınız. Çözüm başlangıç projesi değil bir proje işlevinde değerlendirmek çalışıyorsunuz ve hata iletisi, Çözüm Gezgini'nde proje seçmeyi deneyin ve değerlendirme yeniden deneyin.  
  
## <a name="entering-commands"></a>Komutları girme  
 Büyüktür (>) verilirken işaretiyle girmelisiniz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] içindeki komutlar **hemen** penceresi. Önceden düzenlenen komutları kaydırmak için yukarı ve aşağı ok tuşlarını kullanın.  
  
|Görev|Çözüm|Örnek|  
|----------|--------------|-------------|  
|Bir ifade değerlendirin.|İfade bir soru işareti (?) ile yazdığınızdan.|`? a+b`|  
|Geçici olarak komut modu (tek bir komut yürütmek için) hemen modundayken girin.|Büyük bir Sunuş yapma komutunu girin işareti (>).|`>alias`|  
|Komut penceresine geçin.|Girin `cmd` penceresine, büyük bir Sunuş yapma işareti (>).|`>cmd`|  
|Hemen penceresine dönün.|Girin `immed` büyüktür işareti (>) olmadan penceresine.|`immed`|  
  
## <a name="mark-mode"></a>İşaret modu  
 İçinde herhangi bir önceki satırdaki tıklattığınızda **hemen** penceresinde, shift otomatik olarak işareti moduna. Bu, seçin, düzenlemek ve herhangi bir metin düzenleyicisinde olur ve geçerli satıra yapıştırmak gibi önceki komutların metin kopyalamak sağlar.  
  
## <a name="the-equals--sign"></a>Eşittir (=) işareti  
 Girmek için kullanılan penceresi `EvaluateStatement` komutu belirleyen bir eşittir işareti (=) bir karşılaştırma işleci veya atama işleci olarak yorumlanır.  
  
 İçinde **hemen** penceresinde, bir eşittir işareti (=) atama işleci yorumlanır. Bu nedenle, örneğin, komutu  
  
```  
>Debug.EvaluateStatement(varA=varB)  
```  
  
 değişkene atar `varA` değişkenin değerini `varB`.  
  
 İçinde **komutu** penceresinde, buna karşın bir eşittir işareti (=) bir karşılaştırma işleci yorumlanır. Atama işlemlerinde kullanamazsınız **komutu** penceresi. Örneğin, bunu, değişkenlerin değerleri `varA` ve `varB` farklı, sonra komutu  
  
```  
>Debug.EvaluateStatement(varA=varB)  
```  
  
 bir değeri döndürür `False`.  
  
## <a name="first-chance-exception-notifications"></a>İlk fırsat özel durum bildirimleri  
 İlk fırsat özel durum bildirimleri görüntülenen bazı ayarları yapılandırmalarda **hemen** penceresi.  
  
#### <a name="to-toggle-first-chance-exception-notifications-in-the-immediate-window"></a>İlk fırsat özel durum bildirimleri hemen penceresinde geçiş yapmak için  
  
1.  Üzerinde **Görünüm** menüsünde tıklatın **diğer pencereler**, tıklatıp **çıkış**.  
  
2.  Metin alanı sağ **çıkış** penceresinde ve seçin ya da seçimini **özel durum iletilerini**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcısı ile kodlarda gezinme](../../debugger/navigating-through-code-with-the-debugger.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Visual Studio'da hata ayıklama](../../debugger/debugging-in-visual-studio.md)   
 [Hata ayıklayıcı temel bilgileri](../../debugger/debugger-basics.md)   
 [İzlenecek yol: Tasarım zamanında hata ayıklama](../../debugger/walkthrough-debugging-at-design-time.md)   
 [Visual Studio komut diğer adları](../../ide/reference/visual-studio-command-aliases.md)   
 [Visual Studio'da normal ifadeler kullanma](../../ide/using-regular-expressions-in-visual-studio.md)