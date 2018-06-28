---
title: Görevleri penceresini kullanma | Microsoft Docs
ms.custom: ''
ms.date: 03/18/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.paralleltasks
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, parallel tasks window
ms.assetid: bd5e0612-a0dc-41cf-a7af-1e87d0d5c35f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d840f6c12de20fb613ee27d59395afeb15a5c34b
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37059362"
---
# <a name="using-the-tasks-window"></a>Görevleri Penceresini Kullanma

**Görevleri** pencere benzeyen **iş parçacığı** onun hakkında bilgileri gösterir dışında penceresi <xref:System.Threading.Tasks.Task?displayProperty=fullName>, [task_handle](/cpp/parallel/concrt/reference/task-group-class), veya [WinJS.Promise ](http://msdn.microsoft.com/library/windows/apps/br211867.aspx) yerine her iş parçacığı nesneleri. İş parçacığı gibi görevleri aynı anda çalışabilecek zaman uyumsuz işlemleri temsil eder; Ancak, birden fazla görev aynı iş parçacığı üzerinde çalışabilir.

Yönetilen kodda kullandığınız **görevleri** ile çalışırken penceresi <xref:System.Threading.Tasks.Task?displayProperty=fullName> nesneleri veya ile **await** ve **zaman uyumsuz** anahtar sözcükler (**bekleme** ve **zaman uyumsuz** Visualbasic'tir içinde). Yönetilen kod görevler hakkında daha fazla bilgi için bkz: [paralel programlama](/dotnet/standard/parallel-programming/index).

Yerel kodda kullandığınız **görevleri** ile çalışırken penceresi [görev grupları](/cpp/parallel/concrt/task-parallelism-concurrency-runtime), [paralel algoritmalar](/cpp/parallel/concrt/parallel-algorithms), [zaman uyumsuz aracılar](/cpp/parallel/concrt/asynchronous-agents), ve [Basit görevler](/cpp/parallel/concrt/task-scheduler-concurrency-runtime). Yerel kodda görevler hakkında daha fazla bilgi için bkz: [eşzamanlılık çalışma zamanı](/cpp/parallel/concrt/concurrency-runtime).

JavaScript'te, promise ile çalışırken görevleri penceresini kullanabilirsiniz `.then` kodu. Bkz: [JavaScript (UWP uygulamaları) içinde zaman uyumsuz programlama](http://msdn.microsoft.com/library/windows/apps/hh700330.aspx) daha fazla bilgi için.

Kullanabileceğiniz **görevleri** hata ayıklayıcısında araya girmektir zaman penceresi. Üzerinde erişim **hata ayıklama** menüsünde tıklayarak **Windows** ve ardından **görevleri**. Aşağıdaki çizimde gösterildiği **görevleri** kendi varsayılan modunda penceresi.

![Görevleri penceresini](../debugger/media/parallel_tasks_window.png "Parallel_Tasks_Window")

> [!NOTE]
> Yönetilen kodda bir <xref:System.Threading.Tasks.Task> durumu olan [TaskStatus.Created](<xref:System.Threading.Tasks.TaskStatus.Created>), [TaskStatus.WaitingForActivation](<xref:System.Threading.Tasks.TaskStatus.WaitingForActivation>), veya [TaskStatus.WaitingToRun](<xref:System.Threading.Tasks.TaskStatus.WaitingToRun>) olmayabilir Görüntülenen **görevleri** yönetilen iş parçacığı bir uyku ya da birleştirme durumda olduğunda penceresi.

## <a name="tasks-column-information"></a>Görevler sütun bilgileri

Sütunları **görevleri** penceresini aşağıdaki bilgileri görüntüleyin.

|Sütun adı|Açıklama|
|-----------------|-----------------|
|**bayrakları**|Hangi görevleri işaretlenmiş gösterir ve bayrak veya bir görev bayrakla olanak tanır.|
|**Simgeler**|Sarı bir ok geçerli görev gösterir. Geçerli görev geçerli iş parçacığı üzerinde en üstteki görevidir.<br /><br /> Beyaz ok sonu görevi, diğer bir deyişle, hata ayıklayıcı çağrıldığında geçerli bir belirtir.<br /><br /> Duraklatma simgesinin kullanıcı tarafından dondurulmuş bir görevi belirtir. Freeze ve listede sağ tıklayarak bir görev Çöz.|
|**ID**|Görev için sağlanan sistem numarası. Yerel kodda bu görevin adresidir.|
|**Status**|Geçerli durumunu (zamanlanmış, etkin, engellenmiş, kilitlenen, bekleniyor veya tamamlanmış) görev. Zamanlanmış bir görev henüz çalıştırılmadı ve bu nedenle, henüz bir çağrı yığını, atanan iş parçacığı veya ilgili bilgi yok biridir.<br /><br /> Etkin bir görevi kod hata ayıklayıcısı'ndaki kesmeden önce yürütülmekte olan biridir.<br /><br /> Bir bekleniyor veya engellenen bildirilmesini bir olay, bir kilidi serbest bırakılacak veya sonlandırmak için başka bir görev beklediğinden, engellenen bir görevdir.<br /><br /> Kilitlenen bir görev, iş parçacığı başka bir iş parçacığı ile karşılıklı bekleyen bir görevdir.<br /><br /> Üzerine gelerek **durum** hücre bloğu hakkında daha fazla bilgi kilitlenen veya bekleniyor bir görev için. **Uyarı:** **görevleri** penceresi bekleyin zinciri geçişi (WCT) tarafından desteklenen bir eşitleme temel kullanan bir engellenen görev için kilitlenme bildirir. Örneğin, bir kilitlenen <xref:System.Threading.Tasks.Task> WCT, hata ayıklayıcı raporları kullanan nesne **kanıt bekleniyor karşılıklı**. WCT kullanmaz, eşzamanlılık çalışma tarafından yönetilen kilitlenen bir görev için hata ayıklayıcı raporları **bekleyen**. WCT hakkında daha fazla bilgi için bkz: [bekleyin zinciri geçişi](http://msdn.microsoft.com/library/ms681622\(VS.85\).aspx).|
|**Başlangıç zamanı**|Hangi görev etkin hale geldiğini süre.|
|**Süre**|Görev etkin olmuştur saniye sayısı.|
|**Tamamlanma Zamanı**|Hangi görev tamamlandı süre.|
|**Konum**|Çağrı yığınında görevin geçerli konumu. Görev için tüm çağrı yığını görmek için bu hücreyi üzerine gelerek. Zamanlanmış Görevler bu sütunda bir değer yok.|
|**Görev**|İlk yöntem ve oluşturulduğunda bu göreve geçirilen herhangi bir bağımsız değişken.|
|**AsyncState**|Yönetilen kod için görev durumu. Varsayılan olarak, bu sütun gizlenir. Bu sütunu görüntülemek için bir sütun başlıklarının bağlam menüsünü açın. Seçin **sütunları**, **AsyncState**.|
|**Üst**|Bu görev oluşturulan görev kimliği. Bu boş ise, görev üst öğeye sahip. Bu yalnızca yönetilen programlar için geçerlidir.|
|**İş parçacığı atama**|Görevin çalıştığı iş parçacığı adını ve kimliği.|
|**AppDomain**|Yönetilen kod için görevi Yürütülüyor uygulama etki alanı.|
|**task_group**|Yerel kod, adresini için [task_group](/cpp/parallel/concrt/reference/task-group-class) zamanlanmış görev nesnesi. Zaman uyumsuz aracılar ve Basit görevler için bu sütun 0 olarak ayarlanır.|
|**İşlem**|Görevin çalıştığı işlem kimliği.|

 Bir sütun başlığını sağ tıklayıp ardından istediğiniz sütunları seçerek görünüme sütun ekleyebilirsiniz. (Sütun seçimlerini temizleyerek kaldırın.) Sütunları yeniden sağa veya sola sürükleyerek düzenleyebilirsiniz. Sütun kısayol menüsünü aşağıdaki çizimde gösterilmektedir.

 ![Kısayol Görünüm menüsünde Görevleri penceresinde](../debugger/media/parallel_tasks_contextmenu.png "Parallel_Tasks_ContextMenu")

## <a name="sorting-tasks"></a>Sıralama görevleri
 Görevler sütun ölçütlerine göre sıralamak için sütun başlığına tıklayın. Örneğin,'ı tıklatarak **kimliği** sütun başlığı, görevleri görev kimliği göre sıralama yapabilirsiniz: 1,2,3,4,5 ve benzeri. Sıralama düzenini tersine çevirmek için sütun başlığını tekrar tıklatın. Geçerli sıralama sütunu ve sıralama düzenini sütununda bir ok ile belirtilir.

## <a name="grouping-tasks"></a>Görevler gruplandırma
 Görevleri için liste görünümündeki sütunlardan göre gruplandırabilirsiniz. Örneğin, sağ tıklanarak **durum** sütun başlığını ve ardından **Group by** > **[*durum*]**, şunları yapabilirsiniz aynı durumundaki tüm görevleri gruplandırın. Örneğin, böylece neden bunlar engellenen üzerinde odaklanmak görevleri bekleyen hızlı bir şekilde görebilir. İlgi hata ayıklama oturumu sırasında değil bir grup da daraltabilirsiniz. Aynı şekilde, diğer sütunlara göre gruplandırabilirsiniz. Bir grup (Çalıştır) olabilir yalnızca Grup üstbilgisi yanındaki düğmesine tıklayarak bayrağı. Aşağıdaki çizimde gösterildiği **görevleri** gruplandırılmış modunda penceresi.

 ![Görevleri penceresini gruplandırılmış modunda](../debugger/media/parallel_tasks_groupedmode.png "Parallel_Tasks_GroupedMode")

## <a name="parent-child-view"></a>Üst alt görünümü
 (Bu görünüm, yalnızca yönetilen kod için kullanılabilir.) Sağ tıklanarak **durum** sütun başlığını ve ardından **Group by** > **üst**, görev listesi, hiyerarşik bir görünümü değiştirebilirsiniz Her alt görev görüntülenen veya üst altında gizli bir alt düğümü değil.

## <a name="flagging-tasks"></a>Görevler işaretleme
 Bir görevin çalıştığı görevini seçerek görev liste öğesi ve sonra seçerek iş parçacığı bayrak **bayrağı atanan iş parçacığı** ve bağlam menüsünden ya da ilk sütunda bayrak simgesine tıklayarak. Bazı görevler bayrağı, daha sonra yalnızca bunlar üzerinde odaklanabiliriz bayrak eklenmiş tüm görevler en çok duruma getirmek için bayrağı sütunu sıralayabilirsiniz. Aynı zamanda **Paralel Yığınlar** penceresini görüntülemek için yalnızca görevler bayrağı. Bu hata ayıklama için ilgilendiğiniz değil görevlerini filtrelemenize olanak sağlar. Hata ayıklama oturumları arasında bayrakları kalıcı değildir.

## <a name="freezing-and-thawing-tasks"></a>Dondurma ve görevleri çözme
 Bir görevin çalıştığı görev listesi öğesini sağ tıklatın ve ardından iş parçacığı Dondur **atanan iş parçacığı Dondur**. (Bir görevin zaten dondurulmuş komut varsa, **çözme atanan iş parçacığı**.) Bir iş parçacığı dondurmak, sonra geçerli kesme noktası aracılığıyla koda adım zaman bu iş parçacığı çalıştırmaz. **Dondur tüm iş parçacıklarının ancak bu bir** komutu görev liste öğesi yürütüyor dışındaki tüm iş parçacıklarının donuyor.

 Diğer menü öğelerinin her görev için aşağıda gösterilmektedir.

 ![Kısayol iş parçacığı menüsü Görevleri penceresinde](../debugger/media/parallel_tasks_contextmenu2.png "Parallel_Tasks_ContextMenu2")

## <a name="switching-the-active-task-or-frame"></a>Etkin bir görevi veya çerçeve geçiş

**Geçiş göreve** komutu etkin görev geçerli görev yapar. **Geçiş çerçeveye** komutu etkin yığın kare seçili yığın yapar. Hata ayıklayıcı bağlamını geçerli görev veya seçili yığın çerçevesi geçirir.

## <a name="see-also"></a>Ayrıca bkz.

- [Hata ayıklayıcı temel bilgileri](../debugger/debugger-basics.md)
- [Yönetilen kodda hata ayıklama](../debugger/debugging-managed-code.md)
- [Paralel Programlama](/dotnet/standard/parallel-programming/index)
- [Eşzamanlılık Çalışma Zamanı](/cpp/parallel/concrt/concurrency-runtime)
- [Paralel Yığınlar penceresini kullanma](../debugger/using-the-parallel-stacks-window.md)
- [İzlenecek yol: paralel uygulamada hata ayıklama](../debugger/walkthrough-debugging-a-parallel-application.md)