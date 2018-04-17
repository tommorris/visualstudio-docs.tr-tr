---
title: Yönetilen kod Visual Studio için özel kod çözümleme iade ilkelerini uygulama | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.code.analysis.selecttfsrulesets
- vs.code.analysis.browsefortfsruleset
- vs.code.analysis.policyeditor
ms.assetid: fd029003-5671-4b24-8b6f-032e0a98b2e8
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 234ebb6896f358b7263f8fb7c29ad5be90102495
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="implement-custom-code-analysis-check-in-policies-for-managed-code"></a>Yönetilen kod için özel kod çözümleme iade ilkelerini uygulama

Bir kod çözümleme iade ilkesi sürüm denetimine iade önce üyeleri takım projesinin kaynak kodu çalıştırmalıdır kuralları kümesi belirtir. Microsoft, standart bir dizi sağlar *kural kümeleri* bu Grup kod çözümleme kurallarını işlevsel alanlara. *Özel İade İlkesi kural kümeleri* bir takım projesi için özel kod çözümleme kurallarını kümesi belirtin. Bir kural kümesi .ruleset dosyasında depolanır.

İade ilkeleri takım projesi düzeyinde ayarlayın ve sürüm denetimi ağacında .ruleset dosyasının konumu tarafından belirtilen. Sürüm denetimi konumunda takım ilke özel bir kural kümesinin bir kısıtlama yoktur.

Kod çözümleme özellikleri penceresinde her proje için kod projeleri için yapılandırılır. Özel bir kural için bir kod projesini kümesini, yerel bilgisayarda .ruleset dosyasının fiziksel konuma göre belirtilir. .Ruleset dosya kodunu projeyi aynı sürücüde bulunan belirtildiğinde, Visual Studio Proje yapılandırma dosyasında için göreli bir yol kullanır.

Bir takım projesi özel kural kümesi oluşturmak için bir önerilen herhangi bir kod projesinin bir parçası olmayan özel bir klasöre iade ilkesi .ruleset dosyasının depolanacağı bir yöntemdir. Dosya adanmış bir klasörde saklayın, kural dosya düzenleyebilen kısıtlayan izinleri uygulayabilirsiniz ve dizin yapısını kolayca taşıyabilirsiniz, başka bir dizin veya bilgisayar projeye içerir.

## <a name="create-the-team-project-custom-check-in-rule-set"></a>Takım projesi iade özel kural kümesi oluşturma

Takım projesi için ayarlanmış özel bir kural oluşturmak için önce kümesinde iade ilkesi kuralı için özel bir klasör oluşturun **Kaynak Denetim Gezgini**. Ardından kural kümesi dosyası oluşturun ve sürüm denetimine dosya ekleme. Son olarak, kural kod çözümleme iade ilkesi takım projesi için olarak kümesi belirtin.

> [!NOTE]
> Bir takım projesinde bir klasör oluşturmak için önce takım projesine kök yerel bilgisayardaki bir konuma eşlemeniz gerekir.

### <a name="to-create-the-version-control-folder-for-the-check-in-policy-rule-set"></a>İade İlkesi kural kümesi için sürüm denetim klasörü oluşturmak için

1. Takım Gezgini, takım projesi düğümünü genişletin ve ardından **kaynak denetimi**.

2. İçinde **klasörleri** bölmesinde, takım projesine sağ tıklayın ve ardından **yeni klasör**.

3. Ana kaynak denetimi bölmesinde, **yeni klasör**, tıklatın **yeniden adlandırma**ve klasör kural kümesi için bir ad yazın.

### <a name="to-create-the-check-in-policy-rule-set"></a>İade İlkesi kural kümesi oluşturmak için

1. Üzerinde **dosya** menüsündeki **yeni**ve ardından **dosya**.

2. İçinde **kategorileri** tıklatın **genel**.

3. İçinde **şablonları** listesinde, çift **Kod Analizi kural kümesi**.

4. [Kuralları](../code-quality/how-to-create-a-custom-rule-set.md) dosyası kural kümesinde içerir ve kuralını kaydetmek için oluşturduğunuz kural kümesi klasörü ayarlayın.

### <a name="to-add-the-rule-set-file-to-version-control"></a>Kural eklemek için sürüm denetimine dosya ayarlayın

1. İçinde **Kaynak Denetim Gezgini**, yeni klasörü sağ tıklatın ve ardından **klasöre öğe ekleme**.

     Daha fazla bilgi için bkz: [Git ve VSTS](/vsts/git/overview).

2. Kural kümesi oluşturduğunuz dosyasını tıklatın ve ardından **son**.

     Dosya kaynak denetimine eklenir ve sizin için kullanıma.

3. İçinde **Kaynak Denetim Gezgini** Ayrıntıları penceresinde, dosya adına sağ tıklayın ve ardından **bekleyen değişiklikleri iade**.

4. İçinde **iade** iletişim kutusu, bir açıklama ekleyin ve ardından seçeneğine sahip **iade**.

    > [!NOTE]
    > Takım projesi için zaten bir kod çözümleme iade ilkesi yapılandırdıysanız ve seçtiğiniz **yalnızca geçerli çözümün bir parçası olan dosyaları içerecek şekilde iade zorla**, bir ilke hatası uyarı tetikler. İlke hata iletişim kutusunda seçin **ilke hatası geçersiz kılabilir ve iade etme devam**. Gerekli bir açıklama ekleyin ve ardından **Tamam**.

### <a name="to-specify-the-rule-set-file-as-the-check-in-policy"></a>Dosyası kural belirtmek için ilke olarak ayarlayın

1. Üzerinde **takım** menüsündeki **takım projesi ayarları**ve ardından **kaynak denetimi**.

2. Tıklatın **iade ilkesi**ve ardından **Ekle**.

3. İçinde **iade ilkesi** listesinde, çift **Kod Analizi**, emin olun **yönetilen kod için Kod Analizine Zorlama** onay kutusu seçilidir.

4. İçinde **bu kural kümesini çalıştırmak** tıklatın  **\<kaynak denetiminden kural kümesi seçin >**.

5. Sürüm denetimindeki iade ilkesi kuralı kümesi dosyasının yolunu yazın.

     Yol için aşağıdaki söz dizimini uygun olmalıdır:

     **$/** `TeamProjectName` **/** `VersionControlPath`

    > [!NOTE]
    > Aşağıdaki yordamlardan birini kullanarak yolu kopyalayabilirsiniz **Kaynak Denetim Gezgini**:

    - İçinde **klasörleri** bölmesinde, kural kümesi dosyasını içeren klasörü tıklatın. Sürüm denetim yolu görünür klasörünün kopyalama **kaynak** kutusuna ve kural kümesi dosyasının adını elle yazın.

    - Ayrıntıları penceresinde, kural kümesi dosyasını sağ tıklatın ve ardından **özellikleri**. Üzerinde **genel** sekmesinde, değeri Kopyala **sunucu adı**.

## <a name="synchronize-code-projects-to-the-check-in-policy-rule-set"></a>Kod projeleri iade ilkesi kuralı kümesine Eşitle

Bir takım projesi iade ilkesi kuralı kod projesi yapılandırma kod projesi Özellikleri iletişim kutusundaki kod çözümleme kural kümesi olarak ayarla belirtin. Kural kümesi kodunu projeyi aynı sürücüde yer alıyorsa, göreli bir yol yolun dosya iletişim kutusundan seçildiğinde kural kümesini belirtmek için kullanılır. Denetim yapıları benzer yerel sürümünü kullanan diğer bilgisayarlara taşınabilir proje özelliklerini ayarlar göreli bir yol sağlar.

### <a name="to-specify-a-team-project-rule-set-as-the-rule-set-of-a-code-project"></a>Bir takım projesi kural belirtmek için bir kod proje kural kümesi ayarlayın

1. Gerekirse, iade ilkesi kuralı kümesi klasör ve dosya sürümü denetiminden alın.

   Bu adımda gerçekleştirebilirsiniz **Kaynak Denetim Gezgini** sağ tıklayarak kural klasörünü ve ardından kümesi **en son sürümü Al**.

2. İçinde **Çözüm Gezgini**kod projesine sağ tıklayın ve ardından **özellikleri**.

3. **Kod çözümleme tıklatın**.

4. Gerekiyorsa, uygun seçenekleri tıklatın **yapılandırma** ve **Platform** listeler.

5. Kod çözümleme kodunu projeyi belirtilen yapılandırma kullanılarak oluşturulmuştur her zaman çalıştırmak için seçin **etkinleştirme kodu (tanımlar CODE_ANALYSIS sabiti) çözümleme yapı** onay kutusu.

6. Diğer şirketlerden bileşenleri kodda yoksaymayı seçin **bastırmak oluşturulan kod sonuçlarından** onay kutusu.

7. İçinde **bu kural kümesini çalıştırmak** tıklatın  **\<Gözat... >**.

8. İade İlkesi kuralı kümesi dosyasının yerel sürümünü belirtin.