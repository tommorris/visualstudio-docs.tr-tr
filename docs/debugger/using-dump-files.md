---
title: "Döküm dosyalarını kullanma | Microsoft Docs"
ms.custom: H1HackMay2017
ms.date: 03/08/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.crashdump
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- dumps, about dumps
- crash dumps
- dump files
- dumps
ms.assetid: b71be6dc-57e0-4730-99d2-b540a0863e49
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 179d66b80676cf47bb12e82fcd8e4ac00503a492
ms.sourcegitcommit: 5d43e9590e2246084670b79269cc9d99124bb3df
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="use-dump-files-with-visual-studio"></a>Visual Studio ile döküm dosyalarını kullanma
Döküm dosyaları ile veya olmadan yığınlara; bir döküm dosyası oluşturun; döküm dosyası açın; ikili dosyaları, pdb'ın ve bir döküm dosyası için kaynak dosyası bulun.
  
##  <a name="BKMK_What_is_a_dump_file_"></a>Döküm dosyası nedir?  
 A *döküm dosyası* dökümü alınır zaman içinde bir uygulamanın bir noktada bir anlık görüntüdür. Hangi işlemin yürütülmüş, hangi modüllerin de yüklenmiş olduğunu gösterir. Döküm, yığın bilgileriyle kaydedildiyse, döküm dosyası, zaman içinde o anda uygulamanın belleğinde olanların bir anlık görüntüsünü içerir. Döküm dosyasını Visual Studio'da bir yığın ile açmak, bir hata ayıklama oturumunda kesme noktasında durdurmak gibidir. Yürütme devam edemiyor olsanız da, döküm oluştuğu anda uygulamanın yığınlarını, iş parçacıklarını ve değişken değerlerini inceleyebilirsiniz.  
  
 Dökümleri öncelikle Geliştirici erişimi yok makinelerde oluşan sorunlar hata ayıklama için kullanılır. Örneğin, Müşteri'nin kilitlenme yeniden oluşturun veya makinenizde askıda Müşteri'nin makineden bir döküm dosyası kullanabilirsiniz. Daha fazla test için test makinesinin kullanılabilmesi amacıyla çökmeyi veya takılma verilerini kaydetmek üzere testçiler tarafından da dökümler oluşturulur. Visual Studio hata ayıklayıcı, yönetilen veya yerel kod için döküm dosyaları kaydedebilir. Hata ayıklayıcı dosyalarının kaydedileceği diğer programları veya Visual Studio tarafından oluşturulan döküm dosyalarını yükleyebilir *mini döküm* biçimi.  
  
##  <a name="BKMK_Dump_files__with_or_without_heaps"></a>Döküm dosyaları, ile veya olmadan yığınları  
 Yığın bilgileri içeren veya içermeyen döküm dosyaları oluşturabilirsiniz.  
  
-   **Döküm dosyaları yığın ile** uygulamanın belleğin anlık görüntüsünü içerir. Bu döküm oluşturulduğundaki değişkenlerin değerlerini içerir. Yığınla kaydedilmiş bir döküm dosyası yüklerseniz, uygulama ikili dosyası bulunamasa bile Visual Studio sembolleri yükleyebilir. Visual Studio ayrıca döküm dosyasında yüklenen yerel modüllerin ikili dosyalarını kaydederek hata ayıklamayı daha da kolaylaştırır.  
  
-   **Döküm dosyaları yığınlara olmadan** yığın bilgilerle dökümleri daha küçüktür. Ancak hata ayıklayıcısının sembol bilgilerini bulmak için uygulama ikili dosyalarını yüklemesi gerekir. İkili dosyalar, döküm oluşturulduğunda kullanılan ikili dosyalarla tam olarak eşleşen ikili dosyalar olmalıdır. Sadece yığın değişkenlerin değerleri öbek veri olmadan döküm dosyalarına kaydedilir.  
  
##  <a name="BKMK_Requirements_and_limitations"></a>Gereksinimler ve sınırlamalar  
  
-   En iyi duruma getirilmiş kodun döküm dosyalarının hatalarının ayıklanması kafa karıştırıcı olabilir. Örneğin, işlevlerin derleyici içerilmesi, beklenmeyen çağrı yığınlarıyla sonuçlanabilir ve diğer iyileştirmeler, değişkenlerin ömrünü değiştirebilir.  
  
-   64 bit bilgisayarda çalışan bir Visual Studio örneğinde 64 bit makinelerdeki döküm dosyalarının hataları ayıklanmalıdır.  
  
-   Visual Studio'nun VS 2013 öncesi sürümlerinde, 64 bit makinelerde çalıştırılan 32 bit uygulamaların bazı araçlar tarafından toplanan (Görev Yöneticisi ve 64-bit WinDbg) dökümleri Visual Studio'da açılamadı. Bu sınırlama, VS 2013 sürümünde kaldırılmıştır.  
  
-   Visual Studio, ARM cihazlarından yerel uygulamaların döküm dosyalarının hatalarını ayıklayabilir. Visual Studio, ARM cihazlarındaki yönetilen uygulamaların uygulama döküm dosyalarının da hatalarını ayıklayabilir, ancak bunu yalnızca yerel hata ayıklayıcıda yapabilir.  
  
-   Hata ayıklama için [çekirdek modu](http://msdn.microsoft.com/library/windows/hardware/ff551880.aspx) döküm dosyaları, parçası olan Windows için hata ayıklama araçlarını yükleme [Windows Sürücü Seti (WDK)](/windows/hardware/windows-driver-kit). 
  
-   Visual Studio olamaz hata ayıklama döküm dosyalarını olarak bilinen eski döküm biçiminde kaydedilmiş bir [tam kullanıcı modu dökümü](http://msdn.microsoft.com/library/windows/hardware/ff545506.aspx). Tam kullanıcı modu dökümünün yığını olan bir dökümle aynı olmadığına dikkat edin.  
  
-   İle hata ayıklamak için [SOS.dll (SOS hata ayıklama uzantısı)](/dotnet/framework/tools/sos-dll-sos-debugging-extension) Visual Studio'da parçası olan Windows için hata ayıklama araçları yüklemeniz gerekir [Windows Sürücü Seti (WDK)](/windows/hardware/windows-driver-kit) 
  
##  <a name="BKMK_Create_a_dump_file"></a>Döküm dosyası oluşturma  
 Visual Studio ile bir döküm dosyası oluşturmak için:  
  
-   Visual Studio'daki bir işlemde hata ayıklarken, hata ayıklayıcı kesme noktası veya bir özel durumda durduğunda döküm dosyasını kaydedebilirsiniz. Seçin **hata ayıklama**, ardından **dökümü olarak Kaydet**, ardından **hata ayıklama**. İçinde **Dökümü Kaydet** iletişim kutusunda **farklı türde Kaydet** listesinden seçebilirsiniz **mini döküm** veya **mini döküm yığın ile** (varsayılan).  
  
-   İle [Just-In-Time hata ayıklama](../debugger/just-in-time-debugging-in-visual-studio.md) etkin hata ayıklayıcı dışında çalışan çöken bir işlem hata ayıklayıcı ekleme ve kullanabilirsiniz döküm dosyasını kaydedin. Bkz: [çalıştırma işlemine iliştirme](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)  
  
 Windows mini döküm biçimini destekleyen herhangi bir programla da döküm dosyaları oluşturabilirsiniz. Örneğin, **Procdump** 'ten komut satırı yardımcı programını [Windows SysInternals](http://technet.microsoft.com/sysinternals/default) Tetikleyicileri veya isteğe bağlı işlem kilitlenme bilgi döküm dosyaları oluşturabilirsiniz. Bkz: [gereksinimler ve sınırlamalar](../debugger/using-dump-files.md#BKMK_Requirements_and_limitations) döküm dosyaları oluşturmak için diğer araçları kullanarak hakkında ek bilgi için bu konudaki. 
  
##  <a name="BKMK_Open_a_dump_file"></a>Döküm dosyasını açın  
  
1.  Visual Studio'da, **dosya**, **açık**, **dosya**.  
  
2.  İçinde **Dosya Aç** iletişim kutusunda, döküm dosyasını bulup seçin. Çoğunlukla .dmp uzantısına sahip olacaktır. Ardından **Tamam**.  
  
3.  **Döküm dosyası özeti** penceresi görüntülenir. Bu pencerede, döküm dosyasının hata ayıklama özet bilgilerini görüntüleyebilir, sembol yolunu ayarlayabilir, hata ayıklamayı başlatabilir ve özet bilgilerini panoya kopyalayabilirsiniz.  
  
     ![Mini döküm Özet sayfasında](../debugger/media/dbg_dump_summarypage.png "DBG_DUMP_SummaryPage")  
  
4.  Hata ayıklamayı başlatmak için Git **Eylemler** bölümünde ve seçin **yalnızca yönetilen ile hata ayıklama**, **yerel yalnızca ile hata ayıklama** veya **karmailehataayıklama**.  
  
##  <a name="BKMK_Find_binaries__symbol___pdb__files__and_source_files"></a>İkili dosyaları, simge (.pdb) dosyaları ve kaynak dosyaları bulma  
 Bir döküm dosyasında hata ayıklamak üzere Visual Studio'nun tam özelliklerini kullanmak aşağıdakilere erişim gerekir:  
  
-   Dökümün alındığı .Exe dosyası ve döküm işleminde kullanılan diğer ikili dosyalar (DLL'ler vb.).  
  
     Yığın veriler ile bir dökümün hatalarını ayıklıyorsanız, Visual Studio bazı modüller için eksik ikili dosyalarla başa çıkabilir, ancak geçerli çağrı yığınları oluşturmak için yeterli modüller için ikili dosyalara sahip olmalıdır. Visual Studio, yığın ile döküm dosyasında yerel modüller içerir.  
  
-   .exe ve diğer ikili dosyalar için sembol (.pdb) dosyaları.  
  
-   İlgilendiğiniz modüller için kaynak dosyaları.  
  
     Yürütülebilir ve .pdb dosyaları, döküm oluşturulduğunda kullanılan dosyaların sürüm ve yapısıyla tam olarak eşleşmelidir.  
  
     Kaynak dosyaları bulamazsa modülleri ayrıştırılmış kullanarak ayıklayabilirsiniz,  
  
 **Yürütülebilir dosyalar için varsayılan arama yolları**  
  
 Visual Studio bu konumları döküm dosyasında yer almayan yürütülebilir dosyalar için otomatik olarak arar:  
  
1.  Döküm dosyasını içeren dizin.  
  
2.  Döküm dosyasında belirtilen modül yolu. Bu, makinede dökümün toplandığı modül yoludur.  
  
3.  Belirtilen simge yolları **hata ayıklama**, **seçenekleri**, **simgeleri** Visual Studio sayfasının **Araçları**, **seçenekleri**  iletişim kutusu. Bu sayfada arama yapmak için daha fazla konum ekleyebilirsiniz.  
  
 **Hayır ikili kullanarak > Sembol > kaynak sayfaları**  
  
 Visual Studio döküm modülünde hata ayıklamak için gerekli dosyaları bulamazsanız, uygun bir sayfa görüntülenir (**Hayır ikili bulundu**, **Hayır simgeleri bulunan**, veya **Hayır kaynak bulunamadı**). Bu sayfalar, sorunun nedeni hakkında ayrıntılı bilgi sağlar ve dosyaların doğru konumunu belirlememenize yardımcı olabilecek eylem bağlantıları sağlar. Bkz: [simge (.pdb) belirtin ve kaynak dosyaları](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tam zamanında hata ayıklama](../debugger/just-in-time-debugging-in-visual-studio.md)   
 [Simge (.pdb) belirtin ve kaynak dosyaları](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [IntelliTrace](../debugger/intellitrace.md)