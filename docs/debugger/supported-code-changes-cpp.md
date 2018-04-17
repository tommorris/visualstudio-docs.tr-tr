---
title: Desteklenen kod değişiklikleri (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue, limitations
- supported code changes
- object files, limitations of Edit and Continue
- C# language, supported code changes
- coding, supported code changes
- resource files, limitations of Edit and Continue
- code changes, handling in Edit and Continue
- what's new [C#], supported code changes
- code changes
ms.assetid: f5754363-8a56-417b-b904-b05d9dd26d03
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 8752cb6574a514baa121de744e381e7e37041f11
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="supported-code-changes-c"></a>Desteklenen Kod Değişiklikleri (C++)
Düzenle ve devam et Visual C++ için kod değişiklikleri çoğu türlerini işler. Ancak, program yürütme sırasında bazı değişiklikler uygulanamıyor. Bu değişiklikleri uygulamak için yürütme durdurun ve kod yeni bir sürümünü oluşturabilir.  
  
 Bkz: [Düzenle ve devam et (Visual C++)](../debugger/edit-and-continue-visual-cpp.md) Visual Studio'da c++ Düzenle ve devam et ile çalışma hakkında bilgi.  
  
##  <a name="BKMK_Unsupported_changes"></a> Desteklenmeyen değişiklikler  
 Aşağıdaki C/C++ değişiklikleri hata ayıklama oturumu sırasında uygulanamaz:  
  
-   Genel veya statik verileri çoğu geçer.  
  
-   Başka bir makineden kopyalanan ve yerel olarak oluşturulmuş olmayan yürütülebilir dosyalar yapılan değişiklikler.  
  
-   Veri üyeleri sınıfın gibi bir nesne düzenini etkileyen değişiklikler için bir veri türü.  
  
-   Yeni kod ya da veri fazla 64 k bayt ekleniyor.  
  
-   Yönerge işaretçisi önce bir noktada bir oluşturucu gerektiren değişkenleri ekleniyor.  
  
-   Çalışma zamanı başlatma gerektiren kod etkileyen değişiklikler.  
  
-   Özel durum işleyicileri, bazı durumlarda ekleniyor.  
  
-   Kaynak dosyalardaki değişiklikler.  
  
-   Salt okunur dosyalar kodunda yapılan değişiklikler.  
  
-   Karşılık gelen PDB dosyası olmadan kod yapılan değişiklikler.  
  
-   Hiçbir nesne dosyasına sahip code yapılan değişiklikler.  
  
 Kod değişikliklerini uygulamayı deneyin ve bu değişikliklerden birini olun, bir hata veya uyarı iletisi görünür **çıkış** penceresi.  
  
-   Düzenle ve devam et, statik kitaplıklar güncelleştirmez. Statik kitaplığa değişiklik yaparsanız, eski sürüm ile yürütme devam eder ve herhangi bir uyarı verilir.  
  
##  <a name="BKMK_Unsupported_scenarios"></a> Desteklenmeyen senaryolar  
 Düzenle ve devam et C/C++ için aşağıdaki hata ayıklama senaryolarında kullanılamaz:  
  
-   Hata ayıklama ile derlenmiş yerel uygulamaları [/Zo (geliştirmek en iyi duruma getirilmiş hata ayıklama)](/cpp/build/reference/zo-enhance-optimized-debugging)  
  
-   Visual Studio 2015 güncelleştirme UWP uygulamaları veya bileşenleri hata ayıklama 1, Geri'yi Visual Studio sürümlerinde. Şimdi desteklediği için Visual Studio 2015 güncelleştirme 1'de başlayarak, Düzenle ve devam et UWP C++ uygulamalar ve DirectX uygulamalar kullanabileceğiniz `/ZI` derleyici anahtarıyla `/bigobj` geçin. Düzen de kullanabilirsiniz ve devam ikililerini derlenmiş ile `/FASTLINK` geçin.  
  
-   Windows 98 hata ayıklama.  
  
-   Karışık mod (yerel/yönetilen) hata ayıklama.  
  
-   JavaScript hata ayıklama.  
  
-   SQL hata ayıklama.  
  
-   Hata ayıklama döküm dosyası.  
  
-   İşlenmeyen bir özel durumdan sonra kod düzenleme zaman **işlenmeyen özel durum çağrı yığınındaki bırakma** seçeneği seçili değil.  
  
-   Bir uygulama kullanarak hata ayıklama **ekleme** seçerek uygulama çalıştırmak yerine **Başlat** üzerinde **hata ayıklama** menüsü.  
  
-   İyileştirilmiş kodda hata ayıklama.  
  
-   Derleme hataları nedeniyle oluşturmak yeni bir sürüm başarısız olduktan sonra kodunuzu eski bir sürümü hata ayıklama.  
  
##  <a name="BKMK_Linking_limitations"></a> Bağlama kısıtlamaları  
  
###  <a name="BKMK_Linker_options_that_disable_Edit_and_Continue"></a> Düzenle ve devam et devre dışı bağlayıcı seçenekleri  
 Aşağıdaki bağlayıcı seçeneklerini Düzenle ve devam et devre dışı bırakın:  
  
-   Ayarı **/OPT:REF**, **/OPT:ICF**, veya **/INCREMENTAL:NO** devre dışı bırakır Düzenle ve devam et, şu uyarıyı vererek:  
  
     BAĞLANTI: Uyarısı LNK4075: /EDITANDCONTINUE OPT nedeniyle yoksayılıyor  
  
     belirtim  
  
-   Ayarı **/sipariş**, **/RELEASE**, veya **/FORCE** devre dışı bırakır Düzenle ve devam et, bu uyarı ile:  
  
     BAĞLANTI: Uyarısı LNK4075: /INCREMENTAL/OPTION nedeniyle yoksayılıyor  
  
     belirtim  
  
-   Herhangi bir seçenek ayarı devre dışı bırakır düzenleyebilir ve belirli bir uyarı ile devam program veritabanı (.pdb) dosyası oluşturulmasını engeller.  
  
###  <a name="BKMK_Auto_relinking_limitations"></a> Otomatik sınırlamaları yeniden bağlantılandırma  
 Varsayılan olarak, Düzenle ve devam et i programınızı güncel yürütülebilir bir dosya oluşturmak için bir hata ayıklama oturumu sonunda.  
  
 Bu özgün yapı konumu dışında bir konumdan ayıkladığınız varsa Düzenle ve devam et programınızı yeniden olamaz. Bir ileti el ile yeniden gerektiğini bildirir.  
  
 Düzenle ve devam et değil yeniden statik kitaplıklar. Düzenle ve devam et kullanarak bir statik kitaplık değişiklik yaparsanız, el ile onu kullanarak kitaplık ve yeniden bağlama uygulamaları yeniden yapılandırmanız gerekir.  
  
 Düzenle ve devam et çağrılamadı özel derleme adımları. Özel derleme adımları programınızı kullanıyorsa, böylece özel derleme adımları çağrılabilir el ile yeniden oluşturmak isteyebilirsiniz. Durumda, emin olmak için Düzenle ve devam et sonra yeniden bağlama devre dışı bırakabilirsiniz, el ile yeniden başlatmanız istenir.  
  
 **Düzenle ve devam et sonra yeniden bağlama devre dışı bırakmak için**  
  
1.  Üzerinde **hata ayıklama** menüsünde seçin **seçenekleri ve ayarları**.  
  
2.  İçinde **seçenekleri** iletişim kutusunda **hata ayıklama** düğümü ve select **Düzenle ve devam et** düğümü.  
  
3.  Clear **hata ayıklama sonra yeniden Bağla kod değişiklikleri** onay kutusu.  
  
##  <a name="BKMK_Precompiled_Header_Limitations"></a> Önceden derlenmiş üst bilgi sınırlamaları  
 Varsayılan olarak, Düzenle ve yükler ve işlemleri önceden derlenmiş üstbilgiler kod değişiklikleri işlemleri hızlandırmak için arka planda devam et. Önceden derlenmiş üst bilgiler yüklenirken bir sorun sınırlı RAM'i olan bir makinede derlediğiniz varsa olabilen fiziksel bellek ayırma gerektirir. Bu bir sorun hata ayıklarken kullanılabilir fiziksel bellek miktarını belirlemek için Windows Görev Yöneticisi'ni kullanarak olabilir, belirleyebilirsiniz. Bu miktar, önceden derlenmiş üstbilgi boyutu büyükse, Düzenle ve devam et hiçbir sorun olmalıdır. Tutar, önceden derlenmiş üst bilgilerin boyuttan daha az ise, önceden derlenmiş üstbilgi arka planda yüklenmesini Düzenle ve devam et engelleyebilir.  
  
 **Düzenle ve devam et için önceden derlenmiş üst bilgilerin arka planda yükleme devre dışı bırakmak için**  
  
1.  Üzerinde **hata ayıklama** menüsünde seçin **seçenekleri ve ayarları**.  
  
2.  İçinde **seçenekleri** iletişim kutusunda **hata ayıklama** düğümü ve select **Düzenle ve devam et** düğümü.  
  
3.  Clear **izin önceden derleme** onay kutusu.  
  
##  <a name="BKMK_IDL_Attribute_Limitations"></a> IDL özniteliği sınırlamaları  
 Düzenle ve devam et değil yeniden arabirim tanımı (IDL) dosyaları. Bu nedenle, hata ayıklarken IDL özniteliklere yapılan değişiklikleri yansıtılmaz. IDL öznitelikleri değişiklikler sonuçlarını görmek için hata ayıklamayı durdurun ve uygulamanızı yeniden oluşturun. Düzenle ve devam et oluşturmaz bir hata veya uyarı IDL öznitelikleri değiştirdiyseniz. Daha fazla bilgi için bkz: [IDL öznitelikleri](/cpp/windows/idl-attributes).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Düzenle ve Devam Et (Visual C++)](../debugger/edit-and-continue-visual-cpp.md)