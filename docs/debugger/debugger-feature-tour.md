---
title: Hata ayıklayıcıya ilk bakış
description: Visual Studio hata ayıklayıcısı farklı özelliklerine hızlı göz atın.
ms.custom: mvc
ms.date: 03/27/2018
ms.technology: vs-ide-debug
ms.topic: quickstart
helpviewer_keywords:
- debugger
ms.assetid: c763d706-3213-494f-b4d2-990b6e1ec456
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: de27a6b3fd5b182ac2fa0ad12ed04e4d1105d9ac
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34691098"
---
# <a name="first-look-at-the-visual-studio-debugger"></a>Visual Studio hata ayıklayıcısı ilk bakma

Bu konu, Visual Studio hata ayıklayıcısı özelliklerini tanıtır. Visual Studio'da kendi uygulamanızı açarak izlemek isterseniz, bunu yapabilirsiniz veya bir örnek uygulamasını kullanarak yanı sıra izleyebilirsiniz [Başlangıç Kılavuzu](../debugger/getting-started-with-the-debugger.md).

Burada açıklanan özellikler, C#, C++, Visual Basic, JavaScript ve (belirtilenler dışında) Visual Studio tarafından desteklenen diğer diller için geçerlidir.

## <a name="set-a-breakpoint-and-start-the-debugger"></a>Bir kesme noktası ayarlayın ve hata ayıklayıcısı başlatın

Hata ayıklamak için uygulamanızı hata ayıklayıcısı ekli uygulama işlemi ile başlamanız gerekir. F5 (**hata ayıklama > hata ayıklamayı Başlat**) Bunun en yaygın yoludur. Ancak, uygulamanızı incelemek için tüm kesme noktalarını ayarlamış olabileceğiniz değil artık sağ kod, böylece biz öncelikle bunu ve hata ayıklama başlatılamıyor.

Kod Düzenleyicisi'nde açık bir dosyanız varsa, kod satırının sol kenar boşluğunda tıklayarak bir kesme noktası ayarlayabilirsiniz.

![Bir kesme noktası belirleyerek](../debugger/media/dbg-tour-set-a-breakpoint.gif "bir kesme noktası ayarlama")

F5 tuşuna basın (**hata ayıklama > hata ayıklamayı Başlat**) ve bulduğu ilk kesme hata ayıklayıcı çalıştırır. Uygulama henüz çalışmıyorsa, F5 hata ayıklayıcı başlar ve ilk kesme noktasında durur.

Kod satırını veya bir bölümünü ayrıntılı olarak incelemek istediğiniz kod bildiğinizde kesme noktaları yararlı bir özelliktir.

## <a name="navigate-code-in-the-debugger-using-step-commands"></a>Kod adım komutlarını kullanarak hata ayıklayıcısında gidin

Gezinti, uygulama kodunuzun daha hızlı hale çoğu komutları için klavye kısayolları sunuyoruz. (Menü komutlarını parantez içinde gösterildiği gibi eşdeğer komutları.)

Hata ayıklayıcısı ekli uygulamanızı başlatmak için F11 tuşuna basın (**hata ayıklama > Step Into**). F11 olan **Step Into** komut ve aynı anda uygulama yürütme bir deyim ilerletir. Uygulama ile F11 başlattığınızda, hata ayıklayıcı yürütülen ilk ifade keser.

![F11 Adımla](../debugger/media/dbg-tour-f11.png "F11 adım içine")

Sarı ok üzerinde hata ayıklayıcı duraklatıldı, deyim Ayrıca uygulama (Bu deyim henüz çalıştırılmadı) noktada durduran temsil eder.

F11 yürütme akış çoğu ayrıntılı incelemek için iyi bir yoludur. (Daha hızlı kod üzerinden taşımak için bazı diğer seçenekleri de gösteriyoruz.) Varsayılan olarak, hata ayıklayıcı kullanıcı olmayan kod atlar (daha ayrıntılı bilgi isterseniz bkz [sadece kendi kodumu](../debugger/just-my-code.md)).

>[!NOTE]
> Yönetilen kodda özellikleri ve işleçler (varsayılan davranış) otomatik olarak adım için bildirim isteyip istemediğinizi soran bir iletişim kutusu görürsünüz. Ayarı değiştirmek istiyorsanız, devre dışı daha sonra **özellikleri ve işleçleri Adımlama** ayarı **Araçlar > Seçenekler** menüsünün altında **hata ayıklama**.

## <a name="step-over-code-to-skip-functions"></a>İşlevler atlamak için kod adım

Bir işlev veya yöntem çağrısı kod satırında olduğunda F10 tuşlarına basabilirsiniz (**hata ayıklama > Step Over**) F11 yerine.

F10 işlevler veya yöntemler (kod hala çalıştırır), uygulama kodunuzda içine atlamadan hata ayıklayıcı ilerler. F10 tuşlarına basarak ilgilendiğiniz değil kodu üzerinden atlayabilirsiniz. Bu şekilde, hızlı bir şekilde daha ilgilendiğiniz kodu alabilirsiniz.

## <a name="step-into-a-property"></a>Bir özellikte adım

Hata ayıklayıcı atlar yönetilen özellikleri ve alanları üzerinde varsayılan olarak daha önce belirtildiği gibi ancak **içine belirli adım** komutu bu davranışı geçersiz kılmanıza olanak sağlar.

Bir özelliği veya alanı sağ tıklatın ve seçin **içine belirli adım**, kullanılabilir seçeneklerden birini seçin.

![Adım belirli](../debugger/media/dbg-tour-step-into-specific.png "özel adımla")

Bu örnekte, **içine belirli adım** bize kodunu alır `Path.set`.

![Adım belirli](../debugger/media/dbg-tour-step-into-specific-2.png "özel adımla")

## <a name="run-to-a-point-in-your-code-quickly-using-the-mouse"></a>Kodunuzda hızla fareyle üzerine Çalıştır

Hata ayıklayıcı karşın, bir satır kod kadar üzerine gelerek **çalıştırmak için tıklatın** (burada Çalıştır yürütme) düğmesini ![tıklatın çalıştırmak](../debugger/media/dbg-tour-run-to-click.png "RunToClick") soldaki bölmede görünür.

![I Çalıştır](../debugger/media/dbg-tour-run-to-click-2.png "çalıştırmak için tıklatın")

> [!NOTE]
> **Tıklatın çalıştırmak** (burada Çalıştır yürütme) düğmesini yeni [!include[vs_dev15](../misc/includes/vs_dev15_md.md)].

Tıklatın **tıklatın çalıştırmak** (burada Çalıştır yürütme) düğmesi. Hata ayıklayıcı tıklattığınız kod satırına ilerler.

Bu düğme kullanarak geçici bir kesme noktası ayarlama benzer. Bu komut ayrıca hızlı bir şekilde görünen bir uygulama kodu bölge içinde dolaşma için kullanışlıdır. Kullanabileceğiniz **tıklatın çalıştırmak** herhangi bir açık dosya.

## <a name="advance-the-debugger-out-of-the-current-function"></a>Hata ayıklayıcı geçerli işlevi dışında ilerleyin

Bazı durumlarda, hata ayıklama oturumu devam ancak bu süreç boyunca tüm geçerli işlevi aracılığıyla hata ayıklayıcı ilerletmek isteyebilirsiniz.

Shift + F11 tuşlarına basın (veya **hata ayıklama > dışarı adım**).

Bu komut, uygulama yürütme sürdürür (ve hata ayıklayıcısı ilerler) kadar geçerli işlevi döndürür.

## <a name="run-to-cursor"></a>İmleci çalıştırın

Tuşuna basarak hata ayıklayıcıyı **durdurma hata ayıklama** kırmızı düğme ![durdurma hata ayıklama](../debugger/media/dbg-tour-stop-debugging.png "durdurma hata ayıklama") ya da Shift + F5'e.

Uygulamanızı kod satırı sağ tıklatın ve seçin **çalıştırmak için imleç**. Bu komut, hata ayıklama başlatır ve geçici bir kesme noktası geçerli kod satırında ayarlar.

![İmleci çalıştırmak](../debugger/media/dbg-tour-run-to-cursor.png "için imleç çalıştırın")

Hata ayıklayıcı kesme noktası ayarlarsanız, bu trafik ilk kesme duraklatır.

Seçtiğiniz kod satırı ulaşana kadar F5 tuşuna basın **çalıştırmak için imleç**.

Bu komut, kod düzenleme ve hızlı bir şekilde geçici bir kesme noktası ayarlayın ve hata ayıklayıcısı başlatmak istediğinizde yararlıdır.

> [!NOTE]
> Kullanabileceğiniz **çalıştırmak için imleç** içinde **çağrı yığını** hata ayıklarken penceresi.

## <a name="restart-your-app-quickly"></a>Uygulamanızı hızlı bir şekilde yeniden başlatın

Tıklatın **yeniden** ![yeniden uygulama](../debugger/media/dbg-tour-restart.png "yeniden uygulama") hata ayıklama araç çubuğu düğmesini (**Ctrl + Shift + F5**).

Bastığınızda **yeniden**, uygulama durdurup hata ayıklayıcı karşı zamandan tasarruf sağlar. Hata ayıklayıcı kodu yürüterek isabet ilk kesme noktasındaki duraklatır.

Hata ayıklayıcıyı durdurduktan ve kod düzenleyicisine geri dönmek istiyorsanız, kırmızı Durdur basabilirsiniz ![durdurma hata ayıklama](../debugger/media/dbg-tour-stop-debugging.png "durdurma hata ayıklama") yerine düğmesini **yeniden**.

## <a name="inspect-variables-with-data-tips"></a>Veri ipuçları değişkenlerle inceleyin.

Yararlanabileceğinizi biraz bildiğinize göre uygulama durumu (değişkenler) hata ayıklayıcısı ile inceleniyor başlatmak için iyi bir fırsat sahip. Değişkenleri incelemek sağlayan özellikler hata ayıklayıcısının en kullanışlı özelliklerinden bazıları şunlardır ve yapmak için farklı yolu vardır. Genellikle, bir sorun hata ayıklamak çalıştığınızda değişkenleri olup belirli uygulama durumda beklediğiniz değerlerini depolayan çıkışı bulmak çalışıyorsunuz.

Hata ayıklayıcıda duraklatıldı olsa da, bir nesne fareyle üzerine gelerek ve varsayılan özellik değerini bakın (Bu örnekte, dosya adı `market 031.jpg` varsayılan özellik değeri).

![Veri ipucunu görüntüleme](../debugger/media/dbg-tour-data-tips.gif "veri ipucunu görüntüleme")

Tüm özelliklerini görmek için nesnesini genişletin (gibi `FullPath` özelliği bu örnekte).

Genellikle, hata ayıklama sırasında istediğiniz nesnelerin özellik değerlerini kontrol etmenin hızlı bir yolu ve veri ipuçları yapmak için iyi bir yoldur.

> [!TIP]
> En desteklenen dilleri kodu bir hata ayıklama oturumu ortasında düzenleyebilirsiniz. Daha fazla bilgi için bkz: [Düzenle ve devam et](../debugger/edit-and-continue.md).

## <a name="inspect-variables-with-the-autos-and-locals-windows"></a>Otomatik değişkenler ve yerel windows değişkenlerle inceleyin.

Hata ayıklama sırasında bakmak **otomobiller** Kod düzenleyicisinde sonundaki penceresi.

![Pencere otomobiller](../debugger/media/dbg-tour-autos-window.png "otomatik değişkenler penceresi")

İçinde **otomobiller** penceresinde boyunca değişkenlerin geçerli değerlerini ve bunların türüne bakın. **Otomobiller** penceresi geçerli veya önceki satır üzerinde kullanılan tüm değişkenleri gösterir (içinde C++ pencere gösterir değişkenleri önceki üç kod satırıyla. Dile özgü davranışı için belgelere bakın).

> [!NOTE]
> JavaScript'te, **Yereller** penceresi ancak desteklenen **otomobiller** penceresi.

Ardından, bakmak **Yereller** penceresi. **Yereller** penceresi şu anda kapsamındaki değişkenleri gösterir.

![Yerel öğeler penceresi](../debugger/media/dbg-tour-locals-window.png "yerel öğeler penceresi")

Bu örnekte, `this` nesnesini ve nesne `f` kapsam içindedir. Daha fazla bilgi için bkz: [otomobiller ve yerel Windows incelemek değişkenler](../debugger/autos-and-locals-windows.md).

## <a name="set-a-watch"></a>Bir izleme ayarlama

Kullanabileceğiniz bir **izleme** penceresi bir değişken (veya bir ifade) takip istediğinizi belirtin.

Hata ayıklama, bir nesneyi sağ tıklatın ve seçin **Gözcü Ekle**.

![Gözcü penceresi](../debugger/media/dbg-tour-watch-window.png "Gözcü penceresi")

Bu örnekte Ayarla izleme sahip `f` nesne ve hata ayıklayıcı taşırken değiştirme değeri görebilirsiniz. Diğer değişken windows aksine **izleme** windows her zaman, izlerken değişkenleri Göster (bunlar zaman kapsamının dışına gri).

Daha fazla bilgi için bkz: [izleme ve QuickWatch Windows kullanılarak izleme ayarlama](../debugger/watch-and-quickwatch-windows.md)

## <a name="examine-the-call-stack"></a>Çağrı yığını inceleyin

Tıklatın **çağrı yığını** varsayılan alt sağ bölmede açık olan hata ayıklarken, penceresi.

![Çağrı yığını inceleyin](../debugger/media/dbg-tour-call-stack.png "çağrı yığını inceleyin")

**Çağrı yığını** penceresi içinde yöntemleri ve işlevleri denir sipariş gösterir. Üst çizgi geçerli işlevi gösterir ( `Update` yöntemi bu örnekte). İkinci satır gösterir `Update` çağırıldığı `Path.set` özelliği ve benzeri. Çağrı yığınını incelemek ve bir uygulamanın yürütme akışını anlamak için iyi bir yoludur.

> [!NOTE]
> **Çağrı yığını** penceresi benzer hata ayıklama perspektife Eclipse gibi bazı IDE içinde.

Bu kaynak koduna bakmanız gitmek için kod satırı çift tıklatın ve hata ayıklayıcı tarafından denetlenmekte olan geçerli kapsam, ayrıca değiştirir. Bu hata ayıklayıcı ilerleyin değil.

Sağ menülerden de kullanabilirsiniz **çağrı yığını** başka şeyler için penceresi. Örneğin, belirli işlevleri kesme noktaları ekleme, uygulamasını kullanarak yeniden **çalıştırmak için imleç**ve kaynak kodunu incelemek gidin. Bkz: [nasıl yapılır: çağrı yığınını incelemek](../debugger/how-to-use-the-call-stack-window.md).

## <a name="examine-an-exception"></a>Bir özel durum inceleyin

Hata ayıklayıcı uygulamanızı bir özel durum oluşturduğunda, bir özel durum belirtti kod satırına alır.

![Özel durum Yardımcısı](../debugger/media/dbg-tour-exception-helper.png "özel durum Yardımcısı")

Bu örnekte, **özel durum Yardımcısı** , gösterir bir `System.Argument` özel durumu ve yolun geçerli bir biçimde olmadığını bildiren bir hata iletisi. Bu nedenle, bir yöntemi veya işlev bağımsız değişken bir hata oluştu biliyoruz.

Bu örnekte, `DirectoryInfo` çağrısı depolanan boş dize üzerinde hata vermiş `value` değişkeni.

Özel durum Yardımcısı hataları hata ayıklama yardımcı olabilecek harika bir özelliktir. Ayrıca, hata ayrıntıları görünümü gibi şeyler ve özel durum Yardımcısı bir izleme ekleyin. Ya da gerekirse, belirli özel durum atma koşulları değiştirebilirsiniz.

>  [!NOTE]
> Özel durum Yardımcısı özel durum Yardımcısı'nda değiştirir [!include[vs_dev15](../misc/includes/vs_dev15_md.md)].

Genişletme **Exception ayarlarını** düğümü bu özel durum türü, ancak işleme konusunda daha fazla seçenek görmek için bu tur değişikliği gerekmez!

## <a name="debug-live-aspnet-apps-in-azure-app-service"></a>Azure uygulama hizmeti Canlı ASP.NET uygulamalarında hata ayıklama

**anlık görüntü hata ayıklayıcı** ilgilendiğiniz kod yürüttüğünde üretim uygulamalarınızın bir anlık görüntüsünü alır. Bir anlık görüntüyü almaya hata ayıklayıcı istemek üzere kodunuzda snappoints ve logpoints ayarlayın. Hata ayıklayıcı tam olarak ne üretim uygulamanızın trafiğini etkilemeden sorun oluştu görmenizi sağlar. Anlık görüntü hata ayıklayıcı üretim ortamlarında ortaya çıkan sorunları çözmek için gereken süreyi önemli ölçüde azaltmaya yardımcı olabilir.

![Anlık görüntü hata ayıklayıcıyı başlatma](../debugger/media/snapshot-launch.png "anlık görüntü hata ayıklayıcıyı başlatma")

Anlık görüntü koleksiyonu, Azure App Service'te çalışan ASP.NET uygulamaları için kullanılabilir. .NET Framework 4.6.1 ASP.NET uygulamalarını çalıştırmak veya sonraki bir sürümü ve ASP.NET Core uygulamaları .NET Core 2.0 veya daha sonra Windows üzerinde çalışmalıdır.

Daha fazla bilgi için bkz: [Debug anlık görüntü hata ayıklayıcı kullanarak canlı ASP.NET uygulamaları](../debugger/debug-live-azure-applications.md).

## <a name="view-snapshots-with-intellitrace-step-back-visual-studio-enterprise"></a>IntelliTrace adım geri (Visual Studio Enterprise) sahip görünüm anlık görüntüleri

**IntelliTrace adım sonradan** otomatik olarak bir anlık görüntüsünü her kesme ve hata ayıklayıcı uygulamanızın adım olayını alır. Kaydedilmiş anlık görüntüler, önceki kesme noktaları veya adımları geri dönün ve geçmişte haliyle uygulamanın durumunu görüntülemek etkinleştirin. IntelliTrace adım arka önceki uygulama durumu görmek istediğiniz ancak hata ayıklamayı yeniden başlatın veya istenen uygulama durumu yeniden istemediğiniz durumlarda size zaman kazandırabilir.

Gidin ve görüntülemek anlık görüntülerini kullanarak **adım geriye dönük** ve **İleri** hata ayıklama araç çubuğu düğmeleri. Bu düğmeleri görünür olayları gidin **olayları** sekmesinde **tanılama araçları** penceresi.

![Geri ve İleri düğmelerini adım](../debugger/media/intellitrace-step-back-icons-description.png  "adım geri ve İleri düğmelerini")

Daha fazla bilgi için bkz: [görüntülemek IntelliTrace adım geri kullanarak anlık görüntüsünü](../debugger/how-to-use-intellitrace-step-back.md) sayfası.

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide, hata ayıklayıcı özelliklerinin hızlı bir bakış karşılaşmışsınız. Örnek bir uygulama kullanarak bu özellikleri daha derinlemesine göz isteyebilirsiniz

> [!div class="nextstepaction"]
> [Visual Studio kullanarak hata ayıklamayı öğrenin](../debugger/getting-started-with-the-debugger.md)
