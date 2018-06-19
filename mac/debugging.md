---
title: Xamarin ile hata ayıklama
description: Hata ayıklama, programlama, ortak ve gerekirse, bir parçasıdır. Olgun bir IDE Mac için Visual Studio tüm dizisi kolay hata ayıklama kolaylaştıran özellikler içerir. Güvenli, veri görselleştirme için hata ayıklama gelen bu makalede Mac için Visual Studio'da hata ayıklama tam olası kullanmayı açıklar
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.technology: vs-ide-debug
ms.assetid: BB7A084D-9AC2-48B5-8076-6C8518796BBA
ms.openlocfilehash: dc1ac1636b27133297e5d616de0a0449517a7c06
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33877144"
---
# <a name="debugging-with-xamarin"></a>Xamarin ile hata ayıklama


Mac için Visual Studio yerel hata ayıklayıcı bir izin verme hata ayıklama desteği Xamarin.iOS, Xamarin.Mac ve Xamarin.Android uygulamaları için vardır.
Mac kullanımlar için Visual Studio [ *Mono yumuşak hata ayıklayıcı*](http://www.mono-project.com/docs/advanced/runtime/docs/soft-debugger/), Visual Studio tüm platformlarda yönetilen kodda hata ayıklama için Mac için izin verme Mono çalışma zamanı içine uygulanmadı.

## <a name="the-debugger"></a>Hata ayıklayıcı

Mac için Visual Studio Mono yumuşak hata ayıklayıcı tüm Xamarin uygulamaları yönetilen (C# veya F #) kodda hata ayıklamak için kullanır. Mono yumuşak hata ayıklayıcı farklıdır normal debuggers Mono çalışma zamanına; yerleşik birlikte operative bir hata ayıklayıcı olması oluşturulan kod ve Mono çalışma zamanı hata ayıklama deneyimini sağlamak üzere IDE ile birlikte çalışır. Mono çalışma zamanı hata ayıklama işlevselliği hakkında daha fazla bilgiyi kablo protokolü aracılığıyla kullanıma sunan [Mono belgelerinde](http://www.mono-project.com/docs/advanced/runtime/docs/soft-debugger-wire-format/).


Sabit hata ayıklayıcıları gibi [LLDB]( http://lldb.llvm.org/index.html) veya [GDB]( https://www.gnu.org/software/gdb/), Bilgi Bankası veya iş Birliği hata ayıklaması programdan olmadan bir programı denetlemek, ancak hala Xamarin uygulamaları olayda hata ayıklarken yararlı olabilir, Yerel iOS veya Android kod hatalarını ayıklamak gerekir.

## <a name="using-the-debugger"></a>Hata ayıklayıcıyı kullanma

Herhangi bir uygulama hata ayıklamayı başlatmak için her zaman yapılandırma ayarlandığından emin olun **hata ayıklama**. Hata ayıklama yapılandırmasını yararlı birtakım, hata ayıklama kesme noktaları gibi veri görselleştiriciler kullanarak ve çağrı yığını görüntüleme desteklemek için araçlar sağlar:

![Hata ayıklama yapılandırması](media/debugging-image_0.png)

## <a name="setting-a-breakpoint"></a>Kesme noktası ayarlama

IDE içinde bir kesme noktası ayarlamak için kesme istediğiniz yere kod satırının numarasını yanındaki düzenleyicinizi kenar boşluğu alanını tıklatın:

![Kenar boşluğunda kesme noktası ayarlama](media/debugging-image0.png)


Kodunuzda giderek ayarlanan tüm kesme noktaları görüntüleyebilirsiniz **kesme noktaları paneli**:

![Kesme noktaları listesi](media/debugging-image0a.png)


## <a name="start-debugging"></a>Hata ayıklama başlatılamıyor

Hata ayıklamayı başlatmak için IDE içinde hedef cihaz veya benzer/öykünücü seçin:

![Hedef cihazı seçin](media/debugging-image1.png)

Ardından tuşlarına basarak uygulamanızı dağıtmak **Yürüt** düğmesini veya **Cmd + return**. Bir kesme noktası isabet zaman kodu vurgulanan sarı olur:

![Vurgu gösteren kesme noktası isabet](media/debugging-image2.png)

Hata ayıklama araçları gibi nesnelerin değerleri incelemek için kullanılan bu noktada, kodunuzda neler olduğunu hakkında daha fazla bilgi almak için kullanılabilir:

![Görselleştirmeleri hata ayıklama](media/debugging-image3.png)

## <a name="conditional-breakpoints"></a>Koşullu kesme noktaları

Ayrıca ayarlayabileceğiniz altında bir kesme noktası gerçekleşmelidir durumlarda dikte kuralları, bu ekleme olarak bilinen bir *koşullu kesme noktası*. Koşullu kesme noktası ayarlamak için erişim **kesme noktası Özellikleri penceresinde**, hangi yapılabilir iki yolla:


* Yeni koşullu kesme noktası eklemek için bir kesme noktası ayarlamak istediğiniz kodu satır numarasını solundaki Düzenleyicisi kenar boşluğu sağ tıklatın ve yeni kesme seçin:


 ![Kesme noktası bağlam menüsü](media/debugging-image4.png)

* Varolan bir kesme noktası için bir koşul eklemek için kesme noktası sağ tıklatın ve **kesme noktası özellikleri**, veya **kesme noktaları paneli**, aşağıda gösterilen kesme noktası Düzenle düğmesini seçin:


 ![Kesme noktaları panelinde varolan kesme düzenleme](media/debugging-image5.png)


Daha sonra gerçekleşecek şekilde kesme altında istediğiniz koşulu girebilirsiniz:

 ![Kesme noktası koşulları Düzenle](media/debugging-image6.png)

## <a name="stepping-through-code"></a>Kod atlama

Bir kesme noktası erişildiğinde hata ayıklama araçları program yürütme üzerinde denetim elde etmenizi sağlar. Mac için Visual Studio dört düğmeleri, çalıştırmak ve kod üzerinden adım sağlayan görüntüler. Mac için Visual Studio'da, bunlar aşağıdaki gibi görünür:

 ![Kod üzerinden adım için düğmeler](media/debugging-image7.png)

Dört düğme şunlardır:

*   **Yürüt** -bu kadar sonraki kesme yürütme kodu başlar.
*   **Step Over** -bu kodun sonraki satırında, yürütülür. Sonraki satıra bir işlev çağrısı ise, Step Over işlevi yürütecek ve kodun sonraki satırında durdurulacak *sonra* işlevi.
*   **Step Into** -bu kodun sonraki satırında, ayrıca yürütülür. Sonraki satıra bir işlev çağrısı ise, Step Into işlevi ilk satırında, satır satır hata ayıklama işlevinin devam etmenize izin vererek durdurur. Sonraki satıra bir işlev değil, aynı Step Over olarak davranır.
*   **Step Out** -bu satırına geçerli işlevi burada çağrıldı döndürür.


## <a name="debugging-monos-class-libraries"></a>Mono'nın sınıf kitaplıkları hata ayıklama
Xamarin ürünleri Mono'nın sınıf kitaplıkları için kaynak kodu ile birlikte gelen ve bu hata ayıklayıcı tek adımda şeyler başlık altında nasıl çalıştığınız incelemek için kullanabilirsiniz.

Bu özellik, hata ayıklama sırasında daha fazla bellek tüketir olduğundan, varsayılan olarak kapalıdır.

Bu özelliği etkinleştirmek için Gözat **Mac için Visual Studio > Tercihler > hata ayıklayıcı** ve emin olun "**yalnızca; proje kodunda hata ayıklama Framework koda adım değil.** " seçenek **seçilmemiş**aşağıda gösterildiği gibi:

 ![Framework'te kod seçeneği adım değil](media/debugging-image8.png)
