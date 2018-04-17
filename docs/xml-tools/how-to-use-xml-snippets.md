---
title: Microsoft Visual Studio'daki XML Parçacıkları kullanma | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 3a27375b-81cc-48f6-a884-e1cb8c4f78f5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5751293124edab5c8415cd60d79aba9947fb94bf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-use-xml-snippets"></a>Nasıl yapılır: XML kullanım parçacıkları

XML Düzenleyicisi kısayol menüsünde aşağıdaki iki komutu kullanarak, XML parçacıkları çağırabilirsiniz. **Ekle parçacığı** komutu XML parçacığını İmleç konumuna ekler. **Surround With** komutu seçili metninin çevresindeki XML parçacığını sarmalar. Her XML parçacığını parçacığı türleri atadığı. Kod parçacığında türleri kod parçacığını ile kullanılabilir olup olmadığını belirlemek **Ekle parçacığı** komutu, **Surround With** komutu ya da her ikisini de.

XML parçacığını düzenleyiciye eklendikten sonra kod parçacığını düzenlenebilir tüm alanlarda sarı olarak vurgulanır ve imleç ilk düzenlenebilir alanı konumlandırıldı.

## <a name="insert-snippet"></a>Kod parçacığında Ekle

Aşağıdaki yordamlarda nasıl erişileceği açıklanmıştır **Ekle parçacığı** komutu.

> [!NOTE]
> **Ekle parçacığı** komutu kullanılabilir ayrıca klavye kısayolu (**Ctrl**+**K**, ardından **Ctrl** + **X**).

### <a name="to-insert-snippets-from-the-shortcut-menu"></a>Kısayol menüsünden parçacıkları eklemek için

1. İmleci XML parçacığını eklemek istediğiniz yere getirin.

2. Sağ tıklatıp **Ekle parçacığı**.

   Kullanılabilir XML parçacıkları listesi görüntülenir.

3. Fareyle listesinden veya kod parçacığında ve tuşlarına basarak adını yazarak parçacık **sekmesini** veya **Enter**.

### <a name="to-insert-snippets-using-the-intellisense-menu"></a>Kod parçacıkları IntelliSense menüsünü kullanarak eklemek için

1. İmleci XML parçacığını eklemek istediğiniz yere getirin.

2. Gelen **Düzenle** menüsündeki **IntelliSense**ve ardından **Ekle parçacığı**.

   Kullanılabilir XML parçacıkları listesi görüntülenir.

3. Fareyle listesinden veya kod parçacığında ve tuşlarına basarak adını yazarak parçacık **sekmesini** veya **Enter**.

### <a name="to-insert-snippets-through-the-intellisense-complete-word-list"></a>IntelliSense tam sözcüğü listesi kullanılarak parçacıkları eklemek için

1. İmleci XML parçacığını eklemek istediğiniz yere getirin.

2. Dosyanıza eklemek istediğiniz XML parçacığını yazmaya başlayın. Otomatik tamamlama açıksa, IntelliSense tam sözcüğü listesi görüntülenir. Görünmüyorsa, basın **Ctrl**+**alanı** etkinleştirin.

3. XML parçacığını tam sözcüğü listeden seçin.

4. Tuşuna **sekmesini**, **sekmesini** XML parçacığını çağırmak için.

> [!NOTE]
> XML parçacığını değil çağrıldığında durumlar olabilir. Örneğin, eklemeye çalışırsanız bir `xs:complexType` öğe içinde bir `xs:element` düğüm, Düzenleyici bir XML parçacığını oluşturmaz. Zaman bir `xs:complexType` öğe içinde kullanılır bir `xs:element` düğüm, düzenleyici eklemek için herhangi bir veri içermez gerekli öznitelikler veya alt öğeleri, yok.

### <a name="to-insert-snippets-using-the-shortcut-name"></a>Kısayol adını kullanarak parçacıkları eklemek için

1. İmleci XML parçacığını eklemek istediğiniz yere getirin.

2. Tür `<` Düzenleyicisi bölmesinde.

3. Tuşuna **Esc** IntelliSense tam sözcüğü listesi kapatın.

4. Kod parçacığında ve tuşuna kısayol adını yazın **sekmesini** XML parçacığını çağırmak için.

## <a name="surround-with"></a>İle surround

Aşağıdaki yordamlarda nasıl erişileceği açıklanmıştır **Surround With** komutu.

> [!NOTE]
> **Surround With** komutu kullanılabilir ayrıca klavye kısayolu (**Ctrl**+**K**, ardından **Ctrl** + **S**).

### <a name="to-use-surround-with-from-the-context-menu"></a>Bağlam menüsünden surround ile kullanmak için

1. XML Düzenleyicisi'nde surround için metni seçin.

2. Sağ tıklatıp **Surround With**.

   Kullanılabilir çevreleyen XML parçacıkları ile bir listesi görüntülenir.

3. Fareyle listesinden veya kod parçacığında ve tuşlarına basarak adını yazarak parçacık **sekmesini** veya **Enter**.

### <a name="to-use-surround-with-from-the-intellisense-menu"></a>IntelliSense menüsünden surround ile kullanmak için

1. XML Düzenleyicisi'nde surround için metni seçin.

2. Gelen **Düzenle** menüsündeki **IntelliSense**ve ardından **Surround With**.

   Kullanılabilir çevreleyen XML parçacıkları ile bir listesi görüntülenir.

3. Fareyle listesinden veya kod parçacığında ve tuşlarına basarak adını yazarak parçacık **sekmesini** veya **Enter**.

## <a name="using-xml-snippets"></a>XML parçacıkları

Bir XML parçacığını seçildikten sonra kod parçacığında metnin İmleç konumuna otomatik olarak eklenir. Kod parçacığını düzenlenebilir tüm alanlarda vurgulanır ve ilk düzenlenebilir bir alanı otomatik olarak seçilir. Seçili alanı Kutulu.

Bir alan seçildiğinde, alan için yeni bir değer yazabilirsiniz. Tuşuna basarak **sekmesini** kod parçacığını düzenlenebilir alanları arasında geçiş yapar; tuşlarına basarak **Shift**+**sekmesini** aralarında ters sırada geçiş yapar. Bir alan tıklatarak imleci alana koyar ve bir alan çift seçer. Bir alan vurgulanmış, alanın açıklamasını sunan bir araç ipucu görüntülenebilir.

Verilen alana yalnızca ilk örneği düzenlenemez. Bu alan vurgulanmış, diğer örneklerini alan özetlenmiştir. Düzenlenebilir bir alanı değerini değiştirdiğinizde, bu alan kod parçacığında kullanılan her yerde değiştirilir.

Tuşuna basarak **Enter** veya **Esc** alan düzenlemeyi iptal eder ve normal olarak Düzenleyicisi döndürür.

Kod parçacığı alanı ayarı değiştirerek düzenlenebilir kod parçacığını alanları için varsayılan renkleri değiştirilebilir **yazı tiplerini ve renkleri** bölmesinde **seçenekleri** iletişim kutusu. Daha fazla bilgi için bkz: [nasıl yapılır: değişiklik yazı tiplerini ve renkleri Düzenleyicisi'nde](../ide/reference/how-to-change-fonts-and-colors-in-the-editor.md).

## <a name="see-also"></a>Ayrıca bkz.

- [XML Kod Parçacıkları](../xml-tools/xml-snippets.md)
- [Nasıl Yapılır: XML Şemasından XML Kod Parçacığı Oluşturma](../xml-tools/how-to-generate-an-xml-snippet-from-an-xml-schema.md)
- [Nasıl Yapılır: XML Kod Parçacıkları Oluşturma](../xml-tools/how-to-create-xml-snippets.md)