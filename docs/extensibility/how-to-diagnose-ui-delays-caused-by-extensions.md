---
title: Visual Studio'da gecikmeler uzantısı UI tanılama | Microsoft Docs
ms.custom: ''
ms.date: 01/26/2018
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
author: PooyaZv
ms.author: pozandev
manager: douge
ms.workload: multiple
ms.openlocfilehash: b63f9538c916b74874031704a1f60d0646f8d032
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-diagnose-ui-delays-caused-by-extensions"></a>Nasıl yapılır: kullanıcı Arabirimi tanılamak uzantıları tarafından kaynaklanan gecikmeler

UI yanıt veremez hale geldiğinde, Visual Studio kullanıcı Arabirimi iş parçacığı çağrı yığınını yaprak ile başlayan ve temel çalışma inceler. Visual Studio bir çağrı yığını çerçevesi yüklü ve etkin uzantının bir parçası olan bir modüle ait olduğunu belirlerse, bir bildirim gösterilir.

![UI gecikmesi (yanıt vermeyi durdurma sorununu) bildirim](media/ui-delay-notification-in-vs.png)

Bildirim UI gecikmesi (yani yanıt vermeyi durdurma sorununu kullanıcı arabiriminde) bir uzantı koddan sonucu olabilir kullanıcıya bildirir. Uzantı veya uzantısı gelecekteki bildirimleri devre dışı bırakma seçenekleri ile kullanıcı da sağlar.

Bu belgede nasıl ne uzantısı kodunuzda UI gecikmesi bildirimleri neden olan tanılayabilirsiniz açıklanmaktadır. 

> [!NOTE]
> Visual Studio Deneysel örneğini UI gecikmesi yaşanır tanılamak için kullanmayın. UI gecikmesi bildirimler için gerekli çağrı yığını analiz bazı bölümleri UI gecikmesi bildirimleri değil gösterilebileceği anlamına Deneysel örneğini kullanırken devre dışı bırakılmıştır.

Tanılama işlemine genel bakış aşağıdaki gibidir:
1. Tetikleyici senaryo tanımlayın.
2. VS oturum açma etkinliği ile yeniden başlatın.
3. ETW İzleme başlatın.
4. Yeniden görüntülenmesini bildirim tetikler.
5. ETW İzleme durdurun.
6. Gecikme kimliklerini almak için Etkinlik günlüğünü inceleyin
7. Adım 6 gecikme Kimliğini kullanarak ETW İzleme analiz edin.

Aşağıdaki bölümlerde, bu adımlar daha ayrıntılı ele alacağız.

## <a name="identifying-the-trigger-scenario"></a>Tetikleyici senaryo tanımlama

UI gecikmesi tanılamak için önce hangi (eylemlerin sırasını) bildirim göstermek Visual Studio neden tanımlamak gerekir. Sırada, bildirim açık günlük ile daha sonra tetiklemek için budur.

## <a name="restarting-vs-with-activity-logging-on"></a>Oturum açma etkinliği ile VS yeniden başlatılıyor

Visual Studio "etkinlik günlüğü" üretebilir sorunu ayıklarken yararlı bilgiler sağlayan. Etkinlik Visual Studio'da oturum açmak için Visual Studio ile başlangıç `/log` komut satırı seçeneği. Visual Studio başlatıldıktan sonra etkinlik günlüğü şu konumda depolanır:

```DOS
%APPDATA%\Microsoft\VisualStudio\<vs_instance_id>\ActivityLog.xml
```

Kimliği örneği, VS bulma konusunda daha fazla bilgi edinmek için [algılama ve Visual Studio Örnekleri yönetmek için Araçlar](../install/tools-for-managing-visual-studio-instances.md). Bu etkinlik günlüğü daha sonra UI gecikmesi yaşanır ve ilgili bildirimleri hakkında daha fazla bilgi bulmak için kullanacağız.

## <a name="starting-etw-tracing"></a>Başlangıç ETW İzleme

Kullanabileceğiniz [PerfView](https://github.com/Microsoft/perfview/) ETW izleme toplanacak. PerfView ETW İzleme toplama ve çözümleme için kullanımı kolay arabirim sağlar. Bir izleme toplamak için aşağıdaki komutu kullanın:

```DOS
Perfview.exe collect C:\trace.etl /BufferSizeMB=1024 -CircularMB:2048 -Merge:true -Providers:*Microsoft-VisualStudio:@StacksEnabled=true -NoV2Rundown /kernelEvents=default+FileIOInit+ContextSwitch+Dispatcher
```

Bu UI gecikmesi bildirimlerle ilgili olaylar için Visual Studio kullanan bir sağlayıcı "Microsoft Visual Studio" Sağlayıcı sağlar. Aynı zamanda anahtar sözcüğü PerfView "İş parçacığı zaman yığınları" görünümü oluşturmak için kullanabileceğiniz çekirdek sağlayıcısı belirtir.

## <a name="triggering-the-notification-to-appear-again"></a>Yeniden görüntülenmesini bildirim tetikleme

PerfView izleme koleksiyonu başladıktan sonra yeniden görüntülenmesini tetikleyici eylem dizisinden (1. adım) bildirim için kullanabilirsiniz. Bildirim gösterilen sonra işlem ve çıktı izleme dosyası oluşturmak PerfView için izleme koleksiyonu durdurabilirsiniz.

## <a name="stopping-etw-tracing"></a>ETW İzleme Durdurma

İzleme toplamasını durdurmak için basitçe kullanmak `Stop collection` PerfView penceresinde düğmesini. İzleme koleksiyonu durdurduktan sonra PerfView ETW olayları otomatik olarak işleyecek ve bir çıkış izleme dosyası oluşturur.

## <a name="examining-the-activity-log-to-get-the-delay-id"></a>Gecikme kimlik almak amacıyla etkinlik günlüğü inceleniyor

Daha önce belirtildiği gibi etkinlik günlüğü bulabilirsiniz `%APPDATA%\Microsoft\VisualStudio\<vs_instance_id>\ActivityLog.xml`. Visual Studio uzantı UI gecikmesi her algıladığında, bir düğüm ile etkinlik günlüğü Yazar `UIDelayNotifications` kaynağı olarak. Bu düğüm, dört adet UI gecikmesi hakkında bilgi içerir:

- UI gecikmesi kimliği, UI gecikmesi VS oturumda benzersiz olarak tanımlayan bir sıralı numarası
- Visual Studio oturumunuzu kapatmak için başlangıç tarihinden tanıtan oturum kimliği
- Bir bildirim UI gecikmesi desteklemediğini gösterildi
- Büyük olasılıkla UI gecikmesi nedeniyle uzantısı

```xml
<entry>
  <record>271</record>
  <time>2018/02/03 12:02:52.867</time>
  <type>Information</type>
  <source>UIDelayNotifications</source>
  <description>A UI delay (Delay ID = 0) has been detected. (Session ID=16e49d4b-26c2-4247-ad1c-488edeb185e0; Blamed extension="UIDelayR2"; Notification shown? Yes.)</description>
</entry>
```

> [!NOTE]
> Bir bildirim tüm UI gecikmeler sonucu. Bu nedenle, her zaman "gösterilen bildirim?" denetlemelisiniz doğru sağ UI gecikmesi tanımlamak için değer.

Etkinlik günlüğünde doğru UI gecikmesi bulduktan sonra düğümünde belirtilen UI gecikmesi kimliği yazın. Sonraki adımda karşılık gelen ETW olayı aramak için kimliği kullanacaksınız.

## <a name="analyzing-the-etw-trace"></a>ETW İzleme analiz etme

Ardından, izleme dosyasını açın. PerfView veya yeni bir örneğini başlatarak ve sol üst penceresinin izleme dosyasının konumu için geçerli bir klasör yolu ayarını aynı örneği kullanarak bunu yapabilirsiniz.

![Klasör yolu Perfview içinde ayarlama](media/perfview-set-path.png)

Ardından, sol bölmede izleme dosyasını seçin ve sağ tıklatın veya bağlam menüsünden açık seçerek açın.

> [!NOTE]
> Varsayılan olarak PerfView Zip arşivini çıkarır. Trace.zip açtığınızda otomatik olarak arşiv açar ve izleme açar. Bu izleme toplama sırasında "Zip" kutusunu kaldırarak atlayabilirsiniz. Aktarmak ve farklı makinelerde izlemelerini kullanın planlıyorsanız, ancak "Zip" kutusunu işaretleyerek karşı öneririz. Bu seçeneği olmadan Ngen derlemeler için gerekli pdb izleme eşlik değil ve bu nedenle Ngen derlemelerden simgeleri hedef makinede çözümlenmeyecek. (Bkz [bu blog gönderisine](https://blogs.msdn.microsoft.com/devops/2012/12/10/creating-ngen-pdbs-for-profiling-reports/) Ngen derlemeler için pdb hakkında daha fazla bilgi için.) 

PerfView işlemek ve izlemeyi açmak birkaç dakika sürebilir. İzleme açıldıktan sonra çeşitli "Görünüm" listesi altında görünür.

![PerfView izleme Özet görünümü](media/perfview-summary-view-events-selected.png)

İlk "Olayları" görünümü UI gecikmesi zaman aralığını elde etmek için kullanırız:

1. İzleme "Olayları" düğümünde seçip sağ tıklatın veya bağlam menüsünden açık seçerek "Olayları" görünümünü açın.
2. Seçin "`Microsoft-VisualStudio/ExtensionUIUnresponsiveness`" sol bölmede.
3. ENTER tuşuna basın

Seçimi uygulanır ve tüm `ExtensionUIUnresponsiveness` olayları sağ bölmede görüntülenir.

![Olayları görünümünde olayları seçme](media/perfview-event-selection.png)

Sağ bölmede her satır için UI gecikmesi karşılık gelir. Olay "Gecikme ID" değeri, adım 6'dan etkinlik günlüğü gecikme Kimliğinde eşleşmelidir içerir. Bu yana `ExtensionUIUnresponsiveness` UI gecikmesi, olayın zaman damgası sonunda UI gecikmesi bitiş zamanı (kabaca) işaretleri tetiklenir. Olay, gecikme süresini de içerir. Biz UI gecikmesi başladığı zaman damgası elde etmek için son zaman damgası süresini çıkarabilirsiniz.

![UI gecikmesi zaman aralığı hesaplama](media/ui-delay-time-range.png)

Önceki ekran görüntüsü, örneğin, olayın zaman damgası 12,125.679 ve gecikme süresi (ms) 6,143.085. Bu nedenle,
* 12,125.679 6,143.085 gecikme başlangıcıdır 5,982.594 =.
* UI gecikmesi zaman aralığı için 5,982.594 12,125.679 ' dir.

Zaman aralığı sahibiz sonra biz dışında olaylar görünümü kapatın ve "İş parçacığı (StartStop etkinliklerle) zaman yığınları" görünümünü açın. Bu görünüm özellikle kullanışlı nedeni genellikle kullanıcı Arabirimi iş parçacığı engelleme uzantıları yalnızca başka bir iş parçacığı veya g/Ç-bağlama işlemi bekliyor. Bu nedenle, çoğu durumda için gidilecek seçeneği olan "CPU yığını" görünümü, bu işlem sırasında CPU kullanmadığından engelleme iş parçacığı harcadığı zamanı yakalamak değil. "İş parçacığı zaman yığınları" düzgün engellenen gösteren zamanına göre bu sorunu çözer.

![İş parçacığı (StartStop etkinliklerle) zaman yığınları düğümünde PerfView Özet görünümü](media/perfview-thread-time-with-startstop-activities-stacks.png)

"İş parçacığı zaman yığınları" açılırken görüntülemek için analiz başlatmak için "devenv" işlem seçin.

![İş parçacığı UI gecikmesi çözümleme için zaman yığınları görünümü](media/ui-delay-thread-time-stacks.png)

"İş parçacığı zaman yığınları" Görünümü'nde sol üst içinde sayfasının yığınları bu zaman aralığı için ayarlanmış şekilde önceki adımda ve Enter tuşuna basın biz hesaplanan değerler için zaman aralığını ayarlayabilirsiniz.

> [!NOTE]
> Hangi iş parçacığı UI olduğunu belirleme (Başlangıç) iş parçacığı Visual Studio zaten açıldıktan sonra izleme koleksiyonu başlattıysanız mantığa olabilir. Ancak, ilk kullanıcı Arabirimi (Başlangıç) iş parçacığı yığında olasılıkla her zaman devenv tarafından izlenen işletim sistemi DLL'leri (ntdll.dll ve kernel32.dll) öğeleridir!? ve ardından msenv!. Bu sırası, kullanıcı Arabirimi iş parçacığı tanımlamaya yardımcı olabilir.

 ![Başlangıç iş parçacığı tanımlama](media/ui-delay-startup-thread.png)

Bu görünüm yalnızca paketinizi modüllerden içeren yığınları ekleyerek ayrıca filtreleyebilirsiniz.

* Varsayılan olarak eklenen herhangi bir gruplama kaldırmak için boş metin için "GroupPats" ayarlayın.
* "Mevcut işlem filtre ek olarak, derleme adı kısmını içerecek şekilde IncPats" kümesi. Bu durumda, "devenv; olmalıdır UIDelayR2 ".

![İş parçacığı zaman yığınları görünümünde GroupPath ve IncPath ayarlama](media/perfview-tts-group-path-inc-path.png)

PerfView Kılavuzu kodunuzda performans sorunlarını tanımlamak için kullanabileceğiniz Yardım menüsü altında açıklanmıştır. Ayrıca, aşağıdaki bağlantılar, Visual Studio API kodunuzu en iyi duruma getirmek için iş parçacığı kullanma hakkında daha fazla bilgi sağlar:

* [https://aka.ms/vsthreading](https://aka.ms/vsthreading)
* [https://aka.ms/vsthreadingcookbook](https://aka.ms/vsthreadingcookbook)

Yeni Visual Studio statik çözümleyiciler uzantıları için de kullanabilirsiniz (NuGet paketi [burada](https://www.nuget.org/packages/microsoft.visualstudio.sdk.analyzers)), sağlayan kılavuzu üzerinde en iyi yöntemler verimli uzantıları yazmak için. Bir listesini görmek [VS SDK çözümleyiciler](https://github.com/Microsoft/VSSDK-Analyzers/blob/master/doc/index.md) ve [çözümleyiciler iş parçacığı oluşturma](https://github.com/Microsoft/vs-threading/blob/master/doc/analyzers/index.md).

> [!NOTE]
> Yanıt vermeyi durdurma sorununu bağımlılıkları nedeniyle adres ise üzerinde denetiminiz olmayan (örneğin uzantınızı zaman uyumlu VS Hizmetleri kullanıcı Arabirimi iş parçacığı üzerinde çağırmak varsa), hakkında bilmek isteriz. Visual Studio iş ortağı programımız üyesi olması durumunda, bize bir geliştirici destek isteği göndererek başvurabilirsiniz. Aksi halde, 'Bir sorun bildirmek' içerir ve geri bildirim göndermek üzere aracını `"Extension UI Delay Notifications"` başlık. Lütfen çözümleme ayrıntılı bir açıklaması da içerir.
