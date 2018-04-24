---
title: Visual Studio hata ayıklayıcısında kesme noktaları kullanın | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 02/07/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.breakpointswin
- vs.debug.disassembly.insert
- vs.debug.sourcewin.edit
- vs.debug.file
- vs.debug.breakpt.new
- vs.debug.whenbreakpointishit
- vs.debug.breakpt.choose
- vs.debug.breakpt.location.address
- vs.debug.breakpt.constraints
- vs.debug.breakpoints.delete
- vs.debug.breakpt.location.data
- vc.breakpoints
- vs.debug.breakpt.condition
- vs.debug.breakpt.location.function
- vs.debug.breakpoints
- vs.debug.menu.insert
- vs.debug.filenames
- vs.debug.breakpt.action
- vs.debug.sourcewin.insert
- vs.debug.address
- vs.debug.data
- vs.debug.func
- vs.debug.breakpt.location.file
helpviewer_keywords:
- breakpoints, about breakpoints
ms.assetid: 020b2e97-3b3e-4b2c-872d-b5c6025e120e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 80f1ad8f7b3bc4ac1a93718943803d445aa6ca9a
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="use-breakpoints-in-the-visual-studio-debugger"></a>Visual Studio Hata Ayıklayıcısı'ndaki kesme noktalarını kullanma
Hata ayıklayıcı yürütme, belki de kod değişkenlerinin durumunu görmek için veya çağrı yığını aramak için durdurmak istediğinizde kesme noktaları ayarlayabilirsiniz. Bunlar, bir geliştirici araç en önemli hata ayıklama teknikleri biridir.  
  
##  <a name="BKMK_Overview"></a> Kaynak kodu satır kesme noktası ayarlama  
 Kaynak kodu dosyasının sol kenar boşluğunda tıklayarak ya da bir kod satırına imlecinizi koyma ve F9 tuşlarına basarak bir satır kesme noktası kaynak kodunda ayarlayın. Sol kenar boşluğunda kırmızı bir nokta olarak kesme görünür ve kod satırı de renkli:  
  
 ![Bir kesme noktası belirleyerek](../debugger/media/basicbreakpoint.png "BasicBreakpoint")  
  
 Bu kod hata ayıklayıcısı'ndaki çalıştırdığınızda, o satırdaki kod yürütülmeden önce kesme noktası isabet her çalışmayı durdurur. Kaynak kodu satır sarı renkli:  
  
 ![Kesme noktası yürütme durduruldu](../debugger/media/breakpointexecution.png "BreakpointExecution")  
  
 Bu noktada değerini `testInt` hala 1'dir.  
  
 Değişken değerleri ve çağrı yığınına dahil olmak üzere uygulamanın geçerli durumunda bakabilirsiniz. Çağrı yığını hakkında daha fazla bilgi için bkz: [nasıl yapılır: çağrı yığını penceresinde kullanmak](../debugger/how-to-use-the-call-stack-window.md).  
  
 Herhangi bir yürütülebilir kod satırında bir kesme noktası ayarlayabilirsiniz. Örneğin, C# ' ta, yukarıdaki kodu bir kesme noktası Değişken bildiriminde ayarlayabilirsiniz `for` döngü ya da herhangi bir kod içinde `for` döngü, ancak ayarlayamıyor bir kesme noktası ad alanı veya sınıf bildirimleri veya yöntem imzası.  
  
##  <a name="BKMK_Set_a_breakpoint_in_a_source_file"></a> İşlev kesme noktası ayarlama  
  İşlevi çağrıldığında yürütme bozulabilir.
  
1. Açık **kesme noktaları** penceresi ve **yeni > işlevi kesme noktası**.

2. Bir işlev adı girin **işlev adı** kutusu. 

   İşlev belirtimi daraltmak için:
   
   Tam işlev adı kullanın. 
   Örnek: Namespace1.ClassX.MethodA()
   
   Aşırı yüklenen bir işlevin parametre türleri ekleyin. 
   Örnek: MethodA (int, string)
   
   Kullanım '!' simgesi Modülü belirtin.
   Örnek: App1.dll! MethodA
   
   Context işleci yerel C++'kullanın.
   {işlev, [modül]} [+&lt;yöntemi başlangıcı satır uzaklığı&gt;] Örnek: {MethodA, App1.dll}+2

3. İçinde **dil** açılan listesinde, üzerinde koparmak istediğinizden işlevinin belirli dili seçin.
  
##  <a name="BKMK_Set_a_breakpoint_in_a_function"></a> Diğer tür kesme noktalarını ayarlama  
 Ayrıca, çağrı yığınında, Ayrıştırılmış kod penceresini ve, bir veri koşul veya bir bellek adresi yerel C++ kodda kesme noktaları ayarlayabilirsiniz.  
  
## <a name="BKMK_Set_a_breakpoint_in_the_call_stack_window"></a> Çağrı yığını penceresinde bir kesme noktası ayarlama  
 Yürütme yönergesi veya döndüren bir arama işlevi için bir kesme noktası ayarlayarak satır sonu **çağrı yığını** penceresi. Çağrı yığını hakkında daha fazla bilgi için bkz: [nasıl yapılır: çağrı yığını penceresinde kullanmak](../debugger/how-to-use-the-call-stack-window.md). Hata ayıklayıcı yürütme durduruldu gerekir.  
  
1.  Uygulama hata ayıklamayı Başlat ve bekleme yürütme (örneğin, kesme noktasında) durdurulur. Açık **çağrı yığını** penceresi (**hata ayıklama > Windows > çağrı yığını**, veya **CTRL + ALT + C**).  
  
2.  Çağıran işlevi sağ tıklayın ve ardından **kesme noktası > Kesme Noktası Ekle**, veya yalnızca kısayol tuşunu kullanın **F9**.  
  
3.  Sol kenar boşluğunda işlevi çağrısı adının yanındaki çağrı yığınının bir kesme noktası simgesi görünür.  
  
 İçinde **kesme noktaları** penceresinde, çağrı yığını kesme sonraki yürütülebilir yönerge işlevinde karşılık gelen bir bellek konumuna olan bir adresi olarak görünür. Hata ayıklayıcı yürütme yönerge keser.  
  
 Görsel olarak izleme kesme noktaları için kod yürütme sırasında bkz: [hata ayıklarken çağrı yığınında yöntemler eşleme](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md).  
  
## <a name="setting-a-breakpoint-in-the-disassembly-window"></a>Ayrıştırılmış kod penceresini kesme noktası ayarlama  
 Bir derleme yönerge bir kesme noktası ayarlamak için hata ayıklayıcı kesme modunda olması gerekir.  
  
1.  Uygulama hata ayıklamayı Başlat ve bekleme yürütme (örneğin, kesme noktasında) durdurulur. Açık **ayrıştırılmış** penceresi (**hata ayıklama > Windows > ayrıştırılmış**, veya **Ctrl + Alt + D**).  
  
2.  Sol kenar boşluğunda kesme veya imlecinizi yönerge ve tuşuna ayarlamak istediğiniz yönerge tıklatın **F9**.  
  
## <a name="BKMK_set_a_data_breakpoint_native_cplusplus_only"></a>(Yalnızca yerel C++'da) veri kesme noktası ayarlama  
 Veri kesme noktaları yürütme sırasında belirtilen bellek adresi değişiklikleri depolanan bir değer bölün. Değer okuma ancak değişip değişmediğini, yürütme sonu değil. Veri kesme noktaları ayarlamak için hata ayıklayıcı kesme modunda olması gerekir.  
  
1.  Uygulama hata ayıklamayı başlatma ve bir kesme noktası ulaşılana kadar bekleyin. Üzerinde **hata ayıklama** menüsünde seçin **yeni kesme noktası > veri kesme noktası** (veya açmak **kesme noktaları** penceresi seçin **yeni > veri kesme noktası**.  
  
2.  İçinde **adresi** bellek adresi veya bir bellek adresi veren ifade yazın. Örneğin, `&avar` ne zaman bölüneceği değişkeni içeriğini `avar` değişiklikleri.  
  
3.  İçinde **bayt sayısı** açılan listesinde, izlemek için hata ayıklayıcı istediğiniz bayt sayısını seçin. Örneğin, **4**, hata ayıklayıcı dört başlayarak bayt izleneceği `&avar` ve herhangi bir bayt değeri değiştirirseniz bölün.  
  
 Belirli bellek adresleri uygulanabilirliğini veri kesme noktaları bağımlı aklınızda bulundurun.  
  
-   Değişkenin adresini bir hata ayıklama oturumu için sonraki değiştirir. Veri kesme noktaları otomatik olarak hata ayıklama her oturum sonunda devre dışı bırakılır.  
  
-   Veri kesme noktası ayarlarsanız yerel bir değişken, işlev sona erdiğinde etkin kesme noktası kalır, ancak bellek adresi artık geçerli ve kesme davranışını tahmin edilemez. Yerel bir değişken veri kesme noktası ayarladıysanız kaldırın ya da kesme işlevi sonlandırılmadan önce devre dışı bırakın.  
  
 Veri kesme noktaları bu koşullar altında çalışmıyor:  
  
-   Bellek konumuna değil ayıklanacak bir işlem Yazar  
  
-   Bellek konumuna iki veya daha çok işlemler arasında paylaşılır  
  
-   Bellek konumuna çekirdek içinde güncelleştirilir. Örneğin, bellek için 32-bit Windows aktarılırsa `ReadFile` işlevi, bellek çekirdek modundan güncelleştirilir ve hata ayıklayıcı bellek yazma kesin değildir.  
  
## <a name="setting-a-breakpoint-with-a-memory-address-native-c-only"></a>Bellek adresi (yalnızca yerel C++'da) ile kesme noktası ayarlama  
 Sınıfın belirli bir örneği olarak adlandırılan bir yöntem bir kesme noktası ayarlamak için nesneyi adresini de kullanabilirsiniz.  Örnek buradadır:  
  
 Örneğin, bir nesne türü verilen `my_class` adresiyle adlı bir yöntem işlevi kesme noktası ayarlayabilirsiniz `my_method` bu örnekten çağrılır.  
  
1.  Bu sınıfın örneğini örneği sonra herhangi bir yerde bir kesme noktası ayarlayın.  
  
2.  Örnek adresini (sahip dediğimiz `0xcccccccc`).  
  
3.  Tıklatın **hata ayıklama > Yeni kesme noktası > işlev kesme noktası** (veya **ALT + F9, B**).  
  
4.  Aşağıdaki metni ekleyin **işlev adı** kutusunda:  
  
    ```C++  
    ((my_class *) 0xcccccccc)->my_method  
    ```  
  
##  <a name="BKMK_Specify_advanced_properties_of_a_breakpoint_"></a> Kesme noktaları yönetme  
 Kullanabileceğiniz **kesme noktaları** penceresi (**hata ayıklama > Windows > kesme noktaları**, veya **CTRL + ALT + B**) tüm kesme noktaları görmek için çözümünüz içinde ayarladığınız:  
  
 ![Kesme noktaları penceresi](../debugger/media/breakpointswindow.png "BreakpointsWindow")  
  
 **Kesme noktaları** penceresi, kesme, büyük bir çözümde veya kesme noktaları nerede kritik karmaşık bir hata ayıklama senaryoda özellikle yararlı olabilen yönetmek için merkezi bir yer sağlar. Kaydetmek veya bir dizi kesme noktaları konumunu ve durumunu paylaşmak gerekiyorsa, verme ve kesme noktaları yalnızca alma **kesme noktaları** penceresi.  
  
##  <a name="BKMK_Specify_a_breakpoint_condition_using_a_code_expression"></a> Gelişmiş kesme noktaları  
  
## <a name="breakpoint-conditions"></a>Kesme noktası koşullar  
 Koşullar ayarlayarak bir kesme noktası ne zaman ve nerede yürütür kontrol edebilirsiniz.  
  
1.  Kesme noktası sağ tıklayın veya kesme getirin ve ayarları simgesini seçin.  
  
2.  Bağlam menüsünü **koşullar**. Bu açılır **kesme noktası ayarları** penceresi:  
  
 ![Kesme noktası ayarları](../debugger/media/breakpointsettings.png "BreakpointSettings")  
  
 İade **koşullar** kutusu, pencerenin genişletir çeşitli koşullar göstermek için.  
  
 **Koşullu ifade:** koşullu ifade seçtiğinizde, sonra iki koşul seçebilirsiniz: **doğrudur** ve **değiştiğinde**. Seçin **doğrudur** sonu istiyorsanız, ne zaman ifade memnun veya seçin **değiştiğinde** ifade değeri değiştiğinde bölün istiyorsanız.  
  
 Aşağıdaki örnekte yalnızca isabet kesme ayarlarız değerini `testInt` olan **4**:  
  
 ![Kesme noktası koşulun true olması](../debugger/media/breakpointconditionistrue.png "BreakpointConditionIsTrue")  
  
 Aşağıdaki örnekte yalnızca isabet kesme ayarlarız değerini `testInt` değişiklikler:  
  
 ![Değiştiğinde kesme noktası](../debugger/media/breakpointwhenchanged.png "BreakpointWhenChanged")  
  
 Davranış olduğunda değiştirilen alan farklı programlama dillerini farklıdır. Seçerseniz **değiştiğinde** için yerel kodu, hata ayıklayıcı üzerinde ilk değerlendirme kesme noktası isabet olmaz şekilde bir değişiklik olacak şekilde koşul ilk değerlendirmesi göz önünde bulundurun değil. Seçerseniz **değiştiğinde** yönetilen kod için ilk değerlendirmesinden sonra üzerinde kesme noktası isabet **değiştiğinde** seçilir.  
  
 Bir kesme noktası koşulu geçersiz sözdizimi ile ayarlarsanız, bir uyarı iletisi görüntülenir. Geçerli sözdizimi, ancak geçersiz semantiği ile bir kesme noktası koşul belirtirseniz, kesme noktası isabet ilk kez bir uyarı iletisi görüntülenir. Geçersiz Kesme noktası isabet olduğunda her iki durumda da, hata ayıklayıcı yürütme keser. Koşul geçerliyse ve değerlendiren kesme atlanır `false`.  
  
 Koşul hata ayıklayıcı tarafından tanınan geçerli bir ifade olabilir. Geçerli ifadeler hakkında daha fazla bilgi için bkz: [ayıklayıcıdaki ifadeler](../debugger/expressions-in-the-debugger.md).  

> [!NOTE]
> Kullanabileceğiniz **CTRL + Enter** kapatmak için **kesme noktası ayarları** penceresi.
  
## <a name="using-object-ids-in-breakpoint-conditions-c-and-f"></a>Nesne tanımlayıcıları kullanarak kesme noktası koşullarına (C# ve F #)  
 Belirli bir nesnenin davranışını gözlemlemek istediğiniz zaman zamanlar vardır; Örneğin, neden bir nesne birden çok kez bir koleksiyona eklenmiş çıkışı bulmak isteyebilirsiniz. C# ve F #'de, belirli örnekleri için nesne kimlikleri oluşturabilirsiniz [başvuru türleri](/dotnet/csharp/language-reference/keywords/reference-types) ve kesme noktası koşullarında kullanın. Nesne Kimliği hizmetlerinde hata ayıklama ortak dil çalışma zamanı tarafından (CLR) oluşturulur ve nesneyle ilişkilendirilmiş.  Bir nesne kimliği oluşturmak için aşağıdakileri yapın:  
  
1.  Bir kesme noktası, nesne oluşturulduktan sonra biraz zaman kodda ayarlayın.  
  
2.  Hata ayıklama başlatın ve yürütme kesme durduğunda kesme bulun **Yereller** penceresinin sağ tıklatın ve seçin **olun nesne kimliği**.  
  
     Görmeniz gerekir bir **$** bir süre içinde artı **Yereller** penceresi. Bu nesne kimliğidir.  
  
3.  Araştırmak, örneğin koleksiyona eklenecek nesne olduğunda istediğiniz noktada yeni koşullu kesme noktası ekleyin.  
  
4.  Nesne Kimliği koşullu ifade alanını kullanın. Örneğin, bir değişkeni ise `item` koleksiyona eklenecek nesne başvurma, size koyabilirsiniz **öğesi $n ==**, burada **n** nesne kimlik numarasıdır.  
  
     Bu nesne koleksiyona eklenecek olduğunda yürütme noktada çalışmamasına neden olur.  
  
 Daha sonra nesne kimliği silmek istiyorsanız, değişkeni sağ **Yereller** penceresini açın ve seçin **Nesne Kimliği Sil**.  
  
 Nesne tanımlayıcıları zayıf başvurular oluşturmak ve nesne toplanacak engelleyen değil unutmayın. Bunlar, yalnızca geçerli hata ayıklama oturumu için geçerli olur.  
  
## <a name="hit-count"></a>İsabet sayısı  
 Belirli bir sayıda yineleme sonra yanlış davranan kodunuzda bir döngü başlatır şüpheleniyorsanız, art arda basın zorunda yerine kod ilişkili satırı İsabetli Okuma belirtilen sayıda sonra yürütmeyi durdurmak için kesme noktası ayarlayabilirsiniz **F5**  yineleme düzeyine ulaşmak için.  
  
 İçinde **kesme noktası ayarları** penceresinde ayarlanmış koşul **isabet sayısı**. Ardından, yineleme sayısını belirtebilirsiniz. Aşağıdaki örnekte, her bir yineleme üzerinde isabet kesme noktası ayarlayın:  
  
 ![Kesme noktası isabet sayısı](../debugger/media/breakpointhitcount.png "BreakpointHitCount")  
  
## <a name="filter"></a>Filtrele  
 Yalnızca belirtilen cihazlarda veya belirtilen işlemleri ve iş parçacıklarını tetiklenecek bir kesme noktası kısıtlayabilirsiniz.  
  
 İçinde **kesme ayarı**s penceresi ayarlayın koşul **filtre**. Bir veya daha fazla aşağıdaki ifadeler girin.  
  
-   MachineName "ad" =  
  
-   ProcessID değer =  
  
-   İşlem adı: "ad" =  
  
-   ThreadID değer =  
  
-   ThreadName "ad" =  
  
 Dize değerleri çift tırnak içine alın. Kullanarak yan tümceleri birleştirebilirsiniz `&` (ve) `||` (veya) `!` (yok) ve parantez.  
  
##  <a name="BKMK_Print_to_the_Output_window_with_tracepoints"></a> Kesme noktası eylemleri ve Tracepoints  
 Bir tracepoint bir ileti çıkış penceresine yazdırır bir kesme noktası olur. Bir tracepoint programlama dilini geçici izleme deyiminde gibi işlev görebilir.  
  
 İçinde **kesme noktası ayarları** penceresinde, onay **Eylemler** kutusu. Seçin **çıkış penceresine bir ileti günlüğe** içinde **eylem** grubu. Genel bir dize gibi yazdırabilirsiniz **bunu denemedir**. Bir değişken veya ifade değerini dahil etme kaşlı ayraç içine alın.  Biçim belirticiler de kullanabilirsiniz ([C#](../debugger/format-specifiers-in-csharp.md) ve [C++](../debugger/format-specifiers-in-cpp.md)) bir tracepoint dahil edilen değerleri için.
  
 Tracepoint gelindiğinde yürütme ayırmak için temizleyin **yürütme devam** onay kutusu. Zaman **yürütme devam** denetlenir yürütme değil işlemi durduruldu. Her iki durumda da, ileti yazdırılır.  
  
 Aşağıdaki özel anahtar sözcükleri kullanabilirsiniz **ileti**.  
  
|||  
|-|-|  
|**$ADDRESS**|Geçerli yönergesi|  
|**$CALLER**|Arama işlev adı|  
|**$CALLSTACK**|Çağrı yığını|  
|**$FUNCTION**|Geçerli işlev adı|  
|**$PID**|İşlem kimliği|  
|**$PNAME**|İşlem adı|  
|**$TID**|İş parçacığı kimliği|  
|**$TNAME**|İş parçacığı adı|  
|**$TICK**||  
|**$TNAME**||  
  
##  <a name="BKMK_Set_a_breakpoint_at_a_function_return_in_the_Call_Stack_window"></a> Kesme noktası etiketleri  
 Kesme noktası etiketleri yalnızca kullanılan **kesme noktaları** sıralamak ve kesme noktaları listesini filtrelemek için penceresi. Bir kesme noktası için bir etiket eklemek için kesme noktası satırı seçin ve ardından **etiket** bağlam menüsünde.  
  
## <a name="export-and-import-breakpoints"></a>Dışarı ve içeri aktarma kesme noktaları  
 Bir kesme noktası kesme noktasına sağ tıklayıp seçerek bir XML dosyasına aktarabilirsiniz **verme**. Dosya, varsayılan çözüm dizini olarak kaydedilir. Kesme noktaları almak için açın **kesme noktaları** penceresi (**CTRL + ALT + B**) ve sağ ok simgesini (Araç İpucu **kesme noktaları bir dosyadan içe**) .  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[Visual Studio hata ayıklayıcısında kesme noktaları sorun giderme](../debugger/troubleshooting-breakpoints.md)  
[Hata ayıklayıcısı ile kodlarda gezinme](../debugger/navigating-through-code-with-the-debugger.md)
