---
title: "Seçenekler sayfası, hata ayıklama düğümü özellikleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 564cc8b2-0084-420e-b560-200cc5621a7e
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 9d53460304cee56d39100a82a2e1e975f8129aa6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="options-page-debugging-node-properties"></a>Seçenekler Sayfası, Hata Ayıklama Düğümü Özellikleri
Aşağıdaki tablolar sayfaları (veya özellikleri koleksiyonları) açıklamaktadır ile ilişkili **hata ayıklama** kategorisi, `DTE.Properties("Debugging", <Property Page>)` , **seçenekleri** iletişim kutusu.  
  
## <a name="general"></a>Genel  
 `DTE.Properties("Debugging", "General")`  
  
|Özellik Öğesi Adı|Değer|Açıklama|  
|------------------------|-----------|-----------------|  
|PromptOnBreakpointDelete|Get/Set (Boole)|Hata ayıklayıcı projesindeki tüm kesme noktaları silmeden önce izin ister olup olmadığını belirler.|  
|BreakAllProcesses|Get/Set (Boole)|Tek bir işlem keser her hata ayıklayıcı tüm işlemler keser olup olmadığını belirler.|  
|BreakAtBoundaries|Get/Set (Boole)|Hata ayıklayıcı bir özel durum kenarlık uygulama etki alanları arasında kestiği zaman yürütme keser veya arasında yönetilen ve yerel kodu belirler.|  
|EnableAddressLevelDebugging|Get/Set (Boole)|Adres düzeyi hata ayıklama özelliği etkinleştirilmiş olup olmadığını belirler.|  
|ShowDisassemblyIfNoSource|Get/Set (Boole)|Hata ayıklayıcı kaynak kodu kullanılabilir olmadığında Ayrıştırılmış kod görüntülenip görüntülenmeyeceğini belirler.|  
|EnableBreakpointFilters|Get/Set (Boole)|Kesme noktası filtrelemesinin etkinleştirilip etkinleştirilmeyeceğini belirler.|  
|EnableExceptionAssistant|Get/Set (Boole)|Özel durum Yardımcısı'nı yönetilen özel durumlar için kullanılıp kullanılmayacağını belirler.|  
|UnwindCallstack|Get/Set (Boole)|Hata ayıklayıcı işlenmeyen bir özel durum çağrı yığını unwinds olup olmadığını belirler.|  
|EnableJustMyCode|Get/Set (Boole)|Sadece kendi kodumu için C# ve Visual Basic kodu için etkin olup olmadığını belirler.|  
|ShowAllMembers|Get/Set (Boole)|Kullanıcı olmayan nesneler için hata ayıklayıcı değişkenleri windows tüm nesne üyeleri görüntülenip görüntülenmeyeceğini belirler. Sadece kendi kodumu etkinleştirilmediği sürece bu seçeneğin bir etkisi yoktur.|  
|WarnIfNoUserCode|Get/Set (Boole)|Kullanıcı hiçbir kullanıcı koduna sahip bir işlem ekleme yapmaya çalıştığında hata ayıklayıcı bir uyarı yayar olup olmadığını belirler. Sadece kendi kodumu etkinleştirilmediği sürece bu seçeneğin bir etkisi yoktur.|  
|EnablePropertyEvaluation|Get/Set (Boole)|Hata ayıklayıcı özellikleri otomatik olarak değerlendirir ve yönetilen kodda dolaylı işlevi çağırır olup olmadığını belirler.|  
|CallStringConversion|Get/Set (Boole)|Hata ayıklayıcı örtük olarak bir dize dönüştürme işlevi değişkenleri Windows nesnelerde çağırır olup olmadığını belirler. Bu seçenek yalnızca C# ve JScript kodu için geçerlidir.|  
|EnableSourceServer|Get/Set (Boole)|Hata ayıklayıcı sıfırlayamayacağını erişim kodu bir kaynak sunucudan belirler.|  
|PrintSourceServerDiagnostics|Get/Set (Boole)|Çıktı penceresi kaynak sunucu ile ilgili tanılama iletileri gösterir olup olmadığını belirler. Kaynak sunucu erişimi etkinleştirilmediği sürece bu seçeneğin bir etkisi yoktur.|  
|HighlightEntireLine|Get/Set (Boole)|Hata ayıklayıcı kesme noktaları ve geçerli deyim için tam bir satırın vurgular olup olmadığını belirler.|  
|RequireSourceToMatch|Get/Set (Boole)|Hata ayıklayıcı kaynak dosyalarının hata ayıklama dosyalarını açtığınızda özgün sürümü tam olarak eşleştiğinden gerekli olup olmadığını belirler.|  
|RedirectOutputToImmediate|Get/Set (Boole)|Çıktı penceresi çıkışını komut penceresi yeniden yönlendirilen olup olmadığını belirler.|  
|ShowRawVariableStructure|Get/Set (Boole)|Nesne değişkenleri Windows ham biçiminde gösterilip gösterilmeyeceğini belirler.|  
|SuppressJitOptimization|Get/Set (Boole)|Yönetilen kod için tam zamanı en iyi duruma getirme hata ayıklayıcı tarafından gizlenen olup olmadığını belirler.|  
|WarnIfNoSymbols|Get/Set (Boole)|Hata ayıklayıcı işlem başlatıldığında hiçbir hata ayıklama simgeleri varsa bir uyarı görüntüler olup olmadığını belirler.|  
|WarnIfScriptDisabled|Get/Set (Boole)|Hata ayıklayıcı işlem başlatıldığında komut dosyasında hata ayıklama etkin değilse bir uyarı görüntüler olup olmadığını belirler.|  
|ShowMarkersForAllThreads|Get/Set (Boole)|Hata ayıklayıcı iş parçacığı işaretçileri görüntülenip görüntülenmeyeceğini belirler.|  
|StepOverPropertiesAndOperators|Get/Set (Boole)|Özellikler ve yönetilen kodda işleçleri üzerinden adım belirtir.|  
  
## <a name="edit-and-continue"></a>Düzenle ve Devam Et  
 `DTE.Properties("Debugging", "EditAndContinue")`  
  
|Özellik Öğesi Adı|Değer|Açıklama|  
|------------------------|-----------|-----------------|  
|EnableEditAndContinue|Get/Set (Boole)|Düzenle ve devam et etkinleştirilip etkinleştirilmediğini belirler. Bu seçenek Düzenle ve devam et destekleyen tüm diller için geçerlidir.|  
|InvokedByCommands|Get/Set (Boole)|Düzenle ve devam et otomatik olarak geçerli olup olmadığını kod değişiklikleri kullanıcı bir hata ayıklama komutu gibi seçtiğinde belirler **adım** veya **devam**. Bu seçenek yalnızca yerel koda uygulanır.|  
|InvokedByCommandsAskFirst|Get/Set (Boole)|Düzenle ve devam et kullanıcı bir hata ayıklama komutu gibi seçtiğinde kod değişiklikleri uygulamak için kullanıcının izni uyarıp uyarmayacağını belirler **adım** veya **devam**. Bu seçenek yalnızca yerel koda uygulanır.|  
|WarnAboutStaleCode|Get/Set (Boole)|Düzenle ve devam et güncel ya da eski, kod yürütülmesine neden olur, hata ayıklayıcı bir uyarı iletisi sorunları olup olmadığını belirler. Bu seçenek yalnızca yerel koda uygulanır.|  
|RelinkChangesOnStop|Get/Set (kısa)|Visual Studio kod değişiklikleri uygulama yürütülmesi durdurulduğunda Düzenle ve devam et tarafından uygulanan i olup olmadığını belirler. Bu seçenek yalnızca yerel koda uygulanır.|  
|AllowPrecompiling|Get/Set (kısa)|Düzenle ve devam et verilir olup olmadığını önceden derlenmiş üstbilgi arka planda yükleme belirler. Bu seçenek yalnızca yerel koda uygulanır.|  
  
## <a name="just-in-time"></a>Tam Zamanında  
 `DTE.Properties("Debugging", "JustInTime")`  
  
|Özellik Öğesi Adı|Değer|Açıklama|  
|------------------------|-----------|-----------------|  
|JitManaged|Get/Set (Boole)|Yönetilen kod için Just-In-Time hata ayıklama etkin olup olmadığını belirler.|  
|JitNative|Get/Set (Boole)|Yerel kod için Just-In-Time hata ayıklama etkin olup olmadığını belirler.|  
|JitScript|Get/Set (Boole)|Just-In-Time hata ayıklama için komut dosyası kodu etkin olup olmadığını belirler.|  
  
## <a name="native"></a>Yerel  
 `DTE.Properties("Debugging", "Native")`  
  
|Özellik Öğesi Adı|Değer|Açıklama|  
|------------------------|-----------|-----------------|  
|LoadDllExports|Get/Set (Boole)|Hata ayıklayıcı DLL dışarı aktarma tabloları yükler olup olmadığını belirler.|  
|EnableRPC|Get/Set (Boole)|Hata ayıklayıcı COM uzaktan yordam çağrılarını adımlar olup olmadığını belirler.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Seçeneklerini denetleme](http://msdn.microsoft.com/Library/a09ed242-7494-4cde-bbd1-7a8ec617965d)   
 [Seçenekler sayfalarında özellik öğelerinin adlarını belirleme](http://msdn.microsoft.com/Library/d450422d-47c7-4eeb-9f9f-3286264bc5aa)   
 [Seçenekler sayfası, yazı tipleri ve renkler düğümü özellikleri](../../ide/reference/options-page-fonts-and-colors-node-properties.md)   
 [Seçenekler sayfası, metin düzenleyici düğümü özellikleri](../../ide/reference/options-page-text-editor-node-properties.md)   
 [Genel, hata ayıklama, Seçenekler iletişim kutusu](../../debugger/general-debugging-options-dialog-box.md)   
 [Düzenle ve devam et, hata ayıklama, Seçenekler iletişim kutusu](http://msdn.microsoft.com/Library/009d225f-ef65-463f-a146-e4c518f86103)   
 [Yalnızca hata ayıklama, zaman içinde Seçenekler iletişim kutusu](../../debugger/just-in-time-debugging-options-dialog-box.md)