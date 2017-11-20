---
title: "Hata ayıklama için SDK Yardımcıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dbgmetric.lib
- registry, Debugging SDK
- Debugging SDK, registry locations
- dbgmetric.h
- metrics [Debugging SDK]
ms.assetid: 80a52e93-4a04-4ab2-8adc-a7847c2dc20b
caps.latest.revision: "28"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d9c5d24c8a3a2bb81c87b2cc405a6885b8f23374
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="sdk-helpers-for-debugging"></a>Hata ayıklama için SDK Yardımcıları
Bu işlevler ve bildirimleri hata ayıklama motorları, ifade değerlendiricileri ve sembol sağlayıcıları C++ üzerinde uygulama için genel yardımcı işlevlerdir.  
  
> [!NOTE]
>  Şu anda bu işlevler ve bildirimleri yönetilen hiçbir sürümü vardır.  
  
## <a name="overview"></a>Genel Bakış  
 Visual Studio tarafından kullanılacak sırayla hata ayıklama motorları, ifade değerlendiricileri ve sembol sağlayıcıları için bunlar kayıtlı olması gerekir. Bu kayıt defteri alt anahtarları ve girişleri, aksi takdirde "ölçümleri ayarlama". bilinen ayarlayarak yapılır Aşağıdaki genel işlevler, bu ölçümleri güncelleştirme işlemini kolaylaştırmak için tasarlanmıştır. Bu işlevler tarafından güncelleştirilir her bir kayıt defteri alt anahtarı düzenini öğrenmek için kayıt defteri konumları bölümüne bakın.  
  
## <a name="general-metric-functions"></a>Genel ölçüm işlevleri  
 Bu hata ayıklama motoru tarafından kullanılan genel işlevlerdir. İşlevler için ifade değerlendiricisi özelleştirilmiş ve sembol sağlayıcıları daha sonra ayrıntılı.  
  
### <a name="getmetric-method"></a>GetMetric yöntemi  
 Bir ölçü değeri kayıt defterinden alır.  
  
```cpp  
HRESULT GetMetric(  
   LPCWSTR pszMachine,  
   LPCWSTR pszType,  
   REFGUID guidSection,  
   LPCWSTR pszMetric,  
   DWORD * pdwValue,  
   LPCWSTR pszAltRoot  
);  
```  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|pszMachine|[in] Kayıt yazılır büyük olasılıkla uzak makine adını (`NULL` yerel makine anlamına gelir).|  
|pszType|[in] Ölçüm türlerinden biri.|  
|guidSection|[in] GUID belirli altyapısını, değerlendirici, özel durum, vs. Bu, belirli bir öğe için bir ölçüm türü altında bir alt belirtir.|  
|pszMetric|[in] Elde ölçüm. Bu, belirli bir değerin adına karşılık gelir.|  
|pdwValue|[in] Ölçüm değerinden depolama konumu. DWORD (Bu örnekte) olduğu gibi BSTR, bir GUID veya GUID'leri dizisi döndürebilir GetMetric çeşitli özellikleri vardır.|  
|pszAltRoot|[in] Kullanmak için bir alternatif kayıt defteri kök. Kümesine `NULL` varsayılan değer kullanılacak.|  
  
### <a name="setmetric-method"></a>SetMetric yöntemi  
 Kayıt defterinde belirtilen ölçüm değeri ayarlar.  
  
```cpp  
HRESULT SetMetric(  
         LPCWSTR pszType,  
         REFGUID guidSection,  
         LPCWSTR pszMetric,  
   const DWORD   dwValue,  
         bool    fUserSpecific,  
         LPCWSTR pszAltRoot  
);  
```  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|pszType|[in] Ölçüm türlerinden biri.|  
|guidSection|[in] GUID belirli altyapısını, değerlendirici, özel durum, vs. Bu, belirli bir öğe için bir ölçüm türü altında bir alt belirtir.|  
|pszMetric|[in] Elde ölçüm. Bu, belirli bir değerin adına karşılık gelir.|  
|dwValue|[in] Ölçüm değerinde depolama konumu. DWORD (Bu örnekte), BSTR, bir GUID veya GUID'leri dizisi depolayabilir SetMetric çeşitli özellikleri vardır.|  
|fUserSpecific|[in] Ölçüm kullanıcıya özgü ise ve yerel makine hive yerine kullanıcının hive yazılmalıdır ise TRUE.|  
|pszAltRoot|[in] Kullanmak için bir alternatif kayıt defteri kök. Kümesine `NULL` varsayılan değer kullanılacak.|  
  
### <a name="removemetric-method"></a>RemoveMetric yöntemi  
 Belirtilen Ölçüm kayıt defterinden kaldırır.  
  
```cpp  
HRESULT RemoveMetric(  
   LPCWSTR pszType,  
   REFGUID guidSection,  
   LPCWSTR pszMetric,  
   LPCWSTR pszAltRoot  
);  
```  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|pszType|[in] Ölçüm türlerinden biri.|  
|guidSection|[in] GUID belirli altyapısını, değerlendirici, özel durum, vs. Bu, belirli bir öğe için bir ölçüm türü altında bir alt belirtir.|  
|pszMetric|[in] Kaldırılacak ölçüm. Bu, belirli bir değerin adına karşılık gelir.|  
|pszAltRoot|[in] Kullanmak için bir alternatif kayıt defteri kök. Kümesine `NULL` varsayılan değer kullanılacak.|  
  
### <a name="enummetricsections-method"></a>EnumMetricSections yöntemi  
 Kayıt defteri çeşitli ölçüm bölümlerde numaralandırır.  
  
```cpp  
HRESULT EnumMetricSections(  
   LPCWSTR pszMachine,  
   LPCWSTR pszType,  
   GUID *  rgguidSections,  
   DWORD * pdwSize,  
   LPCWSTR pszAltRoot  
);  
```  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|pszMachine|[in] Kayıt yazılır büyük olasılıkla uzak makine adını (`NULL` yerel makine anlamına gelir).|  
|pszType|[in] Ölçüm türlerinden biri.|  
|rgguidSections|[içinde out] Doldurulacak GUID'ler ön tahsis dizisi.|  
|pdwSize|[in] İçinde depolanan GUID'ler üst sınırını `rgguidSections` dizi.|  
|pszAltRoot|[in] Kullanmak için bir alternatif kayıt defteri kök. Kümesine `NULL` varsayılan değer kullanılacak.|  
  
## <a name="expression-evaluator-functions"></a>İfade değerlendirici işlevleri  
  
|İşlev|Açıklama|  
|--------------|-----------------|  
|GetEEMetric|Bir ölçü değeri kayıt defterinden alır.|  
|SetEEMetric|Kayıt defterinde belirtilen ölçüm değeri ayarlar.|  
|RemoveEEMetric|Belirtilen Ölçüm kayıt defterinden kaldırır.|  
|GetEEMetricFile|Belirtilen Ölçüm dosya adını alır ve dosya içeriğini bir dize olarak döndüren yükler.|  
  
## <a name="exception-functions"></a>Özel durum işlevleri  
  
|İşlev|Açıklama|  
|--------------|-----------------|  
|GetExceptionMetric|Bir ölçü değeri kayıt defterinden alır.|  
|SetExceptionMetric|Kayıt defterinde belirtilen ölçüm değeri ayarlar.|  
|RemoveExceptionMetric|Belirtilen Ölçüm kayıt defterinden kaldırır.|  
|RemoveAllExceptionMetrics|Tüm özel durum ölçümleri kayıt defterinden kaldırır.|  
  
## <a name="symbol-provider-functions"></a>Sembol sağlayıcısı işlevleri  
  
|İşlev|Açıklama|  
|--------------|-----------------|  
|GetSPMetric|Bir ölçü değeri kayıt defterinden alır.|  
|SetSPMetric|Kayıt defterinde belirtilen ölçüm değeri ayarlar.|  
|RemoveSPMetric|Belirtilen Ölçüm kayıt defterinden kaldırır.|  
  
## <a name="enumeration-functions"></a>Numaralandırma işlevleri  
  
|İşlev|Açıklama|  
|--------------|-----------------|  
|EnumMetricSections|Belirtilen bir ölçüm türü için tüm ölçümleri numaralandırır.|  
|EnumDebugEngine|Kayıtlı hata ayıklama motorları numaralandırır.|  
|EnumEEs|Kayıtlı ifade değerlendiricisi numaralandırır.|  
|EnumExceptionMetrics|Tüm özel durum ölçümleri numaralandırır.|  
  
## <a name="metric-definitions"></a>Ölçüm tanımları  
 Bu tanımları için önceden tanımlanmış ölçüm adları kullanılabilir. Çeşitli kayıt defteri anahtarları ve değer adlarını ve geniş karakter dizeleri olarak tanımlanmış olan tüm adları karşılık gelen: Örneğin, `extern LPCWSTR metrictypeEngine`.  
  
|Önceden tanımlanmış ölçüm türleri|Açıklama: Temel anahtar için...|  
|-----------------------------|---------------------------------------|  
|metrictypeEngine|Tüm altyapısı ölçümleri hata ayıklama.|  
|metrictypePortSupplier|Tüm bağlantı noktası tedarikçi ölçümleri.|  
|metrictypeException|Tüm özel durumu ölçümleri.|  
|metricttypeEEExtension|Tüm ifade değerlendiricisi uzantıları.|  
  
|Altyapı özelliklerini hata ayıklama|Açıklama|  
|-----------------------------|-----------------|  
|metricAddressBP|Adres kesme noktaları desteği belirtmek için sıfır olarak ayarlayın.|  
|metricAlwaysLoadLocal|Her zaman yerel olarak hata ayıklama altyapısı yüklemek için sıfır olarak ayarlayın.|  
|metricLoadInDebuggeeSession|KULLANILMIYOR|  
|metricLoadedByDebuggee|Hata ayıklama altyapısı her zaman ile veya ayıklanacak program tarafından yüklenecek olduğunu belirtmek için sıfır olarak ayarlayın.|  
|metricAttach|Varolan programlara ek desteği belirtmek için sıfır olarak ayarlayın.|  
|metricCallStackBP|Çağrı yığını kesme noktaları desteği belirtmek için sıfır olarak ayarlayın.|  
|metricConditionalBP|Koşullu kesme noktaları ayarı için destek belirtmek için sıfır olarak ayarlayın.|  
|metricDataBP|Kesme noktaları verilerde yapılan değişiklikler üzerinde ayarı için destek belirtmek için sıfır olarak ayarlayın.|  
|metricDisassembly|Ayrıştırılmış listesini üretim desteği belirtmek için sıfır olarak ayarlayın.|  
|metricDumpWriting|(Bir çıktı aygıtının bellek dökümü alma) yazma döküm desteği belirtmek için sıfır olarak ayarlayın.|  
|metricENC|Düzenle ve devam et için destek belirtmek için sıfır olarak ayarlayın. **Not:** bir özel hata ayıklama altyapısı hiçbir zaman bu ayarlamanız gerekir ya da her zaman 0 olarak ayarlamanız gerekir.|  
|metricExceptions|Özel durumlar için destek belirtmek için sıfır olarak ayarlayın.|  
|metricFunctionBP|Adlandırılmış kesme noktaları (belirli bir işlev adı çağrıldığında bölün kesme) desteği belirtmek için sıfır olarak ayarlayın.|  
|metricHitCountBP|Kesme noktaları (yalnızca olan belirli kaç kez isabet sonra tetiklenen kesme noktaları) "noktası isabet" ayarı için destek belirtmek için sıfır olarak ayarlayın.|  
|metricJITDebug|(Bir çalışan işlem olarak bir özel durum oluştuğunda hata ayıklayıcı başlatıldığında) tam zamanında hata ayıklama desteği belirtmek için sıfır olarak ayarlayın.|  
|metricMemory|KULLANILMIYOR|  
|metricPortSupplier|Bir uygulanırsa, bu bağlantı noktası tedarikçi CLSID değerine ayarlayın.|  
|metricRegisters|KULLANILMIYOR|  
|metricSetNextStatement|(Hangi Ara deyimleri yürütülmesi atlar) next deyimi ayarlamak için destek belirtmek için sıfır olarak ayarlayın.|  
|metricSuspendThread|İş parçacığı yürütmesi askıya almak için destek belirtmek için sıfır olarak ayarlayın.|  
|metricWarnIfNoSymbols|Simge varsa kullanıcının bildirilmesi gerektiğini belirtmek için sıfır olarak ayarlayın.|  
|metricProgramProvider|Bu program sağlayıcısı CLSID değerine ayarlayın.|  
|metricAlwaysLoadProgramProviderLocal|Bu program sağlayıcısı her zaman yerel olarak yüklenmiş olması gerektiğini belirtmek için sıfır olarak ayarlayın.|  
|metricEngineCanWatchProcess|Bu program sağlayıcısı yerine olayları işlemek için hata ayıklama altyapısı izleneceği olduğunu belirtmek için sıfır olarak ayarlayın.|  
|metricRemoteDebugging|Bu uzaktan hata ayıklama desteği belirtmek için sıfır olarak ayarlayın.|  
|metricEncUseNativeBuilder|Düzenle ve devam Yöneticisi hata ayıklama altyapının encbuild.dll Düzenle ve devam et için oluşturmak için kullanması gerektiğini belirtmek için sıfır olmayan ayarlayın. **Not:** bir özel hata ayıklama altyapısı hiçbir zaman bu ayarlamanız gerekir ya da her zaman 0 olarak ayarlamanız gerekir.|  
|metricLoadUnderWOW64|Bu hata ayıklama altyapısı WOW altında ayıklayıcı işleminde 64 bitlik bir işlem hata ayıklama sırasında yüklenmesi gereken olduğunu belirtmek için sıfır olmayan ayarlayın; Aksi takdirde hata ayıklama altyapısı (WOW64 altında çalışan) Visual Studio işlemi yüklenir.|  
|metricLoadProgramProviderUnderWOW64|Bu program sağlayıcısı WOW altında 64 bitlik bir işlem hata ayıklama sırasında ayıklayıcı işleminde yüklenmesi gerektiğini belirtmek için sıfır olmayan ayarlayın; Aksi takdirde Visual Studio işleminde yüklenecektir.|  
|metricStopOnExceptionCrossingManagedBoundary|Bu işlemi işlenmeyen bir özel durum kodu yönetilen ve yönetilmeyen sınırlarında oluşturulursa durması gerektiğini belirtmek için sıfır olarak ayarlayın.|  
|metricAutoSelectPriority|Hata ayıklama altyapısı (yüksek değerleri eşittir daha yüksek öncelik) otomatik seçimi için bir öncelik için bunu ayarlayın.|  
|metricAutoSelectIncompatibleList|Otomatik seçiminde hata ayıklama motorları GUID'lerini yok sayılacak belirtin girişleri içeren kayıt defteri anahtarı. Bu girişler bir sayı (0, 1, 2 vb.) içeren bir dize olarak ifade edilen bir GUID.|  
|metricIncompatibleList|Bu hata ayıklama altyapısı ile uyumlu olmayan hata ayıklama motorları GUID'ler belirtme girişleri içeren kayıt defteri anahtarı.|  
|metricDisableJITOptimization|Bu yalnızca zaman iyileştirmeler (yönetilen kod için) hata ayıklama sırasında devre dışı bırakılmalıdır olduğunu belirtmek için sıfır olarak ayarlayın.|  
  
|İfade değerlendirici özellikleri|Açıklama|  
|-------------------------------------|-----------------|  
|metricEngine|Belirtilen ifade değerlendiricisi destek hata ayıklama altyapısı sayısı tutar.|  
|metricPreloadModules|Bu program karşı bir ifade değerlendiricisi başlatıldığında modülleri yüklenmiş olduğunu belirtmek için sıfır olarak ayarlayın.|  
|metricThisObjectName|"Bu" nesne adını ayarlayın.|  
  
|İfade değerlendirici uzantısı özellikleri|Açıklama|  
|-----------------------------------------------|-----------------|  
|metricExtensionDll|Bu uzantı destekleyen dll adı.|  
|metricExtensionRegistersSupported|Desteklenen kayıtları listesi.|  
|metricExtensionRegistersEntryPoint|Yazmaçları erişmek için giriş noktası.|  
|metricExtensionTypesSupported|Desteklenen türleri listesi.|  
|metricExtensionTypesEntryPoint|Türleri erişmek için giriş noktası.|  
  
|Bağlantı noktası tedarikçi özellikleri|Açıklama|  
|------------------------------|-----------------|  
|metricPortPickerCLSID|(Bir iletişim kutusu kullanıcı bağlantı noktalarını seçin ve hata ayıklama için kullanılacak bağlantı noktası eklemek için kullanabilirsiniz) bağlantı noktası Seçici CLSID.|  
|metricDisallowUserEnteredPorts|Kullanıcı tarafından girilen bağlantı noktaları için bağlantı noktası tedarikçi eklediyseniz sıfır olmayan (Bu bağlantı noktası Seçici iletişim kutusu temelde salt okunur yapar).|  
|metricPidBase|İşlem kimliklerini ayırırken bağlantı noktası sağlayıcı tarafından kullanılan ana işlem kimliği.|  
  
|Önceden tanımlanmış SP depolama türleri|Açıklama|  
|-------------------------------|-----------------|  
|storetypeFile|Simgeler ayrı bir dosyada depolanır.|  
|storetypeMetadata|Simgeler derlemedeki meta veri olarak depolanır.|  
  
|Çeşitli özellikler|Açıklama|  
|------------------------------|-----------------|  
|metricShowNonUserCode|Bu nonuser kodu göstermek için sıfır olarak ayarlayın.|  
|metricJustMyCodeStepping|Bu atlama yalnızca kullanıcı kodunda oluşabilir belirtmek için sıfır olarak ayarlayın.|  
|metricCLSID|Belirli bir ölçüm türünde bir nesne için CLSID.|  
|metricName|Belirli bir ölçüm türünde bir nesne için kolay ad.|  
|metricLanguage|Dil adı.|  
  
## <a name="registry-locations"></a>Kayıt defteri konumları  
 Ölçümleri okuma ve kayıt defterine özel olarak yazılmış `VisualStudio` alt anahtarı.  
  
> [!NOTE]
>  Çoğu zaman, ölçümleri HKEY_LOCAL_MACHINE anahtarına yazılır. Ancak, bazen HKEY_CURRENT_USER hedef anahtar olacaktır. Her iki anahtarı Dbgmetric.lib işler. Ölçüm alırken HKEY_CURRENT_USER arar ilk sonra HKEY_LOCAL_MACHINE. Ölçüm ayarı, bir parametre kullanmak için hangi en üst düzey anahtarını belirtir.  
  
 *[kayıt defteri anahtarı]*\  
  
 `Software`\  
  
 `Microsoft`\  
  
 `VisualStudio`\  
  
 *[sürüm kök]*\  
  
 *[ölçüm kök]*\  
  
 *[ölçü türü]*\  
  
 *[ölçü] = [ölçüm değeri]*  
  
 *[ölçü] = [ölçüm değeri]*  
  
 *[ölçü] = [ölçüm değeri]*  
  
|Yer tutucu|Açıklama|  
|-----------------|-----------------|  
|*[kayıt defteri anahtarı]*|`HKEY_CURRENT_USER`veya `HKEY_LOCAL_MACHINE`.|  
|*[sürüm kök]*|Visual Studio sürümünü (örneğin, `7.0`, `7.1`, veya `8.0`). Ancak, bu kök ayrıca kullanılarak değiştirilebilir **/rootsuffix** geçiş **devenv.exe**. Bu değiştirici VSIP için genelde olduğu **Exp**, sürüm kök, örneğin, 8.0Exp durumda olacaktır.|  
|*[ölçüm kök]*|Ya da budur `AD7Metrics` veya `AD7Metrics(Debug)`dbgmetric.lib hata ayıklama sürümü kullanılıp kullanılmadığını bağlı olarak. **Not:** dbgmetric.lib kullanılan olsun veya olmasın, hata ayıklama ve yayın arasındaki farklar varsa bu adlandırma kuralını için bağlı kayıt defterinde yansıtılan sürümleri.|  
|*[ölçü türü]*|Yazılacak ölçüm türü: `Engine`, `ExpressionEvaluator`, `SymbolProvider`vb.. Bunlar tüm dbgmetric.h olduğu gibi tanımlanır `metricTypeXXXX`, burada `XXXX` belirli tür adı.|  
|*[ölçü]*|Ölçüm ayarlamak için bir değer atanması bir giriş adı. Ölçümleri gerçek organizasyonu Ölçüm türüne bağlıdır.|  
|*[ölçü değeri]*|Ölçüm için atanan değer. (String, sayı, vb.) bir değere sahip olmalıdır üzerinde Ölçüm türüne bağlıdır.|  
  
> [!NOTE]
>  Tüm GUID biçiminde depolanır `{GUID}`. Örneğin, `{123D150B-FA18-461C-B218-45B3E4589F9B}`.  
  
### <a name="debug-engines"></a>Motorları hata ayıklama  
 Hata ayıklama motorları ölçümleri kayıt defterinde organizasyonu verilmiştir. `Engine`hata ayıklama altyapısı için ölçüm türü adıdır ve karşılık gelen *[ölçüm türü]* yukarıdaki kayıt defteri alt ağaçta.  
  
 `Engine`\  
  
 *[altyapısı GUID]*\  
  
 `CLSID` = *[sınıfı GUID]*  
  
 *[ölçü] = [ölçüm değeri]*  
  
 *[ölçü] = [ölçüm değeri]*  
  
 *[ölçü] = [ölçüm değeri]*  
  
 `PortSupplier`\  
  
 `0` = *[bağlantı noktası tedarikçi GUID]*  
  
 `1` = *[bağlantı noktası tedarikçi GUID]*  
  
|Yer tutucu|Açıklama|  
|-----------------|-----------------|  
|*[altyapısı GUID]*|Hata ayıklama altyapısı GUID.|  
|*[sınıfı GUID]*|Bu hata ayıklama altyapısı uygulayan sınıf GUID.|  
|*[bağlantı noktası tedarikçi GUID]*|Varsa, bağlantı noktası tedarikçi GUID. Birçok hata ayıklama motorları varsayılan bağlantı noktası tedarikçi kullanın ve bu nedenle, kendi tedarikçi belirtmeyin. Bu durumda, alt `PortSupplier` mevcut olacaktır.|  
  
### <a name="port-suppliers"></a>Bağlantı noktası Üreticiler  
 Kayıt defterindeki bağlantı noktası tedarikçi ölçümleri organizasyonu verilmiştir. `PortSupplier`bir bağlantı noktası tedarikçi ölçüm türü adı ve karşılık gelen *[ölçüm türü]*.  
  
 `PortSupplier`\  
  
 *[bağlantı noktası tedarikçi GUID]*\  
  
 `CLSID` = *[sınıfı GUID]*  
  
 *[ölçü] = [ölçüm değeri]*  
  
 *[ölçü] = [ölçüm değeri]*  
  
|Yer tutucu|Açıklama|  
|-----------------|-----------------|  
|*[bağlantı noktası tedarikçi GUID]*|Bağlantı noktası tedarikçi GUID|  
|*[sınıfı GUID]*|Bu bağlantı noktası sağlayıcı uygulayan sınıf GUID|  
  
### <a name="symbol-providers"></a>Sembol sağlayıcıları  
 Kayıt defterinde simgesi tedarikçi ölçümleri organizasyonu verilmiştir. `SymbolProvider`Ölçüm türü simgesi sağlayıcısının adıdır ve karşılık gelen *[ölçüm türü]*.  
  
 `SymbolProvider`\  
  
 *[simge sağlayıcı GUID]*\  
  
 `file`\  
  
 `CLSID` = *[sınıfı GUID]*  
  
 *[ölçü] = [ölçüm değeri]*  
  
 *[ölçü] = [ölçüm değeri]*  
  
 `metadata`\  
  
 `CLSID` = *[sınıfı GUID]*  
  
 *[ölçü] = [ölçüm değeri]*  
  
 *[ölçü] = [ölçüm değeri]*  
  
|Yer tutucu|Açıklama|  
|-----------------|-----------------|  
|*[simge sağlayıcı GUID]*|Sembol sağlayıcı GUID|  
|*[sınıfı GUID]*|Bu simge sağlayıcı uygulayan sınıf GUID|  
  
### <a name="expression-evaluators"></a>İfade Değerlendiricileri  
 İfade değerlendirici ölçümleri kayıt defterinde organizasyonu verilmiştir. `ExpressionEvaluator`İfade değerlendirme için ölçüm türü adıdır ve karşılık gelen *[ölçüm türü]*.  
  
> [!NOTE]
>  Ölçü türü için `ExpressionEvaluator` ifade değerlendiricisi için tüm ölçüm değişiklikleri aracılığıyla uygun ifade değerlendiricisi ölçüm işlevleri gidecek varsayılır gibi dbgmetric.h içinde tanımlı değil (düzenini `ExpressionEvaluator` alt biraz anahtarıdır Ayrıntılar dbgmetric.lib içinde gizlenir şekilde, karmaşık).  
  
 `ExpressionEvaluator`\  
  
 *[dil GUID]*\  
  
 *[satıcı GUID]*\  
  
 `CLSID` = *[sınıfı GUID]*  
  
 *[ölçü] = [ölçüm değeri]*  
  
 *[ölçü] = [ölçüm değeri]*  
  
 `Engine`\  
  
 `0` = *[altyapısı GUID hata ayıklama]*  
  
 `1` = *[altyapısı GUID hata ayıklama]*  
  
|Yer tutucu|Açıklama|  
|-----------------|-----------------|  
|*[dil GUID]*|Bir dil GUID|  
|*[satıcı GUID]*|Bir satıcı GUID|  
|*[sınıfı GUID]*|Bu ifade değerlendiricisi uygulayan sınıf GUID|  
|*[altyapısı GUID hata ayıklama]*|Bu ifade değerlendiricisi çalışır bir hata ayıklama altyapısı GUID|  
  
### <a name="expression-evaluator-extensions"></a>İfade değerlendirici uzantıları  
 İfade değerlendirici uzantısı ölçümleri kayıt defterinde organizasyonu verilmiştir. `EEExtensions`Ölçüm türü ifade değerlendiricisi uzantıları adıdır ve karşılık gelen *[ölçüm türü]*.  
  
 `EEExtensions`\  
  
 *[uzantısı GUID]*\  
  
 *[ölçü] = [ölçüm değeri]*  
  
 *[ölçü] = [ölçüm değeri]*  
  
|Yer tutucu|Açıklama|  
|-----------------|-----------------|  
|*[uzantısı GUID]*|İfade değerlendirici uzantı GUID|  
  
### <a name="exceptions"></a>Özel Durumlar  
 Kayıt defterinde özel durumlar ölçümleri organizasyonu verilmiştir. `Exception`özel durumlar için ölçüm tür adı ve karşılık gelen *[ölçüm türü]*.  
  
 `Exception`\  
  
 *[altyapısı GUID hata ayıklama]*\  
  
 *[özel durum türleri]*\  
  
 *[özel durum]*\  
  
 *[ölçü] = [ölçüm değeri]*  
  
 *[ölçü] = [ölçüm değeri]*  
  
 *[özel durum]*\  
  
 *[ölçü] = [ölçüm değeri]*  
  
 *[ölçü] = [ölçüm değeri]*  
  
|Yer tutucu|Açıklama|  
|-----------------|-----------------|  
|*[altyapısı GUID hata ayıklama]*|Özel durumlar destekleyen bir hata ayıklama altyapısı GUID.|  
|*[özel durum türleri]*|İşlenebilir özel durum sınıfı tanımlayan alt için genel bir başlık. Tipik adları **C++ özel durumlarını**, **Win32 özel durum**, **ortak dil çalışma zamanı özel durumları**, ve **yerel çalışma zamanı denetler**. Bu adları, ayrıca kullanıcıya özel durumu, belirli bir sınıfın tanımlamak için kullanılır.|  
|*[özel durum]*|Bir özel durum için bir ad: Örneğin, **_com_error** veya **Control-Break**. Bu adları, ayrıca kullanıcının belirli bir özel durum tanımlamak için kullanılır.|  
  
## <a name="requirements"></a>Gereksinimler  
 Bu dosyalar bulunur [!INCLUDE[vs_dev10_ext](../../../extensibility/debugger/reference/includes/vs_dev10_ext_md.md)] SDK yükleme dizini (varsayılan olarak, *[sürücü]*\Program Visual Studio 2010 SDK\\).  
  
 Başlık: includes\dbgmetric.h  
  
 Kitaplığı: libs\ad2de.lib, libs\dbgmetric.lib  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [API Başvurusu](../../../extensibility/debugger/reference/api-reference-visual-studio-debugging.md)