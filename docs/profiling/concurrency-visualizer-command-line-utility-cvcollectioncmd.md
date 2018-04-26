---
title: Eşzamanlılık görselleştiricisi komut satırı yardımcı programı (CVCollectionCmd) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.performance.cvcollectioncmd
ms.assetid: 476601be-1608-4014-af15-5aba6ccbed1c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 606a6c021247a00b2244986d5f91ad19d6a167f4
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="concurrency-visualizer-command-line-utility-cvcollectioncmd"></a>Eşzamanlılık Görselleştiricisi Komut Satırı Yardımcı Programı (CVCollectionCmd)
Eşzamanlılık görselleştiricisi komut satırı yardımcı programını (CVCollectionCmd.exe), böylece bunları için Visual Studio eşzamanlılık görselleştiricisi görebilirsiniz komut satırından izlemeleri toplamak için kullanabilirsiniz. Araçlar Visual Studio yüklü olmayan bilgisayarlarda kullanılabilir.  
  
> [!NOTE]
>  Eşzamanlılık görselleştiricisi, Visual Studio 2013'ten başlayarak, isteğe bağlı bir uzantıdır. (Daha önce bunu Visual Studio'da dahil edilmiş.) İndirebilirsiniz [eşzamanlılık görselleştiricisi toplama araçları Visual Studio 2015 için](http://www.microsoft.com/en-in/download/details.aspx?id=49103) İndirme Merkezi'nden.  
  
## <a name="download-the-concurrency-visualizer-command-line-utility"></a>Eşzamanlılık görselleştiricisi komut satırı yardımcı programını indirin  
 Karşıdan yükleme ve komut satırı yardımcı programını yüklemek için Git [eşzamanlılık görselleştiricisi toplama araçları Visual Studio 2015 için](http://www.microsoft.com/en-in/download/details.aspx?id=49103) ve yönergeleri izleyin. Varsayılan olarak %ProgramFiles%\Microsoft eşzamanlılık görselleştiricisi koleksiyonu Tools\ CVCollectionCmd.exe yüklenir (% ProgramFiles (x86) %\Microsoft eşzamanlılık görselleştiricisi koleksiyonu Tools\ x64 üzerinde bilgisayarlar).  
  
## <a name="collect-a-trace-with-cvcollectioncmd"></a>Bir izleme CVCollectionCmd ile Topla  
 Uygulama CVCollectionCmd ile başlatarak veya eklemeyi izleme toplayabilir. Aşağıdaki komut başvurusu seçeneklerinizi için bkz. Örneğin  
  
```  
<Path>CVCollectionCmd /launch c:\myapp\myapp.exe /outdir c:\myapp\data  
```  
  
## <a name="commands-and-parameters"></a>Komutları ve parametreleri  
 Komut satırı yardımcı programı komutları ve parametreleri hakkında Yardım almak için bu komut istemine yazın:  
  
 **CvCollectionCmd /?**  
  
|Seçenek|Açıklama|Parametreler|Döndürülen değerler|  
|------------|-----------------|----------------|-------------------|  
|Sorgu|Koleksiyon başlatılmış olup olmadığını döndürür.|Yok.|Koleksiyon başlatmaya hazır olup olmadığını 0.<br /><br /> 1 koleksiyonu zaten devam ediyor.<br /><br /> Koleksiyon devam ediyor, ancak bir veya daha fazla gerekli içinde değilse 2 [ETW](/dotnet/framework/wcf/samples/etw-tracing) oturumları zaten etkin.|  
|Başlat|Belirtilen işlem eşzamanlılık görselleştiricisi altında çalışır.|Yürütülebilir dosya yolu.|Çalıştır başarılı olursa 0.<br /><br /> Hedef uygulama başlatılamadı Çalıştır başarısız olduysa 1.<br /><br /> 13 Çalıştır CVCollectionCmd belirtilen çıkış dizinine yazma izinlerinin yetersiz olduğundan başarısız oldu.|  
|İliştir|Sistem genelinde izleme toplamaya başlar; belirtilmişse, aksi halde, bir işlem ekler.|Yok.|Ek başarılı olursa 0.<br /><br /> Belirtilen işlem geçersiz ya da belirsiz olduğundan ek başarısız olursa 1.<br /><br /> 13 Eki CVCollectionCmd belirtilen çıkış dizinine yazma izinlerinin yetersiz olduğundan başarısız oldu.|  
|Ayır|Koleksiyon durdurur.|Yok.|ayrılmayı başarılı olursa 0.<br /><br /> Koleksiyon şu anda devam eden değil ayrılmayı başarısız olduysa 1.<br /><br /> Koleksiyon durdurulamadı ayrılmayı başarısız olduysa 2.|  
|Çözümle|Belirtilen izleme analiz eder.|CVTrace dosyasının tam yolu.|Analiz başarılı olursa 0.<br /><br /> Analiz, çünkü sistem genelinde belirtilen izleme, ancak hiçbir hedef işlem belirtildi başlatamıyorsanız, 1.<br /><br /> Çözümleme izleme sistem genelinde ve bir işlem olmadığından başlatamıyorsanız 2 belirtildi.<br /><br /> Belirtilen işlem geçersiz çözümleme başarısız olduysa 3.<br /><br /> Belirtilen CVTrace dosyası geçersiz çözümleme başarısız olduysa 4.|  
|LaunchArgs|Hedef yürütülebilir bağımsız değişkenlerini belirtir. Bu seçenek yalnızca başlatma komutu için geçerlidir.|Uygulama için komut satırı bağımsız değişkeni.|Yok.|  
|OutDir|İzleme dosyalarının kaydedileceği dizini belirtir. Başlatma ve Attach komutları için geçerlidir.|Bir dizin yolu veya göreli yol.|Yok.|  
|İşlem|Attach komutunu ne zaman yürütülür için eklemek için işlem veya işlem Analiz komutunu çalıştırıldığında çözümlemek için bir izleme belirtir. Attach ve analiz komutları için geçerlidir.|PID veya işlemin adı.|Yok.|  
|Config|Koleksiyon ayarlarını Varsayılanları dışında istiyorsanız, yapılandırma dosyasının yolunu belirtir.   Başlatma, Ekle ve analiz komutları için geçerlidir.|Dizin yolu veya XML yapılandırma dosyası göreli yolu.|Yok.|  
  
## <a name="customizing-configuration-settings"></a>Yapılandırma ayarları özelleştirme  
 İzlemeleri toplamak için CVCollectionCmd kullanıyorsanız ve koleksiyon ayarlarını özelleştirmek istediğiniz, sonra bunları belirtmek için bir yapılandırma dosyası'nı kullanın.  
  
> [!NOTE]
>  İzlemeleri toplamak için Visual Studio kullandığınızda, yapılandırma dosyasını doğrudan değiştirmeyin.  Bunun yerine, kullanın [Gelişmiş ayarları](../profiling/advanced-settings-dialog-box-concurrency-visualizer.md) ayarlarını değiştirmek için iletişim kutusu.  
  
 Koleksiyon ayarlarını değiştirmek için CVCollectionCmd yardımcı programı çalıştırdığı makinedeki bir yapılandırma dosyası oluşturun. Yapılandırma dosyası sıfırdan oluşturabilir veya Visual Studio'nun yüklü olduğu bilgisayarın üzerindeki yapılandırma dosyasını kopyalayıp, değiştirebilirsiniz. Dosya adında `UserConfig.xml` ve bulunan **Yerel AppData** klasör. Yardımcı programını çalıştırdığınızda, başlatma, Attach veya Çözümle komutu ile birlikte yapılandırma seçeneğini kullanın.  Yapılandırma seçeneğiyle ilişkilendirilmiş parametresinde yapılandırma dosyasının yolunu belirtin.  
  
### <a name="configuration-file-tags"></a>Yapılandırma dosyası etiketleri  
 XML tabanlı yapılandırma dosyasıdır. Geçerli etiketler ve değerler şunlardır:  
  
|Etiket|Açıklama|Değerler|  
|---------|-----------------|------------|  
|Config|Genel yapılandırma dosyası demarcates.|Bu öğe içermelidir:<br /><br /> -MinorVersion<br />-MajorVersion|  
|MajorVersion|Yapılandırma dosyası ana sürümünü belirtir.|İçin 1 olmalıdır [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] projeleri. Yoksa, 1, yardımcı program çalışmaz.|  
|MinorVersion|Alt yapılandırma dosyası sürümünü belirtir.|İçin 0 olmalıdır [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] projeleri. Aksi halde 0, yardımcı program çalışmaz.|  
|IncludeEnvSymbolPath|Ortam simge yolu (_NT_SYMBOL_PATH) kullanıldığını belirleyen bir değer ayarlar.|-True<br />-False|  
|DeleteEtlsAfterAnalysis|Analiz tamamlandığında ETL dosyaların silinip silinmeyeceğini belirleyen bir değer ayarlar.|-True<br />-False|  
|SymbolPath|Sembol sunucusunun yolunu belirtir. Daha fazla bilgi için bkz: [hata ayıklama simge dosyaları almak için Microsoft Simge sunucusunu kullanmak](http://go.microsoft.com/fwlink/?LinkID=149389).|Bir dizin adı veya URL'si.|  
|İşaretçileri|İşaretçi sağlayıcıları listesini içerir.|Sıfır veya daha fazla MarkerProvider öğeleri içerebilir.|  
|MarkerProvider|Bir tek işaret sağlayıcısı belirtir.|Bu öğe içermelidir:<br /><br /> -Düzeyi<br />-GUID<br />-Adı<br /><br /> Bu öğeleri içerebilir:<br /><br /> -Kategorileri<br />-IsEnabled|  
|Düzey|Bir MarkerProvider önem düzeyini ayarlar.|-Düşük<br />-Normal<br />-Yüksek<br />-Kritik<br />-Her şeyi|  
|Guid|ETW işaret sağlayıcı genel benzersiz tanıtıcısı.|BİR GUID.|  
|Ad|İşaretçi sağlayıcının açıklamasını belirtir.|Bir dize.|  
|Kategoriler|İşaretçi sağlayıcısı için toplanan kategorileri belirtir.|Virgülle ayrılmış bir dize, sayılardan veya numaraları aralıklarına.|  
|IsEnabled|İşaretçi sağlayıcı koleksiyonu için etkin olup olmadığını belirleyen bir değer ayarlar.|-True<br />-False|  
|FilterConfig|Koleksiyondan filtrelenir ETW olayları yapılandırma seçeneklerinin listesini belirtir.|Bu öğeleri içerebilir:<br /><br /> -CollectClrEvents<br />-ClrCollectionOptions<br />-CollectSampleEvents<br />-CollectGpuEvents<br />-CollectFileIO|  
|CollectClrEvents|CLR olayları toplanan olup olmadığını belirleyen bir değer ayarlayın.|-True<br />-False|  
|ClrCollectionOptions|Yerel uygulamalar için CLR olayları toplamak ve verip NGEN özeti olaylarını Topla belirtir.|Bir, her ikisini birden veya hiçbiri bu değerleri içerebilir:<br /><br /> -CollectForNative<br />-DisableNGenRundown|  
|CollectSampleEvents|Örnek olaylar toplanan olup olmadığını belirleyen bir değer ayarlar.|-True<br />-False|  
|CollectGpuEvents|DX tarafından oluşturulan olayları toplanan olup olmadığını belirleyen bir değer ayarlar.|-True<br />-False|  
|CollectFileIO|Dosya g/ç olayları toplanan olup olmadığını belirleyen bir değer ayarlar.|-True<br />-False|  
|UserBufferSettings|Kullanıcı arabelleği ayarlarını parametrelerinin listesini belirtir.|Bu öğe içermelidir:<br /><br /> -BufferFlushTimer<br />-BufferSize<br />-MinimumBuffers<br />-MaximumBuffers|  
|KernelBufferSettings|Çekirdek arabelleği ayarlarını parametrelerinin listesini belirtir.|Bu öğe içermelidir:<br /><br /> -BufferFlushTimer<br />-BufferSize<br />-MinimumBuffers<br />-MaximumBuffers|  
|BufferFlushTimer|ETW arabellek boşaltma süreölçeri belirtir.|Pozitif bir tamsayı.|  
|BufferSize|Her olay izleme oturumu arabellek kilobayt cinsinden için ayrılan bellek miktarı.|0 arasında bir sayı 1024 karakter.|  
|MinimumBuffers|Olay izleme oturumu arabellek havuzu için ayrılan arabellekler minimum sayısı.|Pozitif bir tamsayı iki kez mantıksal çekirdek sayısına eşit veya daha büyük.|  
|MaximumBuffers|Olay izleme oturumu arabellek havuzu için ayrılan arabellek sayısı üst sınırı.|Büyük veya eşit MinimumBuffers sayı.|  
|JustMyCode|Sadece kendi kodumu dizinlerin listesini belirtir.|Sıfır veya daha fazla MyCodeDirectory öğelerinin listesi.|  
|MyCodeDirectory|Kodunuzu içeren bir dizini belirtir.|Mutlak bir yol.|  
  
### <a name="example"></a>Örnek  
 Başlangıçtan itibaren bir yapılandırma dosyası oluşturmak yerine aşağıdaki örneği kopyalayın ve sonra gereksinimlerinizi karşılayacak şekilde değiştirebilirsiniz.  
  
```xml  
<?xml version="1.0"?>  
<LocalConfig xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" MajorVersion="1" MinorVersion="0">  
  
  <IncludeEnvSymbolPath>true</IncludeEnvSymbolPath>  
  
  <DeleteEtlsAfterAnalysis>true</DeleteEtlsAfterAnalysis>  
  
  <TraceLocation>C:\traces</TraceLocation>  
  
  <SymbolPath>http://symweb</SymbolPath>  
  
  <Markers>  
    <MarkerProvider Name="Default" Guid="8d4925ab-505a-483b-a7e0-6f824a07a6f0" Level="Low" />  
    <MarkerProvider Name="TPL" Guid="2e5dba47-a3d2-4d16-8ee0-6671ffdcd7b5" Level="Normal" />  
    <MarkerProvider Name="TPL Dataflow" Guid="16f53577-e41d-43d4-b47e-c17025bf4025" Level="Normal" />  
    <MarkerProvider Name="TPL Synchronization" Guid="ec631d38-466b-4290-9306-834971ba0217" Level="Normal" />  
    <MarkerProvider Name="PLINQ" Guid="159eeeec-4a14-4418-a8fe-faabcd987887" Level="Normal" />  
    <MarkerProvider Name="Concurrency Runtime" Guid="f7b697a3-4db5-4d3b-be71-c4d284e6592f" Level="Normal" />  
    <MarkerProvider Name="Scenario Markers" Guid="fb9244c9-f23a-4966-8a9c-97a51f8c355b" Level="Low" />  
  
    <!-- The IsEnabled and Categories elements are optional -->  
    <MarkerProvider Name="myMarker1" Guid="d0dbb3a3-895c-4ce6-96d9-28f69d664dc3" Level="Critical" IsEnabled="false" Categories="0,1,3-5,8" />  
    <MarkerProvider Name="myMarker2" Guid="03452127-a617-4302-9e30-c0d10442e4ee" Level="Low" IsEnabled="false" Categories="0,1,3-5,8-10,11-13" />  
  </Markers>  
  
  <FilterConfig>  
    <CollectClrEvents>true</CollectClrEvents>  
    <ClrCollectionOptions>CollectForNative DisableNGenRundown</ClrCollectionOptions>  
    <CollectSampleEvents>true</CollectSampleEvents>  
    <CollectGpuEvents>true</CollectGpuEvents>  
    <CollectFileIO>true</CollectFileIO>  
  </FilterConfig>  
  
  <UserBufferSettings>  
    <BufferFlushTimer>0</BufferFlushTimer>  
    <BufferSize>256</BufferSize>  
    <MinimumBuffers>512</MinimumBuffers>  
    <MaximumBuffers>1024</MaximumBuffers>  
  </UserBufferSettings>  
  
  <KernelBufferSettings>  
    <BufferFlushTimer>0</BufferFlushTimer>  
    <BufferSize>256</BufferSize>  
    <MinimumBuffers>512</MinimumBuffers>  
    <MaximumBuffers>1024</MaximumBuffers>  
  </KernelBufferSettings>  
  
  <!-- List of MyCodeDirectory directories -->  
  <JustMyCode>  
    <MyCodeDirectory>C:\myBinaries1</MyCodeDirectory>  
    <MyCodeDirectory>C:\myBinaries2</MyCodeDirectory>  
  </JustMyCode>  
</LocalConfig>  
  
```
