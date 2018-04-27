---
title: Çalıştırılacak C++ Kurallarını Belirtmek için Kural Kümeleri Kullanma
ms.date: 04/28/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- cplusplus
ms.openlocfilehash: ccb64fba6a646de0974c9de6e35beb98738b7300
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2018
---
# <a name="use-rule-sets-to-specify-the-c-rules-to-run"></a>Çalıştırılacak C++ kurallarını belirtmek için kural kümeleri kullanma

Visual Studio'da oluşturma ve özel bir değiştirme *kural kümesi* Kod Analizi ile ilişkilendirilmiş belirli proje gereksinimlerini karşılamak için. Varsayılan kural kümeleri depolanmış `%VSINSTALLDIR%\Team Tools\Static Analysis Tools\Rule Sets`.

**Visual Studio 2017 sürüm 15.7** Düzenleyici herhangi bir metin kullanarak özel kural kümeleri oluşturma ve bunları ne oluşturma sistemi kullanıyorsanız olsun komut satırı derlemeleri uygulayabilirsiniz. Daha fazla bilgi için bkz: [/ analyze: ruleset](/cpp/build/reference/analyze-code-quality).

Visual Studio'da ayarlayın özel bir C++ kuralı oluşturmak için C/C++ projesi Visual Studio IDE içinde açık olması gerekir. Kural kümesi Düzenleyicisi'nde bir standart bir kural kümesi'ni açın ve ardından ekler veya belirli kuralları kaldırın ve isteğe bağlı olarak Kod Analizi kural ihlal ettiğini belirlediğinde gerçekleştirilen eylemleri değiştirebilirsiniz.

Yeni özel bir kural oluşturmak için yeni bir dosya adı kullanarak kaydedin. Özel kural kümesi projeye otomatik olarak atanır.

## <a name="to-create-a-custom-rule-from-a-single-existing-rule-set"></a>Tek bir var olan kural kümesinden özel bir kural oluşturmak için

1. Çözüm Gezgini'nde, proje için kısayol menüsünü açın ve ardından **özellikleri**.

2. Üzerinde **özellikleri** sekmesinde, seçin **Kod Analizi**.

3. İçinde **kural kümesi** aşağı açılan listesinde, aşağıdakilerden birini yapın:

    - Özelleştirmek istediğiniz kural kümesini seçin.

     \- veya -

    - Seçin  **\<Gözat... >** mevcut bir kuralı kümesini belirlemek için listede değil.

4. Seçin **açık** kuralları kural kümesi Düzenleyicisi'nde görüntülenecek.

## <a name="to-modify-a-rule-set-in-the-rule-set-editor"></a>Bir kural değiştirmek için kural kümesi Düzenleyicisi'nde ayarlayın

- Kural kümesi görünen adını değiştirmek için **Görünüm** menüsünde seçin **Özellikler penceresini**. Görünen ad girin **adı** kutusu. Görünen adı dosya adından farklı olabilir dikkat edin.

- Grubun tüm kuralları bir özel kural kümesine eklemek için Grup onay kutusunu seçin. Grubun tüm kuralları kaldırmak için onay kutusunu temizleyin.

- Özel bir kural kümesi için belirli bir kural eklemek, kuralın onay kutusunu seçin. Kural kural kümesinden kaldırmak için onay kutusunu temizleyin.

- Bir kod analizi kural ihlal edildiğinde gerçekleştirilecek eylemi değiştirmek için tercih **eylem** kural için alan ve aşağıdaki değerlerden birini seçin:

     **Uyar** -bir uyarı oluşturur.

     **Hata** -bir hata oluşturur.

     **Hiçbiri** -kural devre dışı bırakır. Bu eylem kural kümesi kuralı kaldırma aynıdır.

## <a name="to-group-filter-or-change-the-fields-in-the-rule-set-editor-by-using-the-rule-set-editor-toolbar"></a>Gruplandırmak için filtre veya kural kümesi Düzenleyici araç çubuğunu kullanarak kural kümesi Düzenleyici alanları değiştirin

- Tüm grupları kurallarında genişletmek için seçin **Tümünü Genişlet**.

- Tüm grupları kurallarında daraltmak için tercih **Daralt tüm**.

- Kurallar tarafından gruplandırılır alanını değiştirmek için alanından seçin **Group By** listesi. Gruplanmamış kuralları görüntülemeyi seçebilir  **\<Hiçbiri >**.

- Eklemek veya kural sütunlarında alanları kaldırmak istediğiniz **sütun seçenekleri**.

- Geçerli çözüme uygulamayın kuralları gizlemek için seçin **Gizle geçerli çözüme uygulamayın kuralları**.

- Gösterme ve gizleme hata eylemi atanmış olan kurallar arasında geçiş yapmak için tercih **Göster Kod Analizi hatalara neden olabilir kuralları**.

- Gösterme ve gizleme uyarı eylemi atanmış olan kurallar arasında geçiş yapmak için tercih **Göster Kod Analizi uyarıları oluşturan kuralları**.

- Gösterme ve gizleme atanan kuralları arasında geçiş yapmak için **hiçbiri** eylemi seçin **Göster etkin olmayan kuralları**.

- Eklemek veya varsayılan kural kümesi geçerli kural kümesinde Microsoft kaldırmak istediğiniz **ekleme veya kaldırma alt kural kümeleri**.

## <a name="to-create-a-rule-set-in-a-text-editor"></a>Bir kural oluşturmak için bir metin düzenleyicisinde ayarlama

Özel bir kural kümesini bir metin düzenleyicisi oluşturun, herhangi bir konumda depolayın bir `.ruleset` uzantısı ve ile uygulama [/ analyze: ruleset](/cpp/build/reference/analyze-code-quality) derleyici seçeneği.

Aşağıdaki örnek, bir başlangıç noktası olarak kullanabileceğiniz dosyası temel bir kural kümesi gösterir:

```xml

<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description=" " ToolsVersion="15.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```
