---
title: İş parçacığı hata ayıklayıcıda görüntüleme | Microsoft Docs
ms.custom: ''
ms.date: 04/25/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.threads
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- threading [Visual Studio], debugging
- Thread.Name property
- debugger, Threads window
- SetThreadName function
- Threads window
- '@TIB'
- debugging [Visual Studio], threads
ms.assetid: 590ffd57-0556-43d8-8962-ee27e5b2b7d7
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b464213f6443ecbdf07c225fc3698697e91b5c11
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2018
ms.locfileid: "35677737"
---
# <a name="view-threads-in-the-debugger-in-visual-studio-using-the-threads-window"></a>Visual Studio'da iş parçacıkları penceresini kullanarak hata ayıklayıcı iş parçacıkları görünümü
İçinde **iş parçacıkları** penceresini inceleyin ve uygulamada hata ayıklaması yaptığınız iş parçacıkları ile çalışır. Nasıl kullanılacağını adım adım yönergeler için **iş parçacıkları** penceresinde görmek [izlenecek yol: iş parçacıkları penceresini kullanarak hata ayıklama](../debugger/how-to-use-the-threads-window.md).
  
 **İş parçacıkları** penceresi, her satır bir iş parçacığında uygulamanızı temsil ettiği bir tablo içerir. Varsayılan olarak, uygulamanızı tüm iş parçacıklarının tabloda listelenir, ancak yalnızca sizi ilgilendiren iş parçacıklarını gösterilecek listeyi filtreleyebilirsiniz. Her sütun, farklı türde bilgi içerir. Ayrıca, bazı sütunları gizleyebilirsiniz. Tüm sütunları görüntülemek, aşağıdaki bilgileri, soldan sağa doğru görünür:  
  
-   Burada, özen istediğiniz bir iş parçacığını işaretleyebileyeceğiniz Bayrak sütunu. Bir iş parçacığı bayrak hakkında daha fazla bilgi için bkz: [nasıl yapılır: bayrağı ve iş parçacıklarını bayrakla](../debugger/how-to-flag-and-unflag-threads.md).  
  
-   Sarı bir ok (ok anahat geçerli olmayan bir iş parçacığı için geçerli hata ayıklayıcı bağlamını gösterir) geçerli iş parçacığı gösterir geçerli iş parçacığı sütunu.
  
-   **Kimliği** her iş parçacığı kimlik numarasını içeren sütun.  
  
-   **Yönetilen kimliği** yönetilen iş parçacıkları için yönetilen kimlik sayıları içeren sütun.  
  
-   **Kategori** sütunu kullanıcı arabirimi iş parçacıkları, uzak yordam çağrı işleyicisi veya çalışan iş parçacıkları iş parçacıkları kategorilere ayırır. Uygulamanın ana iş parçacığı bir özel kategori tanımlar.  
  
-   **Adı** varsa veya olarak ada göre her bir iş parçacığı tanımlayan sütun \<No Name >.  
  
-   **Konumu** sütun, iş parçacığı çalıştığı hangi gösterir. Bu konum iş parçacığı için tam çağrı yığınını Göster genişletebilirsiniz.  
  
-   **Öncelik** öncelik ya da sistem her iş parçacığı için atanan öncelik içeren sütun.  
  
-   **Benzeşim maskesi** (genellikle gizli) gelişmiş bir sütunu olan sütun. Her iş parçacığı için İşlemci benzeşim maskesi bu sütunda görüntülenir. Çok işlemcili bir sistemde, bir iş parçacığı üzerinde çalışabileceği hangi İşlemci benzeşim maskesi belirler.  
  
-   **Askıya sayısı** askıda sayma içerir ve genellikle gizli (genellikle gizli), sütun. Bu sayaç, bir iş parçacığı çalıştırılıp çalıştırılamayacağını belirler. Askıda sayma açıklaması için "Dondurma ve çözme iş parçacığı sayısı" bölümüne bakın.  
  
-   **İşlem adı** (genellikle gizli), her iş parçacığı ait olduğu için işlem içeren sütun. Bu sütun, birden çok işlem ayıklarken yararlı olabilir.  
  
### <a name="to-display-the-threads-window-in-break-mode-or-run-mode"></a>İş parçacıkları penceresini kesme modunda veya çalıştırma modunda görüntülemek için  
  
-   Hata ayıklama sırasında seçin **hata ayıklama** menüsünde **Windows**ve ardından **iş parçacıkları**.  
  
### <a name="to-display-or-hide-a-column"></a>Bir sütunu sakla ya da görüntülemek için  
  
-   Üst kısmındaki araç çubuğunda **iş parçacıkları** penceresinde tıklayın **sütunları**sonra seçin veya temizleyin, göstermek veya gizlemek istediğiniz sütun adı.    

## <a name="display-flagged-threads"></a>Bayraklı iş parçacıklarını görüntüleme  
 Bir simge ile işaretleyerek özel dikkat vermek istediğiniz bir iş parçacığı işaretleyebilirsiniz **iş parçacıkları** penceresi. Daha fazla bilgi için [nasıl yapılır: bayrağı ve iş parçacıklarını bayrakla](../debugger/how-to-flag-and-unflag-threads.md). İçinde **iş parçacıkları** penceresi tüm iş parçacıkları veya yalnızca bayraklı iş parçacıklarını görüntülemeyi seçebilirsiniz.  
  
#### <a name="to-display-only-flagged-threads"></a>Yalnızca bayraklı iş parçacıklarını görüntülemek için  
  
-   Seçin **sadece iş parçacığı bayrak eklenmiş Göster** üst kısmındaki düğmeye **iş parçacıkları** penceresi. (Soluksa, bazı iş parçacıkları ilk bayrak için ihtiyacınız.) 

## <a name="freeze-and-thaw-threads"></a>Dondurma ve iş parçacıklarını çözme  
 Bir iş parçacığını Dondur, sistem kaynakları kullanılabilir olsa bile, iş parçacığının yürütülmesini başlatılmaz.  
  
 Yerel kodda askıya alma veya Windows işlevleri çağırarak iş parçacıklarını sürdürme `SuspendThread` ve `ResumeThread` veya MFC işlevleri [CWinThread::SuspendThread](/cpp/mfc/reference/CWinThread-class#suspendthread) ve [CWinThread::ResumeThread](/cpp/mfc/reference/CWinThread-class#resumethread). Çağırırsanız `SuspendThread` veya `ResumeThread`, değiştirdiğiniz *askıya sayısı*, içinde göründüğü **iş parçacıkları** penceresi. Ancak, dondurma veya çözme yerel bir iş parçacığı, askıda sayma değiştirmeyin. Çözülmüş ve askıya alınmış sayısı sıfır olan sürece yerel kodda iş parçacığı yürütülemiyor.  
  
 Yönetilen kodda dondurma veya çözme iş parçacığı askıda sayma değiştirin. Yönetilen kodda dondurulmuş bir iş parçacığı askıda sayısı 1 ' var. Yerel kodda iş parçacığı tarafından askıya alındı sürece askıya alınmış sayısı 0 dondurulmuş bir iş parçacığı sahip bir `SuspendThread` çağırın.  
  
> [!NOTE]
>  Yönetilen koda yerel koddan bir çağrı hata ayıklaması yaparken, yönetilen kod aynı fiziksel iş parçacığında adlı yerel kod olarak çalışır. Yönetilen kod da askıya alma ya da yerel iş parçacığını dondurma donuyor.  
  
#### <a name="to-freeze-or-thaw-execution-of-a-thread"></a>Dondurma veya çözme iş parçacığı yürütme için  
  
-   Üst kısmındaki araç çubuğunda **iş parçacıkları** penceresinde tıklayın **iş parçacıklarını dondurma** veya **çözme iş parçacığı**.  
  
     Bu eylem, seçili iş parçacıklarını etkiler **iş parçacıkları** penceresi. 

### <a name="switch-to-another-thread"></a>Başka bir iş parçacığına geçiş 

Sarı bir ok, geçerli iş parçacığı (ve yürütme işaretçisi konumunu) gösterir. Kıvrık kuyruklu yeşil bir ok, geçerli hata ayıklayıcı bağlamı geçerli olmayan bir iş parçacığı olduğunu gösterir.

#### <a name="to-switch-to-another-thread"></a>Başka bir iş parçacığına geçiş yapmak için  
  
-   Aşağıdaki adımlardan birini gerçekleştirin:  
  
    -   Herhangi bir iş parçacığı çift tıklayın.  
  
    -   Bir iş parçacığı sağ tıklatıp **iş parçacığına geçiş**.

## <a name="group-and-sort-threads"></a>Grup ve sıralama iş parçacıkları  
 İş parçacıkları gruplandırdığınızda, tablodaki her grup için bir başlık görünür. Başlığı "Çalışan iş parçacığı" veya "Bayrak yok iş parçacığı sayısı" ve ağaç denetimi gibi bir Grup açıklaması içerir. Her grup üyesi iş parçacıklarının grubunun başlığının altında görünür. Bir grubun üyesi iş parçacıklarının gizlemek istiyorsanız, grubu daraltmak için ağaç denetimi kullanabilirsiniz.  
  
 Gruplandırma sıralama üzerinden öncelikli olduğundan, kategoriye, örneğin, iş parçacığı grubu ve alanlarını her kategoride Kimliğine göre sıralayabilirsiniz.  
  
#### <a name="to-sort-threads"></a>İş parçacıkları sıralamak için  
  
1.  Üst kısmındaki araç çubuğunda **iş parçacıkları** penceresinde herhangi bir sütun üst kısmındaki düğmeye tıklayın.  
  
     İş parçacıkları, artık bu sütundaki değerlere göre sıralanır.  
  
2.  Sıralama düzenini tersine çevirmek istiyorsanız, aynı düğmesine tekrar tıklayın.  
  
     Artık listesinin üstünde görünen iş parçacıkları ve en altında görünür.  
  
#### <a name="to-group-threads"></a>İş parçacıklarını gruplandırma  
  
-   İçinde **iş parçacıkları** penceresi araç çubuğu, tıklayın **gruplandırma ölçütü** listelemek ve iş parçacıklarını gruplandırma istediğiniz ölçütleri'ı tıklatın.  
  
#### <a name="to-sort-threads-within-groups"></a>Grupları içindeki dizileri sıralama  
  
1.  Üst kısmındaki araç çubuğunda **iş parçacıkları** penceresinde tıklayın **gruplandırma ölçütü** listelemek ve iş parçacıklarını gruplandırma istediğiniz ölçütleri'ı tıklatın.  
  
2.  İçinde **iş parçacıkları** penceresinde herhangi bir sütun üst kısmındaki düğmeye tıklayın.  
  
     İş parçacıkları, artık bu sütundaki değerlere göre sıralanır.  
  
#### <a name="to-expand-or-collapse-all-groups"></a>Tüm grupları genişletin veya daraltın için  
  
-   Üst kısmındaki araç çubuğunda **iş parçacıkları** penceresinde tıklayın **Grupları Genişlet** veya **grupları Daralt**.  
  
## <a name="search-for-specific-threads"></a>Belirli bir iş parçacığı arama  
 İçinde [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], belirtilen bir dizenin eşleşen iş parçacığı için arama yapabilirsiniz. İş parçacıkları için arama yaptığınızda **iş parçacıkları** penceresinde herhangi bir sütunda arama dizesiyle eşleşen tüm iş parçacıkları pencere görüntüler. Çağrı yığınında üstünde görünen iş parçacığı konumu bilgilerdir **konumu** sütun. Varsayılan olarak, ancak tam çağrı yığınını aranmaz.  
  
#### <a name="to-search-for-specific-threads"></a>Belirli iş parçacığı arama  
  
-   Üst kısmındaki araç çubuğunda **iş parçacıkları** penceresinde, Git **arama** kutusu ve ya da:  
  
    -   Bir arama dizesi yazın ve ENTER tuşuna basın.  
  
         \- veya -  
  
    -   Aşağı açılan listeye tıklayın **arama** kutusunda ve bir önceki aramaya ait arama dizesini seçin.  
  
-   (İsteğe bağlı) Tam çağrı yığınını aramanızda eklemek için işaretleyin **arama çağrı yığını**.   
  
## <a name="display-thread-call-stacks-and-switching-between-frames"></a>Görüntü iş parçacığı çağrı yığınları ve çerçeveler arasında geçiş yapma  
Bir çoklu iş parçacığı kullanan programda her iş parçacığı kendi çağrı yığınına sahiptir. **İş parçacıkları** penceresi bu yığınlarını görüntülemek için kullanışlı bir yol sağlar.

> [!TIP]
> Her iş parçacığı için çağrı yığınını görsel bir temsilini için kullanmak [Paralel Yığınlar](../debugger/get-started-debugging-multithreaded-apps.md) penceresi.
  
#### <a name="to-view-the-call-stack-of-a-thread"></a>İş parçacığı çağrı yığınını görüntülemek için  
  
-   İçinde **konumu** sütun, iş parçacığı konumu yanındaki ters üçgene tıklayın.  
  
     İş parçacığı için çağrı yığınını Göster konumuna genişletir.  
  
#### <a name="to-view-or-collapse-the-call-stacks-of-all-threads"></a>Görüntüleme veya tüm iş parçacığı çağrı yığınlarını Daralt  
  
-   Üst kısmındaki araç çubuğunda **iş parçacıkları** penceresinde tıklayın **çağrı yığınlarını genişletme** veya **Daralt çağrı yığınlarını**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çok iş parçacıklı uygulamalarda hata ayıklama](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Çok iş parçacıklı bir uygulamanın hatalarını ayıklamaya başlama](../debugger/get-started-debugging-multithreaded-apps.md)