---
title: "Visual Studio hata ayıklayıcısı ile kod gidin | Microsoft Docs"
ms.custom: H1Hack27Feb2017
ms.date: 02/07/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.execution
helpviewer_keywords:
- stepping
- debugging [Visual Studio], execution control
- execution, controlling in debugger
ms.assetid: 759072ba-4aaa-447e-8e51-0dd1456fe896
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: f6b83e1be32eb657555131a934f8c11f9567c5bc
ms.sourcegitcommit: 9a2f937e42305db6e3eaa7aadc235b0ba9aafc83
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="navigate-code-with-the-visual-studio-debugger"></a>Visual Studio hata ayıklayıcısı ile kod gidin
Komutlar ve kısayolları hata ayıklayıcı kodda gitmek için ile tanışın ve daha hızlı ve kolay bulmak ve uygulamanızdaki sorunları gidermek hale getirir. Hata ayıklayıcı kodda gidin, ancak uygulamanızın durumunu incelemek veya kendi yürütme akışı hakkında daha fazla bilgi edinin.  
  
## <a name="start-debugging"></a>Hata ayıklama başlatılamıyor  
 Genellikle, bir hata ayıklama oturumu kullanmaya başlamak **F5** (**hata ayıklama** > **hata ayıklamayı Başlat**). Bu komut, uygulamanızın hata ayıklayıcısı ekli başlatır.  
  
 Yeşil ok de hata ayıklayıcıyı başlatır (aynı **F5**).  
  
 ![DBG &#95; Temel kavramları &#95; Başlangıç &#95; hata ayıklama](../debugger/media/dbg_basics_start_debugging.png "DBG_Basics_Start_Debugging")  
  
 Hata ayıklayıcısı ekli uygulamanın başlatmak için birkaç yolu dahil **F11** ([koda adım](#BKMK_Step_into__over__or_out_of_the_code)), **F10** ([kod Adımlama](#BKMK_Step_over_Step_out)), ya da kullanarak **çalıştırmak için imleç**.  Bu seçenekler ne bilgi için bu konudaki diğer bölümlerine bakın.  
  
 Sarı çizginin ayıkladığınızda, sonraki yürütecek kodu gösterir.  
  
 ![DBG &#95; Temel kavramları &#95; BREAK &#95; Mod](../debugger/media/dbg_basics_break_mode.png "DBG_Basics_Break_Mode")  
  
 Hata ayıklama sırasında komutları gibi arasında geçiş yapabilirsiniz **F5**, **F11** ve hızlı bir şekilde istediğiniz bakmak için kod almak için (örneğin, kesme noktaları) Bu konuda açıklanan diğer özellikleri kullanabilirsiniz.  
  
 Yalnızca hata ayıklayıcı duraklatıldığında Yereller penceresinde değişken değerlerini görüntüleme veya Gözcü penceresi ifadeleri değerlendirme gibi birçok hata ayıklayıcı özellikler mevcuttur (olarak da bilinir *kesme modu*). Hata ayıklayıcı duraklatıldığında, uygulama durumu değişkenler, İşlevler sırasında askıya alınır ve nesneler bellekte kalır. Kesme modundayken öğeleri konumlar ve ihlalleri veya hatalar için aranacak durumları inceleyebilirsiniz. Bazı proje türleri için kesme modunda uygulama ayarlamalar yapabilirsiniz. Bu özellikleri gösteren bir video izlemek için bkz: [hata ayıklayıcısı ile çalışmaya başlama](https://www.youtube.com/watch?v=FtGCi5j30YU&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK&index=6).
  
##  <a name="BKMK_Step_into__over__or_out_of_the_code"></a>Satır, koda adım  
 Hata ayıklama sırasında (deyimi her) kodunun her satırda durdurmak için kullanmak **F11** klavye kısayolu (veya **hata ayıklama** > **Step Into** menüsünde).  
  
> [!TIP]
>  Her kod satırının yürütürken, bunların değerleri görmek veya kullanmak için değişkenlerinden gelebilirsiniz [Yereller](../debugger/autos-and-locals-windows.md) ve [izleme](../debugger/autos-and-locals-windows.md) değiştirme değerlerine izlemek için windows.  
  
 Davranışını ilgili bazı ayrıntılar işte **Step Into**:  
  
-   Bir iç içe geçmiş işlev çağrısında **Step Into** adımları en fazla iç içe işlev. Kullanırsanız **Step Into** gibi bir çağrıda `Func1(Func2())`, hata ayıklayıcı adımları işlevdeki `Func2`.  
  
-   Hata ayıklayıcı gerçekte fiziksel satırları yerine kod deyimleri adımları. Örneğin bir `if` yan tümcesi tek bir satırda yazılabilir:  
  
    ```csharp  
    int x = 42;  
    string s = "Not answered";  
    if( int x == 42) s = "Answered!";  
    ```  
  
    ```VB  
    Dim x As Integer = 42  
    Dim s As String = "Not answered"  
    If x = 42 Then s = "Answered!"  
    ```  
  
     Hata ayıklayıcı koşul bu satırına adım, bir adım ve başka olarak sonucu olarak değerlendirir. (Bu örnekte, koşulun doğru olması).  
  
 Görsel olarak çağrı yığınını işlevleri Adımlama sırasında izlemek için bkz: [hata ayıklarken çağrı yığınında yöntemler eşleme](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md).  
  
##  <a name="BKMK_Step_over_Step_out"></a>İşlevler atlanıyor kod üzerinden adım  
 Kod Hata Ayıklayıcısı'ndaki çalıştırırken, genellikle, belirli bir işlev olanlar görmeniz gerekmeyen fark (hakkında önemli değil ya da biliyorsanız gibi çalışır, iyi sınanmış kitaplık kodu). Kod üzerinden geçmek için aşağıdaki komutları kullanın (işlevleri hala doğal olarak, yürütme, ancak hata ayıklayıcı üzerlerine atlar).  
  
|Klavye komutu|Menü komutu|Açıklama|  
|----------------------|------------------|-----------------|  
|**F10**|**Adımlama**|Bir işlev çağrısı geçerli satır içeriyorsa, **Step Over** kod çalışır sonra çağrılan işlev döndükten sonra yürütme kodu ilk satırında askıya alır.|  
|**Shift+F11**|**Dışarı Adım**|**Step Out** kodu çalışmaya devam eder ve geçerli işlevi (hata ayıklayıcı atlar geçerli işlevi aracılığıyla) döndürdüğünde yürütme askıya alır.|  
  
> [!TIP]
>  Giriş noktası uygulamanızda bulmanız gerekiyorsa, başlayın **F10** veya **F11**. Bu komutlar, genellikle, uygulama durumunu incelemek veya kendi yürütme akışı hakkında daha fazla bilgi bulmak istediğiniz faydalıdır.  
  
##  <a name="BKMK_Break_into_code_by_using_breakpoints_or_Break_All"></a>Belirli bir konuma veya işlevi için Çalıştır  
 Tam olarak hangi kodu incelemek istediğiniz bildiğinizde genellikle kodda hata ayıklama için tercih edilen yöntem, bu yöntemleri yararlıdır veya en az hata ayıklamayı başlatmak istediğiniz yeri bildirin.  
  
-   **Kod kümesi kesme noktaları**  
  
     Basit bir kesme noktası kodunuzu ayarlamak için Visual Studio düzenleyicisinde kaynak dosyasını açın. İmleç yürütme askıya alma ve seçin ve bağlam menüsünden görmek için kod penceresinde sağ istediğiniz kod satırında ayarlamak **kesme noktası > Kesme Noktası Ekle** (veya basın **F9**). Satırı yürütülmeden önce hata ayıklayıcısı yürütme sağ askıya alır.  
  
     ![Bir kesme noktası belirleyerek](../debugger/media/dbg_basics_setbreakpoint.png "DBG_Basics_SetBreakpoint")  
  
     Visual Studio'da kesme noktaları zengin bir koşullu kesme noktaları ve tracepoints gibi ek işlevsellik sağlar. Bkz: [kesme noktalarını kullanma](../debugger/using-breakpoints.md).  
  
-   **İmleç konumu çalıştırın**  
  
     İmleç konumu çalıştırmak için imleci yürütülebilir bir kaynağı penceresi kod satırı üzerine getirin. Düzenleyicinin bağlam menüsünde (sağ tıklatma Düzenleyicisi'nde), **çalıştırmak için imleç**. Geçici bir kesme noktası ayarlama gibi budur.

-   **Çalıştırmak için tıklatın** 

    Hata ayıklayıcıda duraklatıldı sırada kodunuzu içinde nokta çalıştırmak için seçin **yürütülmesi için burada** yeşil ok simgesi (gördüğünüz simgeyi bir kod satırı getirildiğinde sırasında). Bu, geçici kesme noktalarını ayarlama gereğini ortadan kaldırır.

    ![Hata ayıklayıcı tıklatın çalıştıran](../debugger/media/dbg-run-to-click.png "DbgRunToClick") 

    > [!NOTE]
    > **I Çalıştır** yeni bir özelliktir [!include[vs_dev15](../misc/includes/vs_dev15_md.md)].
  
-   **El ile koda bölün**  
  
     Kullanılabilir kodun sonraki satırında, çalışan bir uygulama içinde kesme, tercih **hata ayıklama**, **sonu tüm** (klavye: **Ctrl + Alt + Break**). 
  
     Kesme kodu karşılık gelen kaynak olmadan yürütülürken veya simge (.pdb) dosyaları), hata ayıklayıcı görüntüler bir **kaynak dosya bulunamadı** veya **simgeleri bulunamadı** yardımcı olabilecek sayfasında uygun Bul dosyalar. Bkz: [simge (.pdb) belirtin ve kaynak dosyaları](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md). Destekleyici dosyaları erişemiyorsanız, Ayrıştırılmış kod penceresini derleme yönergeleri hala ayıklayabilirsiniz.  
  
-   **Çağrı yığınındaki bir işleve çalıştırın**  
  
     İçinde **çağrı yığını** penceresi (hata ayıklama sırasında kullanılabilir) işlevi seçin, sağ tıklatın ve seçin **çalıştırmak için imleç**. Görsel olarak çağrı yığınını izleme için bkz: [hata ayıklarken çağrı yığınında yöntemler eşleme](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md).  
  
-   **Belirtilen adda bir işlev için çalıştırın**  
  
     Belirtilen işlev ulaşana kadar uygulamanızı çalıştırmak için hata ayıklayıcı anlayabilirsiniz. Çağrı yığını seçin veya işlev adıyla belirtebilirsiniz.  
  
     Bir işlev adına göre belirtmek için **hata ayıklama**, **yeni kesme noktası**, **bölün konumundaki işlev**, işlev ve diğer tanımlama bilgilerini adını girin.  
  
     ![Yeni kesme iletişim kutusu](../debugger/media/dbg_execution_newbreakpoint.png "DBG_Execution_NewBreakpoint")  
  
     İşlev aşırı ya da birden çok ad alanında, istediğiniz işlevleri seçebilirsiniz **kesme noktaları Seç** iletişim kutusu.  
  
     ![Kesme noktaları iletişim kutusu seç](../debugger/media/dbg_execution_overloadedbreakpoints.png "DBG_Execution_OverloadedBreakpoints")  
  
##  <a name="BKMK_Set_the_next_statement_to_execute"></a>Yürütme akışını değiştirmek için işaretçiyi taşıyın  
 Hata ayıklayıcı durdurulduğunda, yürütülecek kod next deyimi ayarlamak için yönerge işaretçisi taşıyabilirsiniz. Bir kaynak veya ayrıştırma penceresi kenar boşluğunda sarı bir ok ucunu yürütülecek next deyimi konumunu işaretler. Bu Ok ucunu taşıyarak, kodu bir kısmı Atla veya daha önce yürütülen bir satırı döndürür. Bu bilinen bir hata içeren kodu bir bölümünü atlanıyor gibi durumlar için kullanabilirsiniz.  
  
 ![İşaretçinin taşıma](../debugger/media/dbg_basics_example3.gif "DBG_Basics_Example3")
  
 Sonraki deyim yürütmek için ayarlamak için aşağıdaki yordamlardan birini kullanın:  
  
-   Bir kaynak penceresinde sarı ok ucunu next deyimi aynı kaynak dosyasına ayarlamak istediğiniz bir konuma sürükleyin.  
  
-   Bir kaynak penceresinde imleci sonraki yürütme, sağ tıklayın ve seçmek istediğiniz satıra ayarlamak **sonraki deyimi Ayarla**.  
  
-   Ayrıştırılmış kod penceresini sonraki yürütme, sağ tıklatın istediğiniz derleme yönergesi üzerinde imleci ayarlamak bir ve **sonraki deyimi Ayarla**.  
  
> [!CAUTION]
>  Sonraki deyim ayarı doğrudan yeni konuma atlamak program sayacı neden olur. Bu komutu dikkatli kullanın:  
>   
>  -   Eski ve yeni yürütme noktaları arasında yönergeleri yürütülmedi.  
> -   Yürütme noktası geriye doğru taşırsanız, müdahalede bulunan yönergeleri geri değildir.  
> -   Sonraki deyim başka bir işlevi veya kapsam genellikle hareket çalışma zamanı hatası veya özel durum çağrı yığını bozulma sonuçlanır. Sonraki deyim için başka bir kapsamda taşımayı deneyin, hata ayıklayıcı içeren bir uyarı iletişim kutusu açılır ve işlemi iptal etmek için bir fırsat sunar. Visual Basic'te, başka bir kapsam veya işlevi next deyimi taşınamıyor.  
> -   Etkin çalışma zamanı denetimleri varsa, yerel C++'da, next deyimi ayarlamak yürütme yönteminin sonuna ulaştığında durum için bir özel duruma neden olabilir.  
> -   Düzenle ve devam et etkin olduğunda, **sonraki deyimi Ayarla** Düzenle ve devam et düzenlemeler yaptıysanız başarısız olamaz yeniden eşleme hemen. Catch bloğu içinde kod düzenlediyseniz, örneğin, oluşabilir. Bu durumda, bir işlem desteklenen bildiren bir hata iletisi görürsünüz.  
  
> [!NOTE]
>  Yönetilen kodda next deyimi aşağıdaki koşullarda taşınamıyor:  
>   
>  -   Sonraki deyim geçerli deyimi daha farklı bir yöntem kullanılıyor.  
> -   Hata ayıklama başlatıldı zaman içinde sadece kullanarak hata ayıklama.  
> -   Çağrı yığını geriye doğru izleme işlemi devam ediyor.  
> -   Bir System.StackOverflowException veya System.Threading.ThreadAbortException özel durum oluşturdu.  
  
 Uygulamanızı etkin olarak çalışırken next deyimi ayarlanamıyor. Sonraki deyim ayarlamak için hata ayıklayıcı kesme modunda olması gerekir.  
  
## <a name="BKMK_Restrict_stepping_to_Just_My_Code"></a>Kullanıcı olmayan koda adım  
 Varsayılan olarak, hata ayıklayıcı denilen bir hata ayıklayıcı tarafından belirlenen hata ayıklama, yalnızca uygulama kodunuzun Göster dener *sadece kendi kodumu*. (Bkz [sadece kendi kodumu](../debugger/just-my-code.md) farklı proje türleri ve diller için nasıl işlediğine ve davranışı nasıl özelleştirebileceğinizi görmek için.) Ancak, bazen hata ayıklarken, framework kod, üçüncü taraf kitaplık kodu veya çağrıları bakmak isteyebilirsiniz işletim sistemine (sistem çağrıları).  
  
 Giderek sadece kendi kodumu devre dışı bırakabilir **Araçları** > **seçenekleri** > **hata ayıklama** ve temizleyin **sadece kendi kodumu etkinleştir** onay kutusu.  
  
 Sadece kendi kodumu devre dışı bırakıldığında, hata ayıklayıcı kullanıcı olmayan koda adım ve kullanıcı olmayan kod hata ayıklayıcı Windows'da görünür.  
  
> [!NOTE]
>  Sadece kendi kodumu aygıt projeleri için desteklenmiyor.  
  
 **Sistem çağrıları adım**  
  
 Başka bir çağrı gibi sistem kodu için hata ayıklama simgeleri yüklemiş ve sadece kendi kodumu etkin değil, bir Sistem çağrısına geçebilirsiniz.  
  
 Microsoft simgesi dosyalara erişmek için bkz: [yerel makinenizde değil simge dosyaları bulmak için simge sunucuları kullanın](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md#BKMK_Use_symbol_servers_to_find_symbol_files_not_on_your_local_machine) içinde [belirtin simge (.pdb) ve kaynak dosyaları](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md) konu.  
  
 Hata ayıklarken belirli sistem bileşeni simgelerini yüklemek için:  
  
1.  Modüller penceresi açın (klavye: **Ctrl + Alt + U**).  
  
2.  Simgelerini yüklemek istediğiniz modülü seçin.  
  
     Bakarak simgeleri yüklenen modüllerine sahip anlayabilirsiniz **simgesi durum** sütun.  
  
3.  Seçin **yük simgeleri** bağlam menüsünde.  
  
##  <a name="BKMK_Step_into_properties_and_operators_in_managed_code"></a>Özellikler ve yönetilen kod işleçleri girme  
 Varsayılan hata ayıklayıcı adımlar özellikleri ve yönetilen kod işleçleri üzerinden. Çoğu durumda, bu hata ayıklama daha iyi bir deneyim sağlar. Özellikleri veya işleçleri Adımlama etkinleştirmeyi seçerseniz **hata ayıklama** > **seçenekleri**. Üzerinde **hata ayıklama** > **genel** sayfasında, Temizle **özellikleri ve işleçler (sadece yönetilen) Adımlama** onay kutusu