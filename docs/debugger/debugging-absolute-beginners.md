---
title: Yeni başlayanlar için hata ayıklama kodu
description: İlk olarak hata ayıklama, Visual Studio ile uygulamalarda hata ayıklama yardımcı olmak için birkaç ilkeleri öğrenin
ms.custom: ''
ms.date: 06/18/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- debugger
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 497479ea7b49581e478534e2f8d83d0dd917a2da
ms.sourcegitcommit: e6b13898cfbd89449f786c2e8f3e3e7377afcf25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/22/2018
ms.locfileid: "36326971"
---
# <a name="how-to-debug-for-absolute-beginners"></a>Başlayanlar için hata ayıklama

Bir hata ayıklayıcısı ile hata ayıklama konusunda çok temellerini öğrenin. Visual Studio gibi bir hata ayıklama aracı denemek hazır hale ve bu uygulamanın hata ayıklamak için çalıştınız ilk kez ise, doğru yerde demektir. Bir hata ayıklayıcısı ilk kez kullandığınızda, umuyoruz (ve beklediğiniz için) normal kullanmakta olduğunuz ne olursa olsun hata ayıklama aracı ASP, tüm hataların kodunuzda göstereceğini. Ne yazık ki, bu kolay değildir. Hata ayıklama öğrenilen bir yetenektir ve zaman ve etkili bir şekilde hata ayıklama öğrenmek için yöntemi alır. Biz hata ayıklamak nasıl öğretmek önce bu nedenle, bazı genel ipuçları ve ilkeler sunuyoruz.

İlk olarak, bu gibi bazı temel soruları yanıtlamak faydalı olabilir "Ne hata ayıklama?" ve "Ne hata ayıklama modu?"

* *Hata ayıklama* hatalar kodunuzdan kaldırma işlemidir.

* *Hata ayıklama modunu* anlamına gelir (kod Yürütülüyor) uygulamanızı çalışırken bir hata ayıklayıcıyı çalışan uygulamanıza eklenmiş olmasıdır. Bir hata ayıklayıcısı ekli, kodunuzu yaptıklarını görebilirsiniz çalışırken. Örneğin, uygulamanızın inceleyebilirsiniz durumu (değişkenleri bakın), bkz. ne işlevleri denir ve hataları bulmaya çalışın. Visual Studio belgelerinde girmenizi istiyoruz genellikle yalnızca dediğimiz hata ayıklama modu, "hata ayıklayıcı Başlat" veya "Hata Ayıklayıcısı'ndaki uygulamanızı çalıştırma".

## <a name="clarify-the-problem-by-asking-yourself-the-right-questions"></a>Sorunu kendi başınıza sağ sorular sorarak açıklamak

Bunu düzeltmek denemeden önce içine çalıştırdığınız sorunu açıklamak için yardımcı olur. Bir sorunla zaten kodunuzda karşılaştık beklediğiniz, aksi takdirde, burada hata ayıklamak nasıl bağlayacağınızı çalışıyor olmayacaktır! Bu nedenle, hata ayıklama başlamadan önce kendinize birkaç soru sorun.

* Ne yapmak için kodunuzu beklediğiniz neydi?

* Bunun yerine ne oldu?

    Uygulamanızı çalışırken bir hatayla (özel) çalıştırdıysanız, iyi bir şey olabilir! Bir özel durum kodu, genellikle bir tür hata çalıştırırken karşılaştı beklenmeyen bir olaydır. [Özel durum Yardımcısı](../debugger/debugger-feature-tour.md#exception) Visual Studio'da hata ayıklama modu içine uygulamanızı koyar, burada özel durum oluştu ve olası düzeltmeleri araştırmanıza yardımcı olması için bir hata iletisi verir, kodunuzda tam yere alır. (Ancak bu makaleyi okuduktan incelemeniz önce son.)

    Başka bir şey oluştuysa, sorunun belirtisi nedir? Bu sorun, kodunuzda oluştuğu şüpheleniyorsanız zaten? Örneğin, bazı metinleri kodunuzu görüntüler, ancak metin yanlıştır, verilerinizi bozuk veya hata çeşit görüntülenecek metni ayarlamak koduna sahip bildiğiniz. Böyle bir sorunu gidermek için büyük olasılıkla Visual Studio hata ayıklayıcısı ekli uygulamanızı başlatın ve değişkenlerinizi aramak gerekir. (Ancak ilk olarak, bu makaleyi okuduktan devam edin.)

## <a name="examine-your-assumptions"></a>Varsayımları inceleyin

Bir hata veya bir hata araştırmak önce belirli bir sonuç beklediğiniz yaptığınız özelliklerinin düşünün. Burada; bu nedenle birkaç kolay hale ancak mutlaka true varsayımlar örnekleri bu uzun bir listesi olabilir.

* Sağ API (diğer bir deyişle, doğru nesne, işlev, yöntemi veya özelliği) kullanıyor. Kullanmakta olduğunuz bir API mevcut düşüncelerinizi yapmak. (API çağrısı hata ayıklayıcısında inceledikten sonra düzeltme seyahat doğru API tanımlamaya yardımcı olmak için belgelerine gerektirebilir.)

* Bir API doğru kullanıyor. Belki de API sağ kullanılan ancak doğru şekilde kullanmadı.

* Kodunuzu herhangi yazım hatalarını yok.

* Kodunuzu bir değişiklik yapıldığında ve görmenizi sağlar sorun ilgisiz olduğu varsayılır.

* Bir değişiklik (örneğin, bir aracı veya kitaplık güncelleştirmesi), ortamınızdaki karşılaştı ve görmenizi sağlar sorun ilgisiz olduğu varsayılır.

* Bir nesne veya belirli bir değere (veya belirli türde bir değer) depolamak için değişken bekleniyordu ancak yoktur.

* Bu kod yeterince iyi hata ayıklamak için anladığınızdan. Genellikle daha yararlıdır kod başkası hata ayıklaması zor. Kodunuzu değilse, süre beklemesini gerekebilir mümkündür kodu önce ne yaptığını öğrenme hata ayıklama, etkili bir şekilde.

    > [!TIP]
    > Küçük başlayın ve çalışan kod ile başlayın! Bazı durumlarda, büyük veya karmaşık bir kod kümesi elde etmek için çalıştığınız çekirdek görev gösteren kod küçük bir parçasını başlatarak düzeltmek daha kolay olur (yani, bir çalışma örneği kopyalayın). Ardından, değiştirin veya hatalar için her bir noktada sınama kodu artımlı olarak, ekleyin.

Varsayımları öğrenerek kodunuzda bir sorunu bulmak için geçen süreyi azaltabilir. Ayrıca, bir sorunu gidermek için geçen süreyi azaltabilir.

## <a name="step-through-your-code-in-debugging-mode-to-find-where-the-problem-occurred"></a>Hata ayıklama modu sorun oluştuğu bulmak için kodunuzu adım adım

Bir özel durum gelmedi, hata ayıklayıcı sorun (veya hatanın belirtisidir) gerçekleştiği tam yerini bulmak için kullanın. Başlamadan önce en iyi sorunun nerede oluşmakta, belirli bölge kodu bulmak için sonra ayarlama yapmak bir [kesme noktası](../debugger/using-breakpoints.md) bu kodu başladığı. Kesme noktaları güvenilir hata ayıklama en temel ve temel özelliğidir. Bir kesme noktası değişkenlerin değerleri veya bellek davranışını göz olabilmesi için Visual Studio çalışan kodunuzu nereye askıya almanız veya kod dalı çalıştırmak destekleyip desteklemediğini belirtir. Bir kod satırı yanındaki sol kenar boşluğunda tıklayarak bir kesme noktası ayarlayabilirsiniz.

![Bir kesme noktası belirleyerek](../debugger/media/dbg-tour-set-a-breakpoint.gif "SetABreakPoint")

Bir kesme noktası ayarladıktan sonra hata ayıklayıcı başlatın (basın **F5** veya **hata ayıklamayı Başlat** düğmesini ![hata ayıklamayı Başlat](../debugger/media/dbg-tour-start-debugging.png "hata ayıklamayı Başlat") içinde hata ayıklama araç) ve kesme ayarladığınız kod yürüttüğünde uygulama duraklatılır (duraklatmak değil, kod yürütmeyi olmadı). Ardından [adım komutları](../debugger/navigating-through-code-with-the-debugger.md) gibi **F10** ve **F11** hata ayıklayıcı ilerleyin ve kodunuzu çalıştırmak için. Hata ayıklama sırasında uygulama kodunuzun gibi normal yürütür. Hata ayıklayıcıda uygulamanızı çalışırken, tanımladığınız sorun için bakın.

> [!NOTE]
> Sorunun nerede oluştuğunu bölge kodu belirlenmesi zordur ise, sorun oluşmadan önce çalıştırılan kodda bir kesme noktası ayarlama ve sorunu görene kadar adım komutlarını kullanmak bildirimi. Aynı zamanda [tracepoints](../debugger/using-breakpoints.md#BKMK_Print_to_the_Output_window_with_tracepoints) oturum iletileri için **çıkış** penceresi. Tarafından günlüğe kaydedilen iletilere göz arayan (ve hangi iletilerin henüz günlüğe haberiniz bile!), bölge kodu sorunlu genellikle ayırabilirsiniz. Bu işlemin Dar Aşağı için birkaç kez yineleyin gerekebilir. Sorun herhangi bir yerde birçok kez yineler (ve bu nedenle yeniden zordur), bir döngü içinde meydana geliyorsa bir [koşullu kesme noktası](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression) yardımcı olabilir.

## <a name="when-you-find-the-region-of-code-with-the-problem-use-the-debugger-to-investigate"></a>Bölge kodu sorunlu bulduğunuzda, hata ayıklayıcı araştırmak için kullanın

Bir sorunun nedenini bulmak için hata ayıklayıcıda uygulamanızı çalıştırırken sorun kodu inceleyin:

* [Değişkenleri incelemek](../debugger/view-data-values-in-data-tips-in-the-code-editor.md) ve içermesi gereken değerlerin türü içerdikleri olup olmadığını denetleyin. Hatalı bir değer bulursanız, hatalı değer nerede ayarlandı Bul (değer belirlendiği bulmak için gerekebilir hata ayıklayıcı yeniden başlatın, bakmak [çağrı yığını](../debugger/how-to-use-the-call-stack-window.md), veya her ikisini de).

* Uygulamanızı beklediğiniz kodu yürütme olup olmadığını denetleyin. (Bir özel durum ve çağrılan özel durum işleyici kodu görene kadar bir özel durum oluştu fark kaydetmedi tanıtıcıları (gizler) kullanıyorsanız Örneğin, kod olabilir.)

## <a name="next-steps"></a>Sonraki adımlar

Bu makalede, birkaç genel hata ayıklama kavramlarını öğrendiniz. Ardından, Visual Studio ile hata ayıklamak öğrenme başlatabilirsiniz.

> [!div class="nextstepaction"]
> [Hata ayıklayıcısı özellik turu](../debugger/debugger-feature-tour.md)
