---
title: "Yönetilen kod için özel kod çözümleme iade ilkelerini uygulama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.code.analysis.selecttfsrulesets
- vs.code.analysis.browsefortfsruleset
- vs.code.analysis.policyeditor
ms.assetid: fd029003-5671-4b24-8b6f-032e0a98b2e8
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 1c940c10c85901e5da7425c33f4bdbd726be7627
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="implementing-custom-code-analysis-check-in-policies-for-managed-code"></a>Yönetilen Kod için Özel Kod Çözümleme İade İlkelerini Uygulama
Bir kod çözümleme iade ilkesi sürüm denetimine iade önce üyeleri takım projesinin kaynak kodu çalıştırmalıdır kuralları kümesi belirtir. Microsoft, standart bir dizi sağlar *kural kümeleri* bu Grup kod çözümleme kurallarını işlevsel alanlara. *Özel İade İlkesi kural kümeleri* bir takım projesi için özel kod çözümleme kurallarını kümesi belirtin. Bir kural kümesi .ruleset dosyasında depolanır.  
  
 İade ilkeleri takım projesi düzeyinde ayarlayın ve sürüm denetimi ağacında .ruleset dosyasının konumu tarafından belirtilen. Sürüm denetimi konumunda takım ilke özel bir kural kümesinin bir kısıtlama yoktur.  
  
 Kod çözümleme özellikleri penceresinde her proje için kod projeleri için yapılandırılır. Özel bir kural için bir kod projesini kümesini, yerel bilgisayarda .ruleset dosyasının fiziksel konuma göre belirtilir. .Ruleset dosya kodunu projeyi aynı sürücüde bulunan belirtildiğinde, Visual Studio Proje yapılandırma dosyasında için göreli bir yol kullanır.  
  
 Bir takım projesi özel kural kümesi oluşturmak için bir önerilen herhangi bir kod projesinin bir parçası olmayan özel bir klasöre iade ilkesi .ruleset dosyasının depolanacağı bir yöntemdir. Dosya adanmış bir klasörde saklayın, kural dosya düzenleyebilen kısıtlayan izinleri uygulayabilirsiniz ve dizin yapısını kolayca taşıyabilirsiniz, başka bir dizin veya bilgisayar projeye içerir.  
  
## <a name="creating-the-team-project-custom-check-in-rule-set"></a>Takım projesi iade özel kural kümesi oluşturma  
 Takım projesi için ayarlanmış özel bir kural oluşturmak için önce kümesinde iade ilkesi kuralı için özel bir klasör oluşturun **Kaynak Denetim Gezgini**. Ardından kural kümesi dosyası oluşturun ve sürüm denetimine dosya ekleme. Son olarak, kural kod çözümleme iade ilkesi takım projesi için olarak kümesi belirtin.  
  
> [!NOTE]
>  Bir takım projesinde bir klasör oluşturmak için önce takım projesine kök yerel bilgisayardaki bir konuma eşlemeniz gerekir.  
  
#### <a name="to-create-the-version-control-folder-for-the-check-in-policy-rule-set"></a>İade İlkesi kural kümesi için sürüm denetim klasörü oluşturmak için  
  
1.  İçinde [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)], takım projesi düğümünü genişletin ve ardından **kaynak denetimi**.  
  
2.  İçinde **klasörleri** bölmesinde, takım projesine sağ tıklayın ve ardından **yeni klasör**.  
  
3.  Ana kaynak denetimi bölmesinde, **yeni klasör**, tıklatın **yeniden adlandırma**ve klasör kural kümesi için bir ad yazın.  
  
#### <a name="to-create-the-check-in-policy-rule-set"></a>İade İlkesi kural kümesi oluşturmak için  
  
1.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **dosya**.  
  
2.  İçinde **kategorileri** tıklatın **genel**.  
  
3.  İçinde **şablonları** listesinde, çift **Kod Analizi kural kümesi**.  
  
4.  Kural kümesinde içeren kuralları belirtin ve sonra kural kümesi dosyasını oluşturduğunuz kural kümesi klasörüne kaydedin.  
  
     Daha fazla bilgi için bkz: [özel kural kümeleri oluşturma](../code-quality/creating-custom-code-analysis-rule-sets.md)  
  
#### <a name="to-add-the-rule-set-file-to-version-control"></a>Kural eklemek için sürüm denetimine dosya ayarlayın  
  
1.  İçinde **Kaynak Denetim Gezgini**, yeni klasörü sağ tıklatın ve ardından **klasöre öğe ekleme**.  
  
     Daha fazla bilgi için bkz: [Git ve VSTS](/vsts/git/overview).  
  
2.  Kural kümesi oluşturduğunuz dosyasını tıklatın ve ardından **son**.  
  
     Dosya kaynak denetimine eklenir ve sizin için kullanıma.  
  
3.  İçinde **Kaynak Denetim Gezgini** Ayrıntıları penceresinde, dosya adına sağ tıklayın ve ardından **bekleyen değişiklikleri iade**.  
  
4.  İçinde **iade** iletişim kutusu, bir açıklama ekleyin ve ardından seçeneğine sahip **iade**.  
  
    > [!NOTE]
    >  Takım projesi için zaten bir kod çözümleme iade ilkesi yapılandırdıysanız ve seçtiğiniz **yalnızca geçerli çözümün bir parçası olan dosyaları içerecek şekilde iade zorla**, bir ilke hatası uyarı tetikler. İlke hata iletişim kutusunda seçin **ilke hatası geçersiz kılabilir ve iade etme devam**. Gerekli bir açıklama ekleyin ve ardından **Tamam**.  
  
#### <a name="to-specify-the-rule-set-file-as-the-check-in-policy"></a>Dosyası kural belirtmek için ilke olarak ayarlayın  
  
1.  Üzerinde **takım** menüsündeki **takım projesi ayarları**ve ardından **kaynak denetimi**.  
  
2.  Tıklatın **iade ilkesi**ve ardından **Ekle**.  
  
3.  İçinde **iade ilkesi** listesinde, çift **Kod Analizi**, emin olun **yönetilen kod için Kod Analizine Zorlama** onay kutusu seçilidir.  
  
4.  İçinde **bu kural kümesini çalıştırmak** tıklatın  **\<kaynak denetiminden kural kümesi seçin >**.  
  
5.  Sürüm denetimindeki iade ilkesi kuralı kümesi dosyasının yolunu yazın.  
  
     Yol için aşağıdaki söz dizimini uygun olmalıdır:  
  
     **$/** `TeamProjectName` **/** `VersionControlPath`  
  
    > [!NOTE]
    >  Aşağıdaki yordamlardan birini kullanarak yolu kopyalayabilirsiniz **Kaynak Denetim Gezgini**:  
  
    -   İçinde **klasörleri** bölmesinde, kural kümesi dosyasını içeren klasörü tıklatın. Sürüm denetim yolu görünür klasörünün kopyalama **kaynak** kutusuna ve kural kümesi dosyasının adını elle yazın.  
  
    -   Ayrıntıları penceresinde, kural kümesi dosyasını sağ tıklatın ve ardından **özellikleri**. Üzerinde **genel** sekmesinde, değeri Kopyala **sunucu adı**.  
  
## <a name="synchronizing-code-projects-to-the-check-in-policy-rule-set"></a>İade İlkesi kuralı kümesine kod projelerini eşitleme  
 Bir takım projesi iade ilkesi kuralı kod projesi yapılandırma kod projesi Özellikleri iletişim kutusundaki kod çözümleme kural kümesi olarak ayarla belirtin. Kural kümesi kodunu projeyi aynı sürücüde yer alıyorsa, göreli bir yol yolun dosya iletişim kutusundan seçildiğinde kural kümesini belirtmek için kullanılır. Denetim yapıları benzer yerel sürümünü kullanan diğer bilgisayarlara taşınabilir proje özelliklerini ayarlar göreli bir yol sağlar.  
  
#### <a name="to-specify-a-team-project-rule-set-as-the-rule-set-of-a-code-project"></a>Bir takım projesi kural belirtmek için bir kod proje kural kümesi ayarlayın  
  
1.  Gerekirse, iade ilkesi kuralı kümesi klasör ve dosya sürümü denetiminden alın.  
  
     Bu adımda gerçekleştirebilirsiniz **Kaynak Denetim Gezgini** sağ tıklayarak kural klasörünü ve ardından kümesi **en son sürümü Al**.  
  
2.  İçinde **Çözüm Gezgini**kod projesine sağ tıklayın ve ardından **özellikleri**.  
  
3.  **Kod çözümleme tıklatın**.  
  
4.  Gerekiyorsa, uygun seçenekleri tıklatın **yapılandırma** ve **Platform** listeler.  
  
5.  Kod çözümleme kodunu projeyi belirtilen yapılandırma kullanılarak oluşturulmuştur her zaman çalıştırmak için seçin **etkinleştirme kodu (tanımlar CODE_ANALYSIS sabiti) çözümleme yapı** onay kutusu.  
  
6.  Diğer şirketlerden bileşenleri kodda yoksaymayı seçin **bastırmak oluşturulan kod sonuçlarından** onay kutusu.  
  
7.  İçinde **bu kural kümesini çalıştırmak** tıklatın  **\<Gözat... >**.  
  
8.  İade İlkesi kuralı kümesi dosyasının yerel sürümünü belirtin.