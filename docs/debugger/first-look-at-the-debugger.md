---
title: "Visual Studio hata ayıklayıcısı ile çalışmaya başlama | Microsoft Docs"
ms.custom: H1Hack27Feb2017
ms.date: 02/07/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: get-started-article
ms.assetid: 0b3138c4-b840-446a-a15c-10ed8e2dd050
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: a969a75a7c0cda89d040b8829fc8313974646c07
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="get-started-with-the-visual-studio-debugger"></a>Visual Studio hata ayıklayıcısı ile çalışmaya başlama
Visual Studio hata ayıklayıcısı herhangi bir dilde kullanımı kolaydır. Basit bir C# programı hata ayıklamak nasıl burada göstereceğiz, ancak C++ ve JavaScript gibi başka bir dilde kodu aynı adımları uygulayabilirsiniz.

Benzer özellikleri gösteren bir video izlemek için bkz: [hata ayıklayıcısı ile çalışmaya başlama](https://www.youtube.com/watch?v=FtGCi5j30YU&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK&index=6).
  
##  <a name="BKMK_Start_debugging_a_VS_project"></a>Temel C# projesinde hata ayıklama  
 Basit bir C# konsol uygulaması ile başlayalım (**Dosya > Yeni > Proje**seçeneğini belirleyip **Visual C#** ve ardından **konsol uygulaması**). Hiçbir zaman önce Visual Studio çalıştıysanız bkz [izlenecek yol: basit bir uygulama oluşturmak](../ide/walkthrough-create-a-simple-application-with-visual-csharp-or-visual-basic.md). **Ana** yöntemi yalnızca 1 10 kez bir tamsayı değişken ekler ve sonuç konsola yazdırır:  
  
```CSharp  
static void Main(string[] args)  
{  
    int testInt = 0;  
    for (int i = 1; i <= 10; i++)  
    {  
        testInt += 1;  
    }  
    Console.WriteLine(testInt);  
}  
```  
  
 Bu kod yapı içinde **hata ayıklama** yapılandırma. Bu yapılandırma, varsayılan olarak ayarlanır. Yapılandırmaları hakkında daha fazla bilgi için bkz: [derleme yapılandırmalarını anlama](../ide/understanding-build-configurations.md).  
  
 Bu kod hata ayıklayıcısı'ndaki tıklayarak çalıştırın **hata ayıklama > hata ayıklamayı Başlat** (veya **Başlat** araç çubuğunda, veya **F5**). Herhangi bir şey konsol penceresinde yazdırıldığı olup olmadığını gerçekte bildiremez uygulama hemen, çıkış.  
  
 Kesme noktası ayarlama ve şimdi Adımlama konsol penceresini görmek için yürütme yetecek kadar uzun süre durdurabilirsiniz. Bir kesme noktası ayarlamak için imlecinizi koyun `Console.WriteLine` satırı ve'ı tıklatın **hata ayıklama > Yeni kesme noktası > işlevi kesme noktası**, ya da aynı satırında sol kenar boşluğunda tıklamanız yeterlidir. Kesme noktası aşağıdaki gibi görünmelidir:  
  
 ![Bir kesme noktası belirleyerek](../debugger/media/getstartedbreakpoint.png "GetStartedBreakpoint")  
  
 Kesme noktaları hakkında daha fazla bilgi için bkz: [kullanarak kesme noktaları](../debugger/using-breakpoints.md).  
  
##  <a name="BKMK_Inspect_Variables"></a>Değişkenleri inceleyin.  
 Genellikle hata ayıklama, belirli bir noktada beklediğiniz değerleri içermeyen değişkenleri bulma içerir. Değişkenleri inceleyebilirsiniz yollardan bazılarını göstereceğiz.  
  
 Hata ayıklamayı yeniden başlatın. Yürütme durdurur önce `Console.WriteLine` kodu yürütür. Şimdi adımla yürütmek için neden olabilir (tıklatın **hata ayıklama > Step Over** veya **F10**). Bu durumda, seçtiğiniz **Step Into** (**F11**) ve aynı sonucu; onayınızı fark daha sonra açıklayacağız. Son büyük ayraç yönteminin satırıyla sarı kapatmış. Konsol penceresine bakın. Görmeniz gerekir **10**.  
  
 Üzerine getirin **testInt** değişken bir veri ipucunda geçerli değerini görüntülemek için.  
  
 ![DBG &#95; Temel kavramları &#95; veri &#95; İpuçları](../debugger/media/dbg_basics_data_tips.png "DBG_Basics_Data_Tips")  
  
 Yalnızca kod penceresini görmeniz gerekir **otomobiller**, **Yereller**, ve **izleme** windows. Bu windows değişkenlerin geçerli değerleri yürütme aynı anda gösterin. Her iki **otomobiller** ve **Yereller** windows Göster **testInt** değerini **10**.  
  
 ![Hata ayıklama sırasında otomatik değişkenler penceresi](../debugger/media/getstartedwindows.png "GetStartedWindows")  
  
 Bu windows hakkında daha fazla bilgi için bkz: [otomobiller ve yerel Windows](../debugger/autos-and-locals-windows.md).  
  
 Değişken değeri biz program aracılığıyla yol olarak nasıl değiştiğini görelim. Bir kesme noktası ayarlayın `testInt += 1;` satır ve hata ayıklamayı yeniden başlatın. Görmelisiniz **testInt** içinde **Yereller** ve **otomobiller** Windows **0**, ve **ı** olan**1**. Ne zaman devam hata ayıklama (**hata ayıklama > devam**, veya **devam** araç çubuğunda veya **F5**), görebilirsiniz değerini **testInt** değişikliklerini **1**, ardından **2**ve benzeri. Bu değişikliklerini aramaktan şikayetçi aldığınızda, kesme noktası kaldırma (**hata ayıklama > kesme**, veya kenar boşluğunda tıklayın) ve hata ayıklama devam edin. Tüm kesme noktalarını kaldırmak istiyorsanız, tıklatın **hata ayıklama > Tüm kesme noktalarını silmek**, veya **CTRL + SHIFT + F9**, tıklatıp **Evet** soran iletişim kutusunda **yapın Tüm kesme noktalarını kaldırmak mı istiyorsunuz?** .  
  
## <a name="stepping-into-and-over-function-calls"></a>İçine ve işlev çağrıları üzerinden Adımlama  
 Hata ayıklayıcı deyimi-by-deyimi içinde kod yürütebilir (**Step Into**) veya hata ayıklayıcı işlevleri atlar sırada kod yürütebilir (**Step Over**) () içinde daha ilgi koduna hızla almak için işlev kodu hala yürütülür). Her iki yöntemde de aynı hata ayıklama oturumu arasında geçiş yapabilirsiniz.  
  
 Arasındaki farkı görmek için **Step Into** ve **Step Over**, başka bir yöntem kullanarak adlı bir yöntem eklemek ihtiyacımız. C# uygulaması için bir yöntem ekleyin ve ana yöntemi çağırın. Kod aşağıdakine benzer görünmelidir:  
  
```CSharp  
static void Main(string[] args)  
{  
    Method1();  
    Console.WriteLine("end");  
}  
  
private static void Method1()  
{  
    Console.WriteLine("in Method1");  
}  
```  
  
 Bir kesme noktası ayarlayın `Method1();` Main yöntemini çağırın ve hata ayıklamayı Başlat. Yürütme böldüğünde tıklatın **hata ayıklama > Step Into** (veya **Step Into** araç çubuğunda veya **F11**). Yürütme sonlarında yeniden Method1() ilk kaşlı ayraç:  
  
 ![Koda atlama](../debugger/media/getstartedstepinto.png "GetStartedStepInto")  
  
 Hata ayıklamayı durdurun ve yeniden başlatın ve yürütme kesme noktasında böldüğünde tıklatın **hata ayıklama > Step Over** (veya **Step Over** araç çubuğunda veya **F10**). Yürütme keser yeniden adresindeki `Console.WriteLine("end");`.  
  
 Hata ayıklayıcısını kullanmaya kodda gezinme hakkında daha fazla bilgi edinmek istiyorsanız bkz [hata ayıklayıcısı ile kodlarda gezinme](../debugger/navigating-through-code-with-the-debugger.md).