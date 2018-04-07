---
title: Visual Studio'da ayarlayın özel kod analizi kural oluşturma | Microsoft Docs
ms.date: 04/04/2018
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.addremoverulesets
helpviewer_keywords:
- Development Edition, rule sets
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: a094b6c59eb4e1d95949dc35a5c0479edb4d5a76
ms.sourcegitcommit: 3724338a5da5a6d75ba00452b0a607388b93ed0c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/06/2018
---
# <a name="custom-rule-sets"></a>Özel kural kümeleri

Özel bir oluşturabileceğiniz *kural kümesi* kod analizi için belirli bir proje gereksinimlerini karşılamak için.

## <a name="create-a-custom-rule-set"></a>Bir özel kural kümesi oluşturma

Özel bir kural oluşturmak için yerleşik bir kural kümesi açabilirsiniz **kural kümesi düzenleyici**. Buradan, ekleme veya kaldırma belirli kurallar ve kural ihlal edildiğinde oluşan eylem değiştirebilir&mdash;Örneğin, bir uyarı veya hata gösterir.

1. İçinde **Çözüm Gezgini**, projeye sağ tıklayın ve ardından **özellikleri**.

2. Üzerinde **özellikleri** sayfaları, select **Kod Analizi** sekmesi.

3. İçinde **bu kural kümesini çalıştırmak** aşağı açılan listesinde, aşağıdakilerden birini yapın:

    - Özelleştirmek istediğiniz kural kümesini seçin.

     \- veya -

    - Seçin  **\<Gözat... >** mevcut bir kuralı kümesini belirlemek için listede değil.

4. Seçin **açık** kuralları kural kümesi Düzenleyicisi'nde görüntülenecek.

Yeni bir kural kümesi dosyasından oluşturabilirsiniz **yeni dosya** iletişim:

1. Seçin **dosya** > **yeni** > **dosya**, veya basın **Ctrl**+**N**.

2. İçinde **yeni dosya** iletişim kutusunda **genel** solda, kategori ve ardından **Kod Analizi kural kümesi**.

3. **Aç**'ı seçin.

   Yeni *.ruleset* dosya kural kümesi Düzenleyicisi'nde açılır.

### <a name="create-a-custom-rule-set-from-multiple-rule-sets"></a>Birden çok kural kümesinden ayarlamak özel bir kural oluşturun

1. Çözüm Gezgini'nde projeye sağ tıklayın ve ardından **özellikleri**.

2. Üzerinde **özellikleri** sayfaları, select **Kod Analizi** sekmesi.

3. Seçin  **\<birden çok kural kümesi... Seç >** gelen **bu kural kümesini çalıştırmak**.

4. İçinde **Ekle veya Kaldır kural kümesi** kural kümesi Seç iletişim kutusunda, istediğiniz yeni kural kümesinde dahil etmek.

   ![Kural kümelerini iletişim kutusu Ekle Kaldır](media/add-remove-rule-sets.png)

5. Seçin **Kaydet**, için bir ad girin *.ruleset* dosya ve ardından **kaydetmek**.

   Yeni kural kümesi içinde seçili **bu kural kümesini çalıştırmak** listesi.

6. Seçin **açmak** yeni kural kümesi kural kümesi Düzenleyicisi'nde açın.

## <a name="name-and-description"></a>Ad ve açıklama

Düzenleyicide açık durumda olan bir kural kümesi görünen adını değiştirmek için açın **özellikleri** seçerek penceresi **Görünüm** > **Özellikler penceresini** menü çubuğunda. Görünen ad girin **adı** kutusu. Ayrıca kural kümesi için bir açıklama girebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

Bir kural kümesini sahip olduğunuza göre sonraki kurallar ekleyerek veya kuralları kaldırma veya kural ihlallerinin önemini düzenleyerek özelleştirmek için bir adımdır.

> [!div class="nextstepaction"]
> [Kuralları kural kümesi Düzenleyicisi'nde Değiştir](../code-quality/working-in-the-code-analysis-rule-set-editor.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: Yönetilen Kod Projesi İçin Kod Çözümlemesini Yapılandırma](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)
- [Kod çözümleme kural kümesi başvurusu](../code-quality/rule-set-reference.md)