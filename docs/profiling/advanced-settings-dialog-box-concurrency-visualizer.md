---
title: Gelişmiş Ayarlar iletişim kutusu (eşzamanlılık görselleştiricisi) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.settings
ms.assetid: bb3d90aa-5f08-4953-9be0-be6cea11633d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8d697ee37cb8412e4fa0a51096858d9fa4b17877
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34690799"
---
# <a name="advanced-settings-dialog-box-concurrency-visualizer"></a>Gelişmiş Ayarlar iletişim kutusu (eşzamanlılık görselleştiricisi)
Kullanarak **Gelişmiş ayarları** iletişim kutusu Eş zamanlılık Görselleştirici izlemeleri nasıl toplanır denetleyebilirsiniz.  İletişim kutusu sembolleri, sadece kendi kodumu, arabelleğe alma, filtreleme, CLR olayları, işaretçileri, sağlayıcıları ve dosyaları için sekme bulunur.  
  
## <a name="symbols"></a>Simgeleri  
 Eşzamanlılık görselleştiricisi Visual Studio hata ayıklayıcısında simge ayarlarının aynısını kullanır. Eşzamanlılık görselleştiricisi ayarları performans verileri ile ilişkili çağrı yığınları çözümlemek için kullanır.  Eşzamanlılık görselleştiricisi izlemeleri işlediğinde, Ayarları sayfasında belirtilen simge sunucuları erişir.  Bu verileri bir ağ üzerinden erişildiğinde izleme işleme yavaşlar.  Simgeler çözümlemek için gerekli süreyi azaltmak için simgeler yerel olarak önbelleğe alabilir. Visual Studio simgeler yüklenmişse, bunları yerel önbellekten yükler.  
  
## <a name="just-my-code"></a>Yalnızca Kendi Kodum  
 Varsayılan olarak, sadece kendi kodumu kümesidir. *exe* ve. *dll* Visual Studio geçerli çözümde ile ilişkili olan dosyaları. Çağrı yığınları filtrelemek için sadece kendi kodumu özelliğini kullandığınızda eşzamanlılık görselleştiricisi bu dosyaları kümesini değerlendirir. Sadece kendi kodumu sekmesinde içeren dizinler ekleyebilirsiniz. *exe* ve. *dll* eşzamanlılık görselleştiricisi sadece kendi kodumu kullanan konumlara dosyaları.  
  
 Yollarını. *exe* ve. *dll* dosyaları izleme toplandığında izleme dosyasında saklanır.  Bu ayarı değiştirmek daha önce toplanan tüm izlemeleri etkilemez.  
  
## <a name="buffering"></a>Arabelleğe alma  
 Eşzamanlılık görselleştiricisi izleme topladığı olay Windows için izleme (ETW) kullanır.  ETW olaylarını depolayan çeşitli arabellekleri kullanır.  Varsayılan ETW arabellek ayarları tüm durumlarda ve bazı durumlarda en iyi olmayabilir, kaybedilen olaylar gibi sorunlara neden olabilir.  ETW arabellek ayarlarını yapılandırmak için arabelleğe kaydetme açık sekmesini kullanabilirsiniz. Daha fazla bilgi için bkz: [olay izleme](http://go.microsoft.com/fwlink/?LinkId=234579) ve [EVENT_TRACE_PROPERTIES yapısı](http://go.microsoft.com/fwlink/?LinkId=234580).  
  
## <a name="filter"></a>Filtrele  
 Filtre sekmesinde eşzamanlılık görselleştiricisi toplayan olay kümesini seçebilirsiniz. Alt olayların seçerek raporlarında görüntülenir, her izleme boyutunu azaltır ve izlemeleri işlemek için gerekli olan süreyi azaltır veri türlerini kısıtlar.  
  
### <a name="clr-events"></a>CLR olayları  
 Ortak dil çalışma zamanı (CLR) tarafından oluşturulan olayları yönetilen çağrı yığınları çözümlemek eşzamanlılık görselleştiricisi etkinleştirin.  CLR olayları koleksiyonunu devre dışı bırakırsanız, izleme boyutu azaltılır, ancak bazı çağrı yığınları verilmiyor giderir.  Sonuç olarak, bazı CPU iş parçacığı etkinliği yanlış kategorilere.  
  
### <a name="collect-for-native-processes"></a>Yerel işlemleri için TOPLA  
 Yönetilen bir işlemi yalnızca profili yerel işlemleri için normalde gereksiz olduklarından, varsayılan olarak, CLR olayları toplanır.  Bazı durumlarda (örneğin, yerel işlem CLR barındırdığında) yerel işlem CLR olaylarını toplayan gerekebilir.  Bu durumda, seçin **toplamak için yerel işlemleri** onay kutusu.  
  
### <a name="disable-rundown-events"></a>Özeti olaylarını devre dışı bırak  
 CLR olayları iki sağlayıcılardan oluşturur: çalışma zamanı ve özeti.  İstiyorsanız, CLR çalışma zamanı modülü olaylarını Topla ancak özeti olay toplama önlemek istiyorsanız, seçin **devre dışı özeti olayları** onay kutusu.  Bu koleksiyon tarafından üretilen izleme dosyasının boyutunu azaltır, ancak bazı yığınları verilmiyor çözebilir. Daha fazla bilgi için bkz: [CLR ETW sağlayıcılar](/dotnet/framework/performance/clr-etw-providers)  
  
### <a name="sample-events"></a>Örnek olaylar  
 Örnek olaylar, iş parçacığı yürütmesi ile ilişkili çağrı yığınları toplamak için kullanabilirsiniz. Bu olaylar, geçerli işlemde çalışan iş parçacıkları için mili saniye başına yaklaşık bir kez toplanır. Örnek olaylar koleksiyonunu devre dışı bırakırsanız, toplanan izleme boyutunu azalır, ancak iş parçacığı yürütmesi ile ilişkili herhangi bir çağrı yığınları görüntüleyemezsiniz.  
  
### <a name="gpu-events"></a>GPU olayları  
 GPU, DirectX tarafından oluşturulan olayları olaylardır. GPU olayları koleksiyonunu devre dışı bırakırsanız, toplanan izleme boyutunu azaltılmış ancak kullanım görünümü ya da iş parçacıkları görünümü DirectX altyapısı etkinliğinde herhangi bir GPU etkinlik görüntüleyemez.  
  
### <a name="file-io-events"></a>Dosya g/ç olayları  
 Dosya g/ç olayları geçerli işlem adına diske erişimleri temsil eder.  Dosya g/ç olayları devre dışı bırakırsanız, izleme boyutunu azalır, ancak iş parçacıkları görünümü herhangi bir bilgi disk kanalları ya da Disk işlemleri hakkında bildirmez.  
  
## <a name="markers"></a>İşaretçileri  
 Üzerinde **işaretçileri** sekmesinde eşzamanlılık görselleştiricisi işaretleyici olarak gösterilen ETW sağlayıcılar kümesini yapılandırabilirsiniz.  Ayrıca işaretleyici koleksiyonu önem düzeyini ve ETW kategorisine göre filtreleyebilirsiniz.  Kullanıyorsanız [eşzamanlılık görselleştiricisi SDK](../profiling/concurrency-visualizer-sdk.md) ve böylece iş parçacıkları görünümünde görünür kendi işaret sağlayıcısını kullanarak, bunu burada kaydedebilirsiniz.  
  
### <a name="add-a-new-provider"></a>Yeni bir sağlayıcı Ekle  
 Kodunuzu kullanıyorsa [eşzamanlılık görselleştiricisi SDK](../profiling/concurrency-visualizer-sdk.md) veya izleyin ETW olayları oluşturur <xref:System.Diagnostics.Tracing.EventSource> kuralı, görüntüleyebilirsiniz bu olayları eşzamanlılık görselleştiricisi bu iletişim kutusunda kaydederek.  
  
 İçinde **adı** alanında, sağlayıcı tarafından oluşturulan olaylar türlerini açıklayan bir ad girin.  İçinde **GUID** alan, bu sağlayıcıyla ilişkili GUID girin. (Bir GUID her ETW sağlayıcı ile ilişkilidir.)  
  
 İsteğe bağlı olarak, kategori veya önem düzeyi temelinde bu sağlayıcı olayları filtrelemek belirtebilirsiniz.  Kategori kullanabilirsiniz filtrelemek için alan eşzamanlılık görselleştiricisi SDK kategorisine bağlı.  Bunu yapmak için virgülle ayrılmış bir dize kategorilerinin veya kategorileri aralıklarını girin.  Bu olayların kategorilerini göstermek için geçerli sağlayıcıda belirtir.  Ekliyorsanız bir <xref:System.Diagnostics.Tracing.EventSource> sağlayıcısı ETW anahtar sözcüğe göre filtre uygulamak için kategori alanı kullanabilir.  Anahtar sözcüğü bir bit maskesi olduğundan, virgülle ayrılmış bir dize tamsayıların hangi bit maskesi kümesini belirlemek için kullanabilirsiniz. Örneğin, "1,2" ilk ve ikinci BITS ayarlar ve bu ondalık 6 dönüşür.  
  
 Önem düzeyi listenin bir önem veya belirtilen değerden küçüktür ETW düzey olayları filtrelemek için kullanabilirsiniz.  
  
### <a name="configure-an-existing-provider"></a>Varolan bir sağlayıcı yapılandırın  
 Varolan bir sağlayıcı ile ilişkili ayarları düzenlemek için listeden seçin ve ardından **düzenleme sağlayıcısı** düğmesi.  Ad, GUID ve filtreleme ayarlarını değiştirebilirsiniz.  
  
### <a name="filter-marker-data-out-of-concurrency-visualizer-reports"></a>Eşzamanlılık görselleştiricisi raporları işaret verileri filtreleme  
 Gelecekte izlemeleri görünmesini belirli bir sağlayıcı için veri istemiyorsanız, kaldırmak istediğiniz sağlayıcı yanındaki onay kutusunu temizleyin.  
  
## <a name="files"></a>Dosyalar  
 Üzerinde **dosyaları** sekmesi altında hangi izleme dosyaları depolanır her zaman bir izleme dizini toplanır belirtebilirsiniz.  Eşzamanlılık görselleştiricisi topladığı her izleme için dört dosyaları oluşturur:  
  
-   Bir çekirdek modu olay izleme (ETL) günlük dosyası (*.* Kernel.etl*)  
  
-   Bir kullanıcı modu olay izleme günlük dosyasını (*.* User.etl*)  
  
-   Eşzamanlılık görselleştiricisi veri dosyası (*.* CVData*)  
  
-   Eşzamanlılık görselleştiricisi izleme dosyası (*.* CVTrace*)  
  
 İki ETL dosya Ham izleme verilerini depolamak ve işlenen verilerin iki eşzamanlılık görselleştiricisi dosyaları depolamak.  Bir izleme işlendikten sonra ham ETL dosyaları genellikle kullanılmaz.  Seçme **silmek olay izleme günlüğü (ETL) dosyaları çözümleme sonrasında** onay kutusu, diskte depolanan izleme veri miktarını azaltır.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Yalnızca kendi kodum](../profiling/just-my-code-threads-view.md)   
 [Eşzamanlılık görselleştiricisi işaretleyicileri](../profiling/concurrency-visualizer-markers.md)