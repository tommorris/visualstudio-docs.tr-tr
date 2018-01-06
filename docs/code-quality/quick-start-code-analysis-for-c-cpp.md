---
title: "Hızlı Başlangıç: C/C++ kod çözümleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- C/C++ code analysis
- code analysis,C/C++
ms.assetid: 6110b8ba-0af6-4acd-b1ba-bb0551f90e44
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5fe47a5e0bb2eb8c2002c8a516ef10aa81aa0e58
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="quick-start-code-analysis-for-cc"></a>Hızlı Başlangıç: C/C++ İçin Kod Çözümleme
Kod çözümleme düzenli olarak C veya C++ kodu çalıştırarak uygulamanızı kalitesini artırabilir. Bu ortak sorunları, iyi bir programlama uygulama ya da test aracılığıyla bulmak zordur kusurları ihlalleri bulmanıza yardımcı olabilir. Kod çözümleme geçerli olan, ancak hala siz veya kodunuzu kullanan diğer kişiler için sorunlarına neden olabilir belirli kod düzenleri arar çünkü kod analizi uyarıları derleyici hataları ve Uyarıları farklılık gösterir.  
  
## <a name="in-this-topic"></a>Bu konuda  
  
-   [Bir proje için kural kümeleri yapılandırma](../code-quality/quick-start-code-analysis-for-c-cpp.md#BKMK_ConfigureRuleSets)  
  
-   [Kod çözümleme çalıştırın](../code-quality/quick-start-code-analysis-for-c-cpp.md#BKMK_Run)  
  
-   [Çözümleme ve Kod Analizi uyarıları gidermek](../code-quality/quick-start-code-analysis-for-c-cpp.md#BKMK_Analyze)  
  
-   [Kod çözümleme uyarıları gizleme](../code-quality/quick-start-code-analysis-for-c-cpp.md#BKMK_Suppress)  
  
-   [İş öğeleri için kod çözümleme uyarıları oluşturma](../code-quality/quick-start-code-analysis-for-c-cpp.md#BKMK_Creating_work_items_for_code_analysis_warnings)  
  
-   [Arama ve kod çözümleme sonuçlarını filtreleme](../code-quality/quick-start-code-analysis-for-c-cpp.md#BKMK_Search)  
  
##  <a name="BKMK_ConfigureRuleSets"></a>Bir proje için kural kümeleri yapılandırma  
  
1.  İçinde **Çözüm Gezgini**, proje adı için kısayol menüsünü açın ve ardından **özellikleri**.  
  
2.  Aşağıdaki adımlar isteğe bağlıdır:  
  
    1.  İçinde **yapılandırma** ve **Platform** listeleri, derleme yapılandırmasını ve hedef platformu seçin.  
  
    2.  Varsayılan olarak, Kod Analizi uyarıları dış araçları tarafından otomatik olarak oluşturulan kodundan bildirmiyor. Oluşturulan kodundan uyarıları görüntülemek için temizleyin **bastırmak oluşturulan kod sonuçlarından** onay kutusu.  
  
        > [!NOTE]
        >  Hataları ve Uyarıları formlar ve şablonlar görüntülendiğinde bu seçenek kod çözümleme hataları ve Uyarıları oluşturulan kodundan engelleme. Hem görüntülemek ve bir form veya şablon için kaynak kodunu sağlayabilirsiniz.  
  
3.  Kod çözümleme proje seçilen yapılandırma kullanılarak oluşturulmuştur her zaman çalıştırmak için seçin **derlemede C/C++ için Kod Analizi etkinleştir** onay kutusu. Ayrıca Kod Analizi el ile açarak çalıştırabilirsiniz **Çözümle** menüsüne ve ardından seçme **çalıştırmak kod çözümleme** *ProjectName*.  
  
4.  İçinde **bu kural kümesini çalıştırmak** listesinde, aşağıdakilerden birini yapın:  
  
    -   Kullanmak istediğiniz kural kümesini seçin.  
  
    -   Seçin  **\<Gözat... >** var olan bir özel kural kümesini belirlemek için listede değil.  
  
    -   Özel bir kural kümesini tanımlar.  
  
         Daha fazla bilgi için bkz: [özel kural kümeleri oluşturma](../code-quality/creating-custom-code-analysis-rule-sets.md).  
  
### <a name="standard-cc-rule-sets"></a>Standart C/C++ kural kümeleri  
 Visual Studio iki standart yerel kod için kural kümesini içerir:  
  
|Kural kümesi|Açıklama|  
|--------------|-----------------|  
|Microsoft yerel Minimum kurallar önerilir|Bu kural kümesine olası güvenlik açıklarını ve uygulama çökme (Crash) dahil olmak üzere, yerel kodunuzda en kritik sorunlar odaklanır. Yerel projeleriniz için oluşturduğunuz herhangi bir özel kural kümesi içinde bu kural kümesi içermelidir.|  
|Microsoft yerel önerilen kurallar|Bu kural kümesine çok çeşitli sorunlar ele alınmaktadır. Bu yerel Minimum önerilen kurallar Microsoft tüm kurallar içerir.|  
  
##  <a name="BKMK_Run"></a>Kod çözümleme çalıştırın  
 Proje Özellikleri sayfaların kod çözümleme sayfasında projenizi derleme her zaman çalıştırmak için Kod Analizi yapılandırabilirsiniz. Kod çözümleme el ile de çalıştırabilirsiniz.  
  
 Kod çözümleme bir çözüm üzerinde çalıştırmak için:  
  
-   Üzerinde **yapı** menüsünde seçin **çalıştırmak Kod Analizi çözüm üzerinde**.  
  
 Kod çözümleme bir proje üzerinde çalıştırmak için:  
  
-   Çözüm Gezgini'nde proje adını seçin.  
  
-   Üzerinde **yapı** menüsünde seçin **çalıştırmak kod çözümleme** *proje adı*.  
  
 Çözüm ve Proje derlenir ve Kod Analizi çalıştırır. Sonuçları Kod Analizi penceresinde görüntülenir.  
  
##  <a name="BKMK_Analyze"></a>Çözümleme ve Kod Analizi uyarıları gidermek  
 Belirli bir uyarı çözümlemek için Kod Analizi penceresinde uyarıyı başlığını seçin. Sorun hakkında ek bilgileri görüntülemek için uyarı genişletir. Mümkün olduğunda, kod analizi için uyarı öncülük analiz mantığı ve satır numaralarını görüntüler. Sorunun olası çözümleri dahil olmak üzere uyarı hakkında ayrıntılı bilgi için Yardım konusunu ileti MSND Kitaplığı'nda görüntülemek için uyarı kimliği seçin.  
  
 Bir uyarı genişlettiğinizde, uyarıya neden olan kod satırı Visual Studio Kod Düzenleyicisi'nde vurgulanır.  
  
 Sorun anladıktan sonra kodunuzda çözebilirsiniz. Ardından uyarı artık Kod Analizi penceresinde görüntülenir ve yeni uyarılar gerçekleşti, düzeltme henüz emin olmak için Kod Analizi yeniden çalıştırın.  
  
> [!TIP]
>  Kod çözümleme Kod Analizi penceresinden yeniden çalıştırabilirsiniz. Seçin **Çözümle** düğmesine tıklayın ve analiz kapsamını seçin. Analiz çözümün tamamında veya seçili bir proje üzerinde yeniden çalıştırabilirsiniz.  
  
##  <a name="BKMK_Suppress"></a>Kod çözümleme uyarıları gizleme  
 Kod çözümleme uyarısı düzeltme değil zaman karar verebilirsiniz zamanlar vardır. Uyarı çözümleme sorunu kodunuzu herhangi bir gerçek uygulaması içinde çıkabilecek olasılık ile ilgili çok fazla değiştirilemeyen gerektirir karar verebilirsiniz. Veya uyarıda kullanılan analiz belirli bağlam için uygun olduğunu düşünüyorsanız. Kod Analizi penceresinde artık görünecekleri bireysel uyarıları gizleyebilirsiniz.  
  
 Bir uyarıyı gizlemek için:  
  
1.  Ayrıntılı bilgi görüntülenmiyorsa genişletmek için uyarı başlığını seçin.  
  
2.  Seçin **Eylemler** uyarı sonundaki bağlantı.  
  
3.  Seçin **bastırmak ileti** ve ardından **içinde kaynak**.  
  
 Bir ileti gizleme ekler `#pragma warning (disable:` *WarningId* `)` kod satırı için uyarı gizler.  
  
##  <a name="BKMK_Creating_work_items_for_code_analysis_warnings"></a>İş öğeleri için kod çözümleme uyarıları oluşturma  
 Visual Studio içinde hatalardan oturum iş öğesi izleme özelliğini kullanabilirsiniz. Bu özelliği kullanmak için Team Foundation Server örneğine bağlamanız gerekir.  
  
 **Bir veya daha fazla C/C++ kod uyarıları için bir iş öğesi oluşturmak için**  
  
1.  Kod Analizi penceresinde genişletin ve Uyarıları seçin  
  
2.  Uyarılar için kısayol menüsünden seçin **iş öğesi oluşturma**ve ardından iş öğesi türünü seçin.  
  
3.  Visual Studio seçili uyarılar için bir tek iş öğesi oluşturur ve iş öğesi bir IDE belge penceresinde görüntüler.  
  
4.  Ek bilgileri ekleyin ve ardından **çalışma öğesini Kaydet**.  
  
##  <a name="BKMK_Search"></a>Arama ve kod çözümleme sonuçlarını filtreleme  
 Uyarı iletilerini uzun listeler arayabilir ve birden çok proje çözümü uyarıları filtreleyebilirsiniz.  
  
1.  **Başlığı veya Uyarı Kimliği Filtresi uyarılarını için**: anahtar sözcüğü girin **filtre** metin kutusu.  
  
2.  **Projeye göre filtre uyarılar için**: bir birden çok proje çözümü üst listesinde bir veya daha fazla projeleri seçin Kod Analizi penceresinin sağ. Tüm uyarıları görüntülemek için çözüm adı seçin.  
  
3.  **Önem derecesi bazında Filtresi uyarılarını için**: varsayılan olarak, bir önem derecesi kod çözümleme iletileri atanan **uyarı**. Bir veya daha fazla iletileri olarak önemini atayabilirsiniz **hata** özel bir kuralda ayarlayın. Ya da seçin **uyarı** veya **hata** ilgili önem atanan iletileri görüntülemek için. Seçin **tüm** tüm iletileri görüntülemek için.