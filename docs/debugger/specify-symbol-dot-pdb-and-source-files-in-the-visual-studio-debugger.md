---
title: Simge (.pdb) ve kaynak dosyaları hata ayıklayıcıda belirtme | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 04/05/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Debugger.Native
- VS.ToolsOptionsPages.Debugger.Symbols
- vs.debug.options.Native
- vs.debug.nosymbols
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- source code
- .dbg files
- source code, managing
- symbols, managing
- .pdb files
- dbg files
- pdb files
- debugger
ms.assetid: 1105e169-5272-4e7c-b3e7-cda1b7798a6b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b0a77ef00ee549006f9b4c6efb255c23543d6746
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="specify-symbol-pdb-and-source-files-in-the-visual-studio-debugger"></a>Visual Studio hata ayıklayıcısında simge (.pdb) ve kaynak dosyaları belirtin
Bir simge dosyası olarak da bilinir program veritabanı (.pdb) dosyası, sınıfları, yöntemleri ve diğer kod projenize derlenmiş yürütülebilir dosyalarda kullanılan tanımlayıcıları için kaynak kodundaki oluşturduğunuz tanımlayıcıları eşler. .Pdb dosyası, kaynak kodundaki deyimleri yürütülebilir dosyalardaki yürütme yönergeleriyle de eşleştirir. Hata ayıklayıcı iki temel bilgiler belirlemek için bu bilgileri kullanır:

* Visual Studio IDE içinde görüntülenecek kaynak dosyası ve satır numarası adı
* Bir kesme noktası ayarlandığında adresindeki durdurmak için yürütülebilir dosya konumu

Sembol dosyası ayrıca orijinal kaynak dosyası konumunu ve isteğe bağlı olarak, kaynak dosyasının alındığı kaynak sunucusunun konumunu içerir.
  
> [!TIP]
> Proje Kaynak kodunuzu dışında kodda hata ayıklama istiyorsanız, Windows kodu veya üçüncü taraf kodu gibi proje çağrılarınızı, .pdb (ve isteğe bağlı olarak, harici kod kaynak dosyalarını) konumunu belirtmeniz gerekir ve bu dosyaları t derleme tam olarak eşleşmesi gerekir Müşterinizle yürütülebilir.  
 
##  <a name="BKMK_Find_symbol___pdb__files"></a> Hata ayıklayıcı simge dosyaları nerede arama? 
  
1.  DLL veya yürütülebilir dosyanın içinde belirtilen konum.  
  
     (Varsayılan olarak, bilgisayarınızda bir DLL veya yürütülebilir dosya oluşturduysanız bağlayıcı, DLL veya yürütülebilir dosya içindeki ilgili .pdb dosyasının yolunu ve dosya adını tam olarak yerleştirir. Hata ayıklayıcı önce DLL'de veya yürütülebilir dosyada belirtilen konumda sembol dosyasının varolup olmadığını denetler. Her zaman bilgisayarınızda derlediğiniz kod için kullanılabilir semboller olduğundan bu yararlıdır.)  
  
2.  .pdb dosyaları aynı klasörde DLL veya yürütülebilir dosya yok.

3. Herhangi bir konumuna [hata ayıklayıcı seçeneklerinde belirtilen](#BKMK_Specify_symbol_locations_and_loading_behavior) simge dosyaları için. 
  
    * Yerel sembol önbellek klasörleri.  
  
    * Tüm ağ, Internet veya yerel simge sunucuları ve (etkinse) Microsoft Simge Sunucusu'nu gibi belirtilir konumları. 

> [!NOTE]
> Visual Studio 2012 önce uzak cihazda yönetilen kod hata ayıklaması olduğunda uzak makinede simge dosyaları put gereklidir. Visual Studio 2012'den başlayarak, tüm simge dosyaları yerel makine üzerinde veya bir konumda yer almalıdır [hata ayıklayıcı seçeneklerinde belirtilen](#BKMK_Specify_symbol_locations_and_loading_behavior).  
  
##  <a name="BKMK_Why_do_symbol_files_need_to_exactly_match_the_executable_files_"></a> Neden simge dosyaları yürütülebilir dosyaları tam olarak eşleşmesi gerekiyor mu?  
Hata ayıklayıcı, yalnızca yürütülebilir dosya oluşturulduğunda, oluşturulan .pdb dosyasıyla tam olarak eşleşen bir yürütülebilir dosya için bir .pdb dosyasını yükler (yani, .pdb özgün olmalı veya özgün .pdb'nin kopyasını olmalıdır). Doğru ve verimli kod oluşturma olan temel görevinin yanı sıra derleyici derleme hızı için de optimize edilmiş olduğundan, kodun kendisi değişmese bile yürütülebilir dosyanın gerçek düzeni değişebilir. Daha fazla bilgi için bkz: [neden Visual Studio gerektiriyor hata ayıklayıcı simge dosyaları tam olarak eşleşen ile oluşturulan ikili dosyalar?](https://blogs.msdn.microsoft.com/jimgries/2007/07/06/why-does-visual-studio-require-debugger-symbol-files-to-exactly-match-the-binary-files-that-they-were-built-with/)
  
##  <a name="BKMK_Specify_symbol_locations_and_loading_behavior"></a> Hata ayıklayıcı simge dosyaları ve yükleme davranışını simgesi burada göründüğünü yapılandırın
 Visual Studio IDE projesinde hata ayıklarken hata ayıklayıcı proje dizininde bulunan simge dosyaları otomatik olarak yükler. Alternatif arama yollarını belirtin ve sunucuları Microsoft, Windows veya üçüncü taraf bileşenler için Sembol **Araçlar > Seçenekler > hata ayıklama > sembolleri**. Hata ayıklayıcı simgelerini otomatik olarak yüklemek için istediğiniz belirli modüller de belirtebilirsiniz. Ve daha sonra etkin bir şekilde hata ayıklama yaparken bu ayarları el ile değiştirebilirsiniz.  
  
1.  Visual Studio'da açın **Araçlar > Seçenekler > hata ayıklama > sembolleri** sayfası.  
  
     ![Araçlar &#45; seçenekleri &#45; hata ayıklama &#45; sembolleri sayfa](../debugger/media/dbg_tools_options_symbols.gif "DBG_Tools_Options_Symbols")  
  
2.  Klasörü seçin ![Araçları&#47; seçenekleri&#47; hata ayıklama&#47;simgeleri klasör simgesine](../debugger/media/dbg_tools_options_foldersicon.png "DBG_Tools_Options_FoldersIcon") simgesi. Düzenlenebilir metin görünür **simge (.pdb) dosya konumları** kutusu.  
  
3.  URL'yi ya da sembol sunucusunun veya sembol konumunun dizin yolunu yazın. Deyimi tamamlama doğru biçimi bulmanıza yardımcı olur.

    Kullanabileceğiniz **Ctrl + Yukarı** ve **Ctrl + aşağı** simge konumları yükleme sırasını değiştirmek için. Tuşuna **F2** bir URL düzenlemek için veya dizin yolu.
  
4.  Sembol artırmak için performans yükleme yolunu yazın simgeleri kopyalanabildiği simge sunucuları tarafından yerel bir dizine **simgeleri bu dizinde önbelleğe** simgeleri kopyalanabilir yerel bir dizine kutusu.  
  
    > [!NOTE]
    >  Sembol önbelleğinizi korunan klasöre (C:\Windows folder veya bunun alt klasörlerinden biri) koymayın. Bunun yerine okuma-yazma klasörü kullanın.  
  
### <a name="specify-symbol-loading-behavior"></a>Sembol yükleme davranışı belirtin 
  
Otomatik olarak yüklenmesini istediğiniz dosyaları belirtin **simge (.pdb) dosya konumları** hata ayıklama başlattığınızda konumları kutusu. Proje dizinindeki sembol dosyaları her zaman yüklenir.  
  
1.  Seçin **tüm modüllerin belirtilmediyse** seçtiğinizde belirttiğiniz dışındaki tüm modülleri tüm simgelerini yüklemek için **belirt dışlanan modülleri** bağlantı.  
  
2.  Seçin **yalnızca modülleri belirtilen** seçeneğini ve ardından **modülleri belirtmesini** otomatik olarak yüklenen istediğiniz dosyaları sembol modülleri listelemek için. Diğer modüller için sembol dosyaları göz ardı edilir.  
  
### <a name="specify-additional-symbol-options"></a>Ek sembol seçenekleri belirtin 
  
Üzerinde aşağıdaki seçenekleri de ayarlayabilirsiniz **Araçlar > Seçenekler > hata ayıklama > Genel** sayfa:  
  
**Yük DLL dışarı aktarmaları (yalnızca yerel)**  
  
Seçildiğinde, DLL dışa aktarma tablolarını yükler. DLL dışa aktarma tablolarının sembole yönelik bilgileri, Windows iletileri, Windows yordamları (WindowProcs), COM nesneleri veya sıralama ile ya da sembolleri olmayan herhangi bir DLL ile çalışıyorsanız yararlı olabilir. DLL dışa aktarma bilgilerini okuma bazı ek okumalar içerir. Bu nedenle, bu özellik varsayılan olarak kapalıdır.  
  
DLL'den dışarı aktarma tablosunda hangi simgeler kullanılabildiğinde görmek için `dumpbin /exports`. Semboller tüm 32-bit sistem DLL için kullanılabilir. Okuyarak `dumpbin /exports` çıkışı, alfasayısal olmayan karakter dahil tam işlevi adını görebilirsiniz. Bu, bir işlev bir kesme noktası ayarlamak için yararlıdır. DLL dışarı aktarma tablolarındaki işlev adları, hata ayıklayıcının başka bir yerinde kesilmiş görünebilir. Aramalar geçerli işlev en üstte (en yoğun şekilde iç içe geçmiş) olacak şekilde arama sırasıyla listelenir. Daha fazla bilgi için bkz: [DUMPBIN/dışarı aktarmalar](/cpp/build/reference/dash-exports).  
  
###  <a name="BKMK_Use_symbol_servers_to_find_symbol_files_not_on_your_local_machine"></a> Simge sunucuları yerel makinenizde değil simge dosyaları bulmak için kullanın  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] hata ayıklama simge dosyaları symsrv protokolünü uygulayan simgesi sunucularından indirebilirsiniz. [Visual Studio Team Foundation Server](http://msdn.microsoft.com/Library/bd6977ca-e30a-491a-a153-671d81222ce6) ve [Windows için hata ayıklama araçları](http://msdn.microsoft.com/library/windows/hardware/ff551063\(v=VS.85\).aspx) simge sunucuları uygulayabilirsiniz iki araçlardır. VS kullanılacak simge sunucuları belirtin **seçenekleri** iletişim kutusu.  
  
 Kullanabileceğiniz sembol sunucuları şunlardır:  
  
 **Microsoft ortak simge sunucuları**  
  
 Bir sistem DLL dosyasına veya bir üçüncü taraf kitaplığına yapılan bir çağrı sırasında oluşan bir çökme hatasını gidermek için, genellikle Windows DLL'leri, EXE'ler, ve cihaz sürücüleri için semboller içeren .pdb dosyalarına gereksinim duyarsınız. Bu sembolleri Microsoft ortak sembol sunucularından elde edebilirsiniz. Microsoft ortak simge sunucuları MDAC, IIS, ISA, ek olarak Windows işletim sistemleri için simgeler sağlamak ve [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].  
  
 Microsoft simge sunucuları kullanmayı tercih **seçenekleri ve ayarları** üzerinde **hata ayıklama** menü ve ardından **simgeleri**. Seçin **Microsoft simge sunucuları**.  
  
 **Bir iç ağdaki veya yerel makinenizde simge sunucuları**  
  
 Ekibiniz veya şirketiniz, kendi ürünleriniz için ve dış kaynaklardan alınan sembollerin önbelleği olarak sembol sunucuları oluşturabilir. Kendi makineniz üzerinde bir sembol sunucusu olabilir. Bir URL veya bir yol olarak simge sunucuları konumu girin **hata ayıklama**/**simgeleri** VS sayfasının **seçeneği iletişim**.  
  
 **Üçüncü taraf simge sunucuları**  
  
 Üçüncü taraf Windows uygulamaları ve kitaplıkları sağlayıcılar internet üzerinden sembol sunucusuna erişim sağlayabilir. Bu simge sunucuları URL'sini de girin **hata ayıklama**/**simgeleri** sayfası  
  
> [!NOTE]
>  Microsoft ortak sembol sunucularından farklı bir sembol sunucusu kullanıyorsanız, sembol sunucusunun ve yolunun güvenilir olduğundan emin olun. Sembol dosyası rastgele yürütülebilir kod içerebileceğinden güvenlik tehditlerine maruz kalabilirsiniz.  
  
###  <a name="BKMK_Find_and_load_symbols_while_debugging"></a> Bulma ve hata ayıklama sırasında simgeleri yükleme  
 Hata ayıklayıcı kesme modundayken, hata ayıklayıcı seçenekleriyle daha önce hariç tutulan veya derleyicinin bulamadığı bir modül için semboller yükleyebilirsiniz. Çağrı Yığını, Modüller, Yereller, Otolar ve tüm Gözcü pencerelerinin kısayol menülerinden sembol yükleyebilirsiniz. Hata ayıklayıcısı sembol veya kaynak dosyalarına sahip olmayan kodu keserse, bir belge penceresi görüntülenir. Burada, eksik dosyaları ve bunları bulup yüklemek için yapılacak eylemler hakkında bilgi bulabilirsiniz.
  
 **Hayır simgeleri yüklenen belge sayfalarının sembolleriyle Bul**  
  
 Hata ayıklayıcının kullanılabilir sembolleri bulunmayan kodlara girebilmesi için çeşitli yollar vardır:  
  
1.  Kodun içine adımlama.  
  
2.  Kodu kesme noktasından veya özel durumdan ayırma.  
  
3.  Farklı bir iş parçacığına geçiş.  
  
4.  Çağrı Yığını penceresinde bir çerçeveyi çift tıklayarak yığın çerçevesini değiştirme.  
  
 Aşağıdaki olaylardan biri gerçekleştiğinde, hata ayıklayıcı görüntüler **Hayır simgeleri yüklenen** bulmak ve gerekli simgeleri yükleme sayfası.  
  
 ![Simgeler yüklenen sayfa](../debugger/media/dbg_nosymbolsloaded.png "DBG_NoSymbolsLoaded")  
  
-   Arama yolları değiştirmek için seçili bir yol seçin veya **yeni** ve yeni bir yol girin. Seçin **yük** yeniden arama yolları ve bulunursa sembol dosyası yüklemek için.  
  
-   Seçin **göz atın ve bulma***yürütülebilir dosya adı***...**  herhangi sembol seçenekleri geçersiz kılmak ve arama yolları yeniden deneyin. Sembol dosyası bulunursa yüklenir veya sembol dosyasını el ile seçmeniz için bir Dosya Gezgini görüntülenir.  
  
-   Seçin **Simge Ayarları Değiştir...**  görüntülemek için **hata ayıklama** > **simgeleri** VS Seçenekleri iletişim kutusu sayfası.  
  
-   Seçin **ayrıştırılmış kodu görüntüleme** ayrıştırılmış bir kez yeni bir pencerede göstermek için.  
  
-   Kaynak veya simge dosyaları bulunamadığında ayrıştırılmış her zaman göstermek için seçin **Seçenekleri iletişim kutusu** her ikisini de seçin ve bağlama **adresi düzeyi hata ayıklamayı etkinleştir** ve **Göster ayrıştırılmış varsa Kaynak mevcut değil**.  
  
     ![Seçenekler &#47; hata ayıklama &#47; genel ayrıştırılmış seçenekleri](../debugger/media/dbg_options_general_disassembly_checkbox.png "DBG_Options_General_disassembly_checkbox")  
  
 **Kısayol menüsünden sembol seçenekleri değiştirme**  
  
 Kesme modunda çalışırken, Çağrı Yığını, Modüller, Yerel Öğeler, Otomatik Öğeler ve tüm İzleme pencerelerinde görüntülenen öğelerin sembollerini bulabilir ve yükleyebilirsiniz. Pencerede bir öğe seçin, kısayol menüsünü açın ve aşağıdaki seçeneklerden birini seçin:  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Yük semboller**|Belirtilen konumlardan simgeleri yüklemeye çalışır **hata ayıklama**/**simgeleri** sayfasında **seçenekleri** iletişim kutusu. Sembol dosyası bulunamazsa, Dosya Gezgini başlatılır, bu sayede aranacak yeni bir konum belirtebilirsiniz.|  
|**Simge yükleme bilgileri**|Yüklenen sembol dosyasının konumunu veya hata ayıklayıcı dosyasını bulamazsanız, aranan konumları gösteren bilgiler sunar.|  
|**Simge Ayarları...**|Açılır **hata ayıklama**/**simgeleri** VS sayfasının **seçenekleri** iletişim kutusu.|  
|**Her zaman otomatik olarak yükleme**|Hata ayıklayıcı tarafından otomatik yüklenen dosya listesine sembol dosyası ekler.|  
  
###  <a name="BKMK_Set_compiler_options_for_symbol_files"></a> Simge dosyaları derleyici seçeneklerini ayarlama  
 Ne zaman projenizi VS IDE içinden derleme ve standart kullanmak **hata ayıklama** yapı yapılandırması, C++ ve yönetilen derleyicileri kodunuz için uygun simge dosyalarını oluşturun. Sembol dosyaları oluşturmak için komut satırında derleyici seçeneklerini de ayarlayabilirsiniz.  
  
 **C++ seçenekleri**  
  
 Program veritabanı (.pdb) dosyası, hata ayıklamayı ve programınızın Hata ayıklama yapılandırmasının artımlı bağlamasına olanak tanıyan proje durum bilgilerini tutar. .Pdb dosyasını ile yapı oluşturulduğunda [/zi veya/zi](/cpp/build/reference/z7-zi-zi-debug-information-format) (C/C++ için).  
  
 İçinde [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)], [/Fd](/cpp/build/reference/fd-program-database-file-name) seçeneği derleyici tarafından oluşturulan .pdb dosyasını adları. Bir proje oluşturduğunuzda [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] sihirbazları kullanarak **/Fd** seçeneği ayarlanmış adlı bir .pdb dosyasını oluşturmak için *proje*.pdb.  
  
 Derleme görevleri dosyası kullanarak C/C++ uygulamanızı oluşturun ve belirtirseniz **/zı** veya **/zı** olmadan **/Fd**, iki .pdb dosyaları ile bitmelidir:  
  
-   VC*x*.pdb, burada *x* Visual C++, örneğin VC11.pdb sürümünü temsil eder. Bu dosya, tek tek OBJ dosyaları için hata ayıklama bilgilerini depolar ve proje derleme görevleri dosyası ile aynı dizinde bulunur.  
  
-   Project.pdb the.exe dosyasının tüm hata ayıklama bilgilerini bu dosyada depolanır. C/C++'ta \debug alt dizininde bulunur.  
  
 Her bir OBJ dosyası oluşturur, C/C++ derleyicisi hata ayıklama bilgileri VC birleştirir*x*.pdb. Eklenen bilgiler türü bilgilerini içerir, ancak işlev tanımları gibi sembol bilgilerini içermez. Her kaynak dosyası gibi ortak üstbilgi dosyaları içerir olsa bile bunu \<windows.h >, bu başlıklarından tür tanımları, yalnızca bir kez, her OBJ dosyasında olmak yerine depolanır.  
  
 Bağlayıcı, projenin EXE dosyasına ilişkin hata ayıklama bilgilerini içeren project.pdb'yi oluşturur. Yalnızca türü bilgileri VC içinde bulunan işlev prototipleri de dahil olmak üzere, tam hata ayıklama bilgileri project.pdb dosyayı içeren*x*.pdb. Her iki .pdb dosyası da artımlı güncelleştirmelere izin verir. Bağlayıcı ayrıca .pdb dosyasının yolunu, oluşturduğu .exe veya .dll dosyasına katıştırır.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Hata ayıklayıcı altında yolu EXE veya DLL dosyasını .pdb dosyasında project.pdb dosyayı bulmak için olarak kullanır. Hata ayıklayıcı .pdb dosyanın bu konumda bulamıyor veya yol geçersiz (örneğin, başka bir bilgisayara proje taşındıysa) olduğunda, hata ayıklayıcı EXE içeren yolu arar, simge yolları belirtilen **seçenekleri** iletişim kutusu (**hata ayıklama** klasörünü **simgeleri** düğüm). Hata ayıklayıcı, hata ayıklaması yapılan yürütülebilir öğeyle eşleşmeyen bir .pdb dosyası yüklemez. Hata ayıklayıcı .pdb dosyası bulamazsa, bir **Bul simgeleri** iletişim kutusu görüntülenirse, simgelerini arama veya ek konumlar arama yolu eklemek için sağlayan.  
  
 **.NET framework seçenekleri**  
  
 Program veritabanı (.pdb) dosyası, hata ayıklamayı ve programınızın hata ayıklama yapılandırmasının artımlı bağlamasına olanak tanıyan proje durum bilgilerini tutar. .Pdb dosyasını ile yapı oluşturulduğunda **/debug**. Uygulamaları derleme **/debug:full** veya **/debug:pdbonly**. İle derleme **/debug:full** debuggable kod oluşturur. İle derleme **/debug:pdbonly** .pdb dosyaları oluşturur ama oluşturmayacak `DebuggableAttribute` JIT Derleyici hata ayıklama bilgileri kullanılabilir olduğunu bildirir. Kullanım **/debug:pdbonly** debuggable olmasını istemediğiniz yayın derlemesi için .pdb dosyaları oluşturmak istiyorsanız. Daha fazla bilgi için bkz: [/Debug (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/debug-compiler-option) veya [/Debug (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/debug).  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Hata ayıklayıcı altında yolu EXE veya DLL dosyasını .pdb dosyasında project.pdb dosyayı bulmak için olarak kullanır. Hata ayıklayıcı .pdb dosyanın bu konumda bulamıyor veya yol geçersiz, hata ayıklayıcı EXE içeren yolu arar ve sembol yolları sonra belirtilen **seçenekleri** iletişim kutusu. Bu yol, genellikle **hata ayıklama** klasöründe **simgeleri** düğümü. Hata ayıklayıcı, hata ayıklaması yapılan yürütülebilir dosyayla eşleşmeyen bir .pdb dosyası yüklemez. Hata ayıklayıcı .pdb dosyası bulamazsa, bir **Bul simgeleri** iletişim kutusu görüntülenirse, simgelerini arama veya ek konumlar arama yolu eklemek için sağlayan.  
  
 **Web uygulamaları**  
  
 Uygulamanızın yapılandırma dosyası (Web.config) hata ayıklama moduna ayarlanmalıdır. Hata ayıklama modu ASP.NET'in dinamik olarak oluşturulan dosyalar için sembol oluşturmasına neden olur ve hata ayıklayıcının ASP.NET uygulamasına eklemesine olanak tanır. Visual Studio hata ayıklamak başlattığınızda Web projeleri şablondan projenizi oluşturduysanız bu otomatik olarak ayarlar.  
  
##  <a name="BKMK_Find_source_files"></a> Kaynak dosyaları bulma  
  
###  <a name="BKMK_Where_the_debugger_searches_for_source_files"></a> Hata ayıklayıcı için kaynak dosyaları nerede arar  
 Hata ayıklayıcı kaynak dosyaları aşağıdaki konumlarda arar:  
  
1.  Hata ayıklayıcı tarafından başlatılan Visual Studio örneğinin IDE'si içinde açık olan dosyalar.  
  
2.  Visual Studio örneğinde açık çözüm dosyaları.  
  
3.  Belirtilen dizin **ortak özellikleri**/**kaynak dosyalarında Hata Ayıkla** çözüm özelliklerini sayfasında. (İçinde **Çözüm Gezgini**, çözüm düğümünü sağ tıklatın ve seçin seçin **özellikleri**. )  
  
4.  Modülün .pdb dosyasının kaynak bilgisi. Bu, modül oluşturulduğunda kaynak dosyanın konumu olabileceği gibi, bir kaynak sunucuya ilişkin komut da olabilir.  
  
###  <a name="BKMK_Find_and_load_source_files_with_the_No_Source___No_Symbols_Loaded_pages"></a> Bulma ve Hayır Source/No simgeleri yüklenen sayfaları ile kaynak dosyalarını yükleme  
 Hata ayıklayıcı kaynak dosyası olduğu kullanılabilir bir konumda yürütme böldüğünde görüntülenir **Hayır kaynak yüklenen** veya **Hayır simgeleri yüklenen** yardımcı olabilecek sayfaları kaynak dosyasını bulmak. **Hayır simgeleri yüklenen** hata ayıklayıcı, aramayı tamamlamak yürütülebilir dosyası için bir simge (.pdb) dosya bulamadığında görüntülenir. Sembol Yok sayfası dosyayı aramak için seçenekler sağlar. Seçeneklerden birini çalıştırdıktan sonra .pdb bulunursa ve hata ayıklayıcı semboller dosyasındaki bilgileri kullanarak kaynak dosyayı alırsa, kaynak görüntülenir. Aksi halde, bir **Hayır kaynak yüklenen** sayfası sorunu açıklayan görüntülenir. Sayfa, sorunu giderebilecek eylemleri gerçekleştirebilen seçenek bağlantıları görüntüler.  
  
###  <a name="BKMK_Add_source_file_search_paths_to_a_solution"></a> Kaynak dosya arama yolları bir çözüme ekleyin  
 Kaynak dosyalarını aramak için ağ veya yerel dizin belirtebilirsiniz.  
  
1.  Çözüm Gezgini'nde çözümü seçin ve ardından **özellikleri** kısayol menüsünden.  
  
2.  Altında **ortak özellikleri** düğümü seçin **kaynak dosyalarında Hata Ayıkla**.  
  
3.  Klasörü tıklatın ![Araçları&#47; seçenekleri&#47; hata ayıklama&#47;simgeleri klasör simgesine](../debugger/media/dbg_tools_options_foldersicon.png "DBG_Tools_Options_FoldersIcon") simgesi. Düzenlenebilir metin görünür **kaynak kodu içeren dizinler** listesi.  
  
4.  Aramak istediğiniz yolu ekleyin.  
  
 Yalnızca belirtilen dizin arandığına dikkat edin. Arama yapmak istediğiniz alt dizinler için girdi eklemeniz gerekir.  
  
###  <a name="BKMK_Use_source_servers"></a> Kaynak sunucular kullanın  
 Yerel makinede kaynak kod olmadığında veya .pdb dosyası kaynak kodla eşleşmediğinde, uygulamada hata ayıklamaya yardımcı olması için Kaynak Sunucuyu kullanabilirsiniz. Kaynak Sunucu, dosya isteklerini alır ve gerçek dosyaları döndürür. Kaynak Sunucu, srcsrv.dll adlı bir DLL dosyası ile çalışır. Kaynak Sunucu, kaynak kodu depodan almak için kullanılan komutların yanı sıra kaynak kodu deposuna işaretçiler içeren uygulamanın .pdb dosyasını okur. devenv.exe ve srcsrv.dll ile aynı dizine konması gereken srcsrv.ini adlı dosyadaki izin verilen komutları listeleyerek hangi komutlara uygulamanın .pdb dosyasından yürütülmesini izin verileceğini sınırlayabilirsiniz.  
  
> [!IMPORTANT]
>  Rastgele komutlar uygulamanın .pdb dosyasına katıştırılabildiğinden yalnızca yürütmek istediğiniz komutları srcsrv.ini dosyasına koyduğunuzdan emin olun. srcsvr.ini dosyasında olmayan bir komutu yürütme girişimi, bir onay iletişim kutusunun görüntülenmesine neden olur. Daha fazla bilgi için bkz: [güvenlik uyarısı: hata ayıklayıcı gerekir yürütme güvenilmeyen komut](../debugger/security-warning-debugger-must-execute-untrusted-command.md). Komut parametrelerinde bir doğrulama yapılmadı, bu nedenle güvenilir komutlara dikkat edin. Örneğin, cmd.exe'ye güvendiyseniz, kötü niyetli bir kullanıcı, komutu tehlikeli duruma getirecek parametreler belirtebilir.  
  
 **Kaynak sunucu kullanımını etkinleştirmek için**  
  
1.  Önceki bölümde açıklanan güvenlik önlemleri ile derlediğinizden emin olun.  
  
2.  Üzerinde **Araçları** menüsünde seçin **seçenekleri**.  
  
     **Seçenekleri** iletişim kutusu görüntülenir.  
  
3.  İçinde **hata ayıklama** düğümü seçin **genel**.  
  
4.  Seçin **etkinleştirmek kaynak sunucu desteği** onay kutusu.  
  
     ![Kaynak sunucu seçenekleri etkinleştirmek](../debugger/media/dbg_options_general_enablesrcsrvr_checkbox.png "DBG_Options_General_EnableSrcSrvr_checkbox")  
  
5.  (İsteğe bağlı) İstediğiniz alt seçeneği belirleyin.  
  
     Unutmayın her ikisi de **izin kaynak sunucu için kısmi güven derlemeler (sadece yönetilen)** ve **sormadan güvenilmeyen kaynak sunucu komutları çalıştırmak her zaman** yukarıda açıklanan güvenlik riskleri artırabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[Simge dosyaları ve Visual Studio simge ayarlarını anlama](https://blogs.msdn.microsoft.com/visualstudioalm/2015/01/05/understanding-symbol-files-and-visual-studios-symbol-settings/)

[Visual Studio 2012 ve 2013 değişiklikler yüklerken .NET uzaktan simgesi](http://blogs.msdn.com/b/visualstudioalm/archive/2013/10/16/net-remote-symbol-loading-changes-in-visual-studio-2012-and-2013.aspx)