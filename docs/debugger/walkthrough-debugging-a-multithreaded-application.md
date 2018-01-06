---
title: "İş parçacığı Hata Ayıklayıcısı'ndaki görüntülemek | Microsoft Docs"
ms.custom: 
ms.date: 04/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.threads
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
caps.latest.revision: "44"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: bde9f1c8aa09f8e5961bd228a5f1947c2fc30f82
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="view-threads-in-the-debugger-in-visual-studio-using-the-threads-window"></a>İş parçacıkları penceresini kullanarak Visual Studio hata ayıklayıcısında görünüm iş parçacıkları
İçinde **iş parçacığı** penceresinde inceleyin ve hata ayıklama yaptığınız uygulama iş parçacığı ile çalışırsınız. Nasıl kullanılacağını hakkında adım adım yönergeler için **iş parçacığı** penceresinde bkz [izlenecek yol: iş parçacıkları penceresini kullanarak hata ayıklama](../debugger/how-to-use-the-threads-window.md).
  
 **İş parçacığı** penceresi, her satır bir iş parçacığı, uygulamanızda temsil ettiği bir tablo içerir. Varsayılan olarak, uygulamanızdaki tüm iş parçacıklarının tablo listeler, ancak sizi ilgilendiren iş parçacığı göstermek için listedeki filtreleyebilirsiniz. Her sütun farklı türde bilgi içerir. Ayrıca, bazı sütunları gizleyebilirsiniz. Tüm sütunları görüntülemek, aşağıdaki bilgileri, soldan sağa görünür:  
  
-   Burada, özellikle dikkat istediğiniz bir iş parçacığı işaretleyebilirsiniz bayrağı sütun. Bir iş parçacığı bayrak hakkında daha fazla bilgi için bkz: [nasıl yapılır: bayrağı ve iş parçacıklarını bayrakla](../debugger/how-to-flag-and-unflag-threads.md).  
  
-   Sarı bir ok (ok anahat geçerli olmayan bir iş parçacığı için geçerli hata ayıklayıcı bağlamını gösterir) geçerli iş parçacığının gösterir geçerli iş parçacığı sütununun.
  
-   **Kimliği** her iş parçacığı kimliği numarasını içeren sütun.  
  
-   **Yönetilen kimliği** yönetilen iş parçacığı için yönetilen kimliği sayıları içeren sütun.  
  
-   **Kategori** iş parçacığı kullanıcı arabirimi iş parçacıkları, uzak yordam çağrısı işleyicileri ya da çalışan iş parçacığı kategorilere ayıran sütun. Özel bir kategori uygulamanın ana iş parçacığı tanımlar.  
  
-   **Adı** varsa veya olarak ada göre her iş parçacığı tanımlayan sütun \<No Name >.  
  
-   **Konumu** sütun, iş parçacığı çalıştığı hangi gösterir. İş parçacığı için tam çağrı yığını göstermek için bu konuma genişletebilirsiniz.  
  
-   **Öncelik** öncelik veya sistem için her bir iş parçacığı atanan öncelik içeren sütun.  
  
-   **Benzeşim maskesi** (genellikle gizli) gelişmiş bir sütunu olan sütun. Bu sütun her iş parçacığı için İşlemci benzeşim maskesi gösterir. İşlemcili bir sistemde, bir iş parçacığı çalıştırılabileceği hangi İşlemci benzeşim maskesi belirler.  
  
-   **Askıya sayısı** askıya alınmış sayısı içerir ve genellikle gizli (genellikle gizli), bir sütun. Bu sayaç, bir iş parçacığı çalıştırılıp çalıştırılamayacağını belirler. Askıya alınan sayısı açıklaması için "Dondurma ve çözme iş parçacığı sayısı" bölümüne bakın.  
  
-   **İşlem adı** (genellikle gizli), her iş parçacığı ait olduğu için işlem içeren sütun. Bu sütun, birden çok işlem ayıklarken yararlı olabilir.  
  
### <a name="to-display-the-threads-window-in-break-mode-or-run-mode"></a>Kesme modunda veya çalışma modunda iş parçacıkları penceresini görüntülemek için  
  
-   Hata ayıklama sırasında seçin **hata ayıklama** menüsündeki **Windows**ve ardından **iş parçacığı**.  
  
### <a name="to-display-or-hide-a-column"></a>Görüntülemek veya bir sütun gizlemek için  
  
-   En üstündeki araç çubuğunda **iş parçacığı** penceresinde, tıklatın **sütunları**, ardından seçin veya göstermek veya gizlemek istediğiniz sütunun adını temizleyin.    

## <a name="display-flagged-threads"></a>Bayrak eklenmiş iş parçacığı görüntüleme  
 Bir simge ile işaretleyerek özel dikkat vermek istediğiniz bir iş parçacığı bayrak **iş parçacığı** penceresi. Daha fazla bilgi için bkz: [nasıl yapılır: bayrağı ve iş parçacıklarını bayrakla](../debugger/how-to-flag-and-unflag-threads.md). İçinde **iş parçacığı** penceresi tüm iş parçacıkları veya yalnızca bayraklı iş parçacığı görüntülemek için seçin.  
  
#### <a name="to-display-only-flagged-threads"></a>Yalnızca görüntülemek için iş parçacıklarını bayrakla  
  
-   Seçin **yalnızca iş parçacıklarını bayrakla Göster** en üstündeki düğmesi **iş parçacığı** penceresi. (Bunu görünüyorsa, bazı iş parçacıkları ilk bayrak gerekir.) 

## <a name="freeze-and-thaw-threads"></a>Dondurma ve çözme iş parçacıkları  
 Bir iş parçacığı dondurmak, kaynaklar kullanılabilir olsa bile sistem yürütme iş parçacığının başlatılmaz.  
  
 Yerel kodda askıya alma veya Windows işlevleri çağırarak iş parçacıklarını sürdürme `SuspendThread` ve `ResumeThread` veya MFC işlevleri [CWinThread::SuspendThread](/cpp/mfc/reference/CWinThread-class.md#cwinthread__suspendthread) ve [CWinThread::ResumeThread](/cpp/mfc/reference/CWinThread-class.md#cwinthread__resumethread). Çağırırsanız `SuspendThread` veya `ResumeThread`, değiştirdiğiniz *askıya sayısı*, göründüğü içinde **iş parçacığı** penceresi. Ancak, donmasına veya yerel bir iş parçacığı çözme, askıya alınmış sayısı değiştirmeyin. Çözülmüş ve askıya alınmış sayısı sıfır sahip sürece yerel kodda iş parçacığı yürütülemiyor.  
  
 Yönetilen kodda dondurma ya da bir iş parçacığı çözme askıya alınmış sayısı değişmez. Yönetilen kodda askıya alınmış sayısını 1 dondurulmuş bir iş parçacığı vardır. Yerel kodda iş parçacığı tarafından askıya sürece askıya alınmış sayısı 0 dondurulmuş bir iş parçacığı sahip bir `SuspendThread` çağırın.  
  
> [!NOTE]
>  Yerel koddan yönetilen koda çağrısı hata ayıklamasını yaparken, yönetilen kod adlı yerel kod olarak aynı fiziksel iş parçacığı çalıştırır. Yönetilen kod ayrıca askıya alma veya yerel iş parçacığı dondurma donuyor.  
  
#### <a name="to-freeze-or-thaw-execution-of-a-thread"></a>Freeze veya bir iş parçacığı yürütülmesi çözme  
  
-   Üstündeki araç çubuğunda **iş parçacığı** penceresinde tıklatın **iş parçacıklarını dondurmak** veya **çözme iş parçacığı**.  
  
     Bu eylem, seçili iş parçacığı etkiler **iş parçacığı** penceresi. 

### <a name="switch-to-another-thread"></a>Başka bir iş parçacığı için geçiş 

Sarı bir ok geçerli iş parçacığının (ve yürütme işaretçi konumunu) gösterir. Süslü kuyruklu yeşil bir ok geçerli hata ayıklayıcı bağlamını geçerli olmayan bir iş parçacığı olduğunu gösterir.

#### <a name="to-switch-to-another-thread"></a>Başka bir iş parçacığı için geçiş yapmak için  
  
-   Aşağıdaki adımlardan birini gerçekleştirin:  
  
    -   Hiçbir iş parçacığı çift tıklayın.  
  
    -   Bir iş parçacığı sağ tıklatın ve **geçiş iş parçacığına**.

## <a name="group-and-sort-threads"></a>Grup ve sıralama iş parçacıkları  
 İş parçacığı gruplandırdığınızda, tablodaki her grup için bir başlığı görüntülenir. Başlık "Çalışan iş parçacığı" veya "Bayrak yok iş parçacığı sayısı" ve ağaç denetimi gibi Grup açıklamasını içerir. Her grup üyesi iş parçacıklarının grup başlığı altında görünür. Bir grup için üye iş parçacıklarını gizlemek istiyorsanız, Grup daraltmak için ağaç denetimi kullanabilirsiniz.  
  
 Gruplandırma sıralama üzerinden öncelikli olduğundan, kategoriye, örneğin, iş parçacıkları grup ve ardından her kategoride Kimliğine göre sıralayın.  
  
#### <a name="to-sort-threads"></a>İş parçacığı sıralamak için  
  
1.  Üstündeki araç çubuğunda **iş parçacığı** penceresinde herhangi bir sütun üst düğmesini tıklatın.  
  
     İş parçacığı, artık bu sütundaki değerlere göre sıralanır.  
  
2.  Sıralama düzenini tersine istiyorsanız, tekrar aynı düğmeye tıklayın.  
  
     Listenin başında şimdi görünen iş parçacığı altta görünür.  
  
#### <a name="to-group-threads"></a>Grup iş parçacığı  
  
-   İçinde **iş parçacığı** penceresi araç tıklatın **Group by** listelemek ve Grup iş parçacığı tarafından istediğiniz ölçütü'i tıklatın.  
  
#### <a name="to-sort-threads-within-groups"></a>İş parçacığı grupları içindeki sıralamak için  
  
1.  En üstündeki araç çubuğunda **iş parçacığı** penceresinde tıklatın **Group by** listelemek ve Grup iş parçacığı tarafından istediğiniz ölçütü'i tıklatın.  
  
2.  İçinde **iş parçacığı** penceresinde herhangi bir sütun üst düğmesini tıklatın.  
  
     İş parçacığı, artık bu sütundaki değerlere göre sıralanır.  
  
#### <a name="to-expand-or-collapse-all-groups"></a>Genişlet veya daralt tüm gruplar için  
  
-   Üstündeki araç çubuğunda **iş parçacığı** penceresinde tıklatın **Grupları Genişlet** veya **grupları Daralt**.  
  
## <a name="search-for-specific-threads"></a>Belirli iş parçacığı arama  
 İçinde [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], belirtilen bir dizeyle Eşleştir iş parçacığı arama yapabilirsiniz. İş parçacıkları için arama yaptığınızda **iş parçacığı** penceresini penceresi herhangi sütununda arama dizesiyle eşleşen tüm iş parçacıklarının görüntüler. Çağrı yığınında üstündeki görüntülenen iş parçacığı konum bilgilerdir **konumu** sütun. Varsayılan olarak, ancak, tam çağrı yığını aranmaz.  
  
#### <a name="to-search-for-specific-threads"></a>Belirli iş parçacığı arama  
  
-   Üstündeki araç çubuğunda **iş parçacığı** penceresinde, Git **arama** kutusu ve ya da:  
  
    -   Bir arama dizesi yazın ve ENTER tuşuna basın.  
  
         \-veya -  
  
    -   Aşağı açılan listeye tıklayın **arama** kutusunda ve bir arama dizesi önceki aramadan seçin.  
  
-   (İsteğe bağlı) Tam çağrı yığını aramanızda eklemek için seçin **arama çağrı yığını**.   
  
## <a name="display-thread-call-stacks-and-switching-between-frames"></a>Görüntü iş parçacığının çağrı yığınları ve çerçeveler arasında geçiş yapma  
Birden çok iş parçacıklı bir programda kendi çağrı yığını her iş parçacığı vardır. **İş parçacığı** penceresi bu yığınları görüntülemek için kolay bir yol sağlar.

> [!TIP]
> Her iş parçacığı için çağrı yığını görsel için kullanmak [Paralel Yığınlar](../debugger/get-started-debugging-multithreaded-apps.md) penceresi.
  
#### <a name="to-view-the-call-stack-of-a-thread"></a>Bir iş parçacığı çağrı yığınını görüntülemek için  
  
-   İçinde **konumu** sütun, iş parçacığı konumun yanındaki ters üçgen'ı tıklatın.  
  
     İş parçacığı için çağrı yığını göstermek için konum genişletir.  
  
#### <a name="to-view-or-collapse-the-call-stacks-of-all-threads"></a>Görüntülemek veya tüm iş parçacıklarının çağrı yığınları daraltmak için  
  
-   Üstündeki araç çubuğunda **iş parçacığı** penceresinde tıklatın **çağrı yığınları genişletin** veya **Daralt çağrı yığınları**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birden çok iş parçacıklı uygulamalarda hata ayıklama](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Çok iş parçacıklı uygulamada hata ayıklama kullanmaya başlama](../debugger/get-started-debugging-multithreaded-apps.md)