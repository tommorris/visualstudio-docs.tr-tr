---
title: 'Hızlı Başlangıç: C/C++ kod çözümleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- C/C++ code analysis
- code analysis,C/C++
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3b892fa9c737561399de3edad569102a8d79ab02
ms.sourcegitcommit: 3724338a5da5a6d75ba00452b0a607388b93ed0c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/06/2018
---
# <a name="quickstart-code-analysis-for-cc"></a>Hızlı Başlangıç: C/C++ için Kod Analizi

Kod çözümleme düzenli olarak C veya C++ kodu çalıştırarak uygulamanızı kalitesini artırabilir. Bu ortak sorunları, iyi bir programlama uygulama ya da test aracılığıyla bulmak zordur kusurları ihlalleri bulmanıza yardımcı olabilir. Kod çözümleme geçerli olan, ancak hala siz veya kodunuzu kullanan diğer kişiler için sorunlarına neden olabilir belirli kod düzenleri arar çünkü kod analizi uyarıları derleyici hataları ve Uyarıları farklılık gösterir.

## <a name="configure-rule-sets-for-a-project"></a>Bir proje için kural kümeleri yapılandırma

1. İçinde **Çözüm Gezgini**, proje adı için kısayol menüsünü açın ve ardından **özellikleri**.

2. Aşağıdaki adımlar isteğe bağlıdır:

    1. İçinde **yapılandırma** ve **Platform** listeleri, derleme yapılandırmasını ve hedef platformu seçin.

    2. Varsayılan olarak, Kod Analizi uyarıları dış araçları tarafından otomatik olarak oluşturulan kodundan bildirmiyor. Oluşturulan kodundan uyarıları görüntülemek için temizleyin **bastırmak oluşturulan kod sonuçlarından** onay kutusu.

        > [!NOTE]
        > Hataları ve Uyarıları formlar ve şablonlar görüntülendiğinde bu seçenek kod çözümleme hataları ve Uyarıları oluşturulan kodundan engelleme. Hem görüntülemek ve bir form veya şablon için kaynak kodunu sağlayabilirsiniz.

3. Kod çözümleme proje seçilen yapılandırma kullanılarak oluşturulmuştur her zaman çalıştırmak için seçin **derlemede C/C++ için Kod Analizi etkinleştir** onay kutusu. Ayrıca Kod Analizi el ile açarak çalıştırabilirsiniz **Çözümle** menüsüne ve ardından seçme **çalıştırmak kod çözümleme** *ProjectName*.

4. İçinde **bu kural kümesini çalıştırmak** listesinde, aşağıdakilerden birini yapın:

    - Kullanmak istediğiniz kural kümesini seçin.

    - Seçin  **\<Gözat... >** var olan bir özel kural kümesini belirlemek için listede değil.

    - Tanımlayan bir [özel kural kümesi](../code-quality/how-to-create-a-custom-rule-set.md).

### <a name="standard-cc-rule-sets"></a>Standart C/C++ kural kümeleri

Visual Studio iki standart yerel kod için kural kümesini içerir:

|Kural kümesi|Açıklama|
|--------------|-----------------|
|Microsoft yerel Minimum kurallar önerilir|Bu kural kümesine olası güvenlik açıklarını ve uygulama çökme (Crash) dahil olmak üzere, yerel kodunuzda en kritik sorunlar odaklanır. Yerel projeleriniz için oluşturduğunuz herhangi bir özel kural kümesi içinde bu kural kümesi içermelidir.|
|Microsoft yerel önerilen kurallar|Bu kural kümesine çok çeşitli sorunlar ele alınmaktadır. Bu yerel Minimum önerilen kurallar Microsoft tüm kurallar içerir.|

## <a name="run-code-analysis"></a>Kod çözümleme çalıştırın

Proje Özellikleri sayfaların kod çözümleme sayfasında projenizi derleme her zaman çalıştırmak için Kod Analizi yapılandırabilirsiniz. Kod çözümleme el ile de çalıştırabilirsiniz.

Kod çözümleme bir çözüm üzerinde çalıştırmak için:

- Üzerinde **yapı** menüsünde seçin **çalıştırmak Kod Analizi çözüm üzerinde**.

 Kod çözümleme bir proje üzerinde çalıştırmak için:

- Çözüm Gezgini'nde proje adını seçin.

- Üzerinde **yapı** menüsünde seçin **çalıştırmak kod çözümleme** *proje adı*.

 Çözüm ve Proje derlenir ve Kod Analizi çalıştırır. Sonuçlar hata listesinde görüntülenir.

## <a name="analyze-and-resolve-code-analysis-warnings"></a>Çözümleme ve Kod Analizi uyarıları gidermek

Belirli bir uyarı analiz etmek için hata listesine uyarı başlığını seçin. Sorun hakkında ek bilgileri görüntülemek için uyarı genişletir. Mümkün olduğunda, kod analizi için uyarı öncülük analiz mantığı ve satır numaralarını görüntüler. Sorunun olası çözümleri dahil olmak üzere uyarı hakkında ayrıntılı bilgi için karşılık gelen çevrimiçi Yardım konusunu görüntülemek için uyarı kimliği seçin.

Bir uyarıyı seçtiğinizde, uyarıya neden olan kod satırı Visual Studio Kod Düzenleyicisi'nde vurgulanır.

Sorun anladıktan sonra kodunuzda çözebilirsiniz. Ardından, uyarı artık hata listesinde görüntülenir ve yeni uyarılar gerçekleşti, düzeltme henüz emin olmak için Kod Analizi yeniden çalıştırın.

## <a name="suppress-code-analysis-warnings"></a>Kod çözümleme uyarılarını bastırma

Kod çözümleme uyarısı düzeltme değil zaman karar verebilirsiniz zamanlar vardır. Uyarı çözümleme sorunu kodunuzu herhangi bir gerçek uygulaması içinde çıkabilecek olasılık ile ilgili çok fazla değiştirilemeyen gerektirir karar verebilirsiniz. Veya uyarıda kullanılan analiz belirli bağlam için uygun olduğunu düşünüyorsanız. Artık hata listesinde görünecekleri bireysel uyarıları gizleyebilirsiniz.

Bir uyarıyı gizlemek için:

1. Ayrıntılı bilgi görüntülenmiyorsa genişletmek için uyarı başlığını seçin.

2. Seçin **Eylemler** uyarı sonundaki bağlantı.

3. Seçin **bastırmak ileti** ve ardından **içinde kaynak**.

 Bir ileti gizleme ekler `#pragma warning (disable:` *WarningId* `)` kod satırı için uyarı gizler.

## <a name="create-work-items-for-code-analysis-warnings"></a>İş öğeleri için Kod Analizi uyarıları oluşturma

Visual Studio içinde hatalardan oturum iş öğesi izleme özelliğini kullanabilirsiniz. Bu özelliği kullanmak için Team Foundation Server örneğine bağlamanız gerekir.

**Bir veya daha fazla C/C++ kod uyarıları için bir iş öğesi oluşturmak için**

1. Hata listesi genişletin ve Uyarıları seçin

2. Uyarılar için kısayol menüsünden seçin **iş öğesi oluşturma**ve ardından iş öğesi türünü seçin.

3. Visual Studio seçili uyarılar için bir tek iş öğesi oluşturur ve iş öğesi bir IDE belge penceresinde görüntüler.

4. Ek bilgileri ekleyin ve ardından **çalışma öğesini Kaydet**.

## <a name="search-and-filter-code-analysis-results"></a>Arama ve filtreleme kod çözümleme sonuçları

Uyarı iletilerini uzun listeler arayabilir ve birden çok proje çözümü uyarıları filtreleyebilirsiniz.

- **Başlığı veya Uyarı Kimliği Filtresi uyarılarını için**: Ara kutusuna anahtar sözcüğü girin.

- **Önem derecesi bazında Filtresi uyarılarını için**: varsayılan olarak, bir önem derecesi kod çözümleme iletileri atanan **uyarı**. Bir veya daha fazla iletileri olarak önemini atayabilirsiniz **hata** özel bir kuralda ayarlayın. Üzerinde **önem** sütunu **hata listesi**, aşağı açılan oku tıklatın ve ardından filtre simgesini seçin. Seçin **uyarı** veya **hata** ilgili önem atanan iletileri görüntülemek için. Seçin **Tümünü Seç** tüm iletileri görüntülemek için.

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ için Kod Analizi](../code-quality/code-analysis-for-c-cpp-overview.md)