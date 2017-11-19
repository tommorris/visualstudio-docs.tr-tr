---
title: "Nasıl yapılır: XML parçacıklarını kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a27375b-81cc-48f6-a884-e1cb8c4f78f5
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d442dbf376d5615b6c10842c16d01183fc70056a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-use-xml-snippets"></a>Nasıl yapılır: XML parçacıklarını kullanma
XML Düzenleyicisi kısayol menüsünde aşağıdaki iki komutu kullanarak, XML parçacıkları çağırabilirsiniz. **Ekle parçacığı** komutu XML parçacığını İmleç konumuna ekler. **Surround With** komutu seçili metninin çevresindeki XML parçacığını sarmalar. Her XML parçacığını parçacığı türleri atadığı. Kod parçacığında türleri kod parçacığını ile kullanılabilir olup olmadığını belirlemek **Ekle parçacığı** komutu, **Surround With** komutu ya da her ikisini de.  
  
 XML parçacığını düzenleyiciye eklendikten sonra kod parçacığını düzenlenebilir tüm alanlarda sarı olarak vurgulanır ve imleç ilk düzenlenebilir alanı konumlandırıldı.  
  
## <a name="insert-snippet"></a>Kod parçacığında Ekle  
 Aşağıdaki yordamlarda nasıl erişileceği açıklanmıştır **Ekle parçacığı** komutu.  
  
> [!NOTE]
>  **Ekle parçacığı** komutu kullanılabilir ayrıca klavye kısayolu (CTRL + K sonra CTRL + X).  
  
#### <a name="to-insert-snippets-from-the-shortcut-menu"></a>Kısayol menüsünden parçacıkları eklemek için  
  
1.  İmleci XML parçacığını eklemek istediğiniz yere getirin.  
  
2.  Sağ tıklatıp **Ekle parçacığı**.  
  
     Kullanılabilir XML parçacıkları listesi görüntülenir.  
  
3.  Parçacık fareyle listesinden veya kod parçacığını adını yazıp sekme veya ENTER tuşuna basarak seçin.  
  
#### <a name="to-insert-snippets-using-the-intellisense-menu"></a>Kod parçacıkları IntelliSense menüsünü kullanarak eklemek için  
  
1.  İmleci XML parçacığını eklemek istediğiniz yere getirin.  
  
2.  Gelen **Düzenle** menüsündeki **IntelliSense**ve ardından **Ekle parçacığı**.  
  
     Kullanılabilir XML parçacıkları listesi görüntülenir.  
  
3.  Parçacık fareyle listesinden veya kod parçacığını adını yazıp sekme veya ENTER tuşuna basarak seçin.  
  
#### <a name="to-insert-snippets-through-the-intellisense-complete-word-list"></a>IntelliSense tam sözcüğü listesi kullanılarak parçacıkları eklemek için  
  
1.  İmleci XML parçacığını eklemek istediğiniz yere getirin.  
  
2.  Dosyanıza eklemek istediğiniz XML parçacığını yazmaya başlayın. Otomatik tamamlama açıksa, IntelliSense tam sözcüğü listesi görüntülenir. Görünmüyorsa, etkinleştirmek için CTRL + ARA ÇUBUĞU tuşlarına basın.  
  
3.  XML parçacığını tam sözcüğü listeden seçin.  
  
4.  Sekme tuşuna basın, XML parçacığını çağrılacak SEKMESİ.  
  
> [!NOTE]
>  XML parçacığını değil çağrıldığında durumlar olabilir. Örneğin, eklemeye çalışırsanız bir `xs:complexType` öğe içinde bir `xs:element` düğüm, Düzenleyici bir XML parçacığını oluşturmaz. Zaman bir `xs:complexType` öğe içinde kullanılır bir `xs:element` düğüm, düzenleyici eklemek için herhangi bir veri içermez gerekli öznitelikler veya alt öğeleri, yok.  
  
#### <a name="to-insert-snippets-using-the-shortcut-name"></a>Kısayol adını kullanarak parçacıkları eklemek için  
  
1.  İmleci XML parçacığını eklemek istediğiniz yere getirin.  
  
2.  Tür `<` Düzenleyicisi bölmesinde.  
  
3.  IntelliSense tam sözcüğü listesini kapatmak için ESC tuşuna basın.  
  
4.  Kod parçacığını kısayol adını yazın ve XML parçacığını çağırmak için SEKME tuşuna basın.  
  
## <a name="surround-with"></a>İle surround  
 Aşağıdaki yordamlarda nasıl erişileceği açıklanmıştır **Surround With** komutu.  
  
> [!NOTE]
>  **Surround With** komuttur ayrıca klavye kısayolu (CTRL + K sonra CTRL + S) ile kullanılabilir.  
  
#### <a name="to-use-surround-with-from-the-context-menu"></a>Bağlam menüsünden surround ile kullanmak için  
  
1.  XML Düzenleyicisi'nde surround için metni seçin.  
  
2.  Sağ tıklatıp **Surround With**.  
  
     Kullanılabilir çevreleyen XML parçacıkları ile bir listesi görüntülenir.  
  
3.  Parçacık fareyle listesinden veya kod parçacığını adını yazıp sekme veya ENTER tuşuna basarak seçin.  
  
#### <a name="to-use-surround-with-from-the-intellisense-menu"></a>IntelliSense menüsünden surround ile kullanmak için  
  
1.  XML Düzenleyicisi'nde surround için metni seçin.  
  
2.  Gelen **Düzenle** menüsündeki **IntelliSense**ve ardından **Surround With**.  
  
     Kullanılabilir çevreleyen XML parçacıkları ile bir listesi görüntülenir.  
  
3.  Parçacık fareyle listesinden veya kod parçacığını adını yazıp sekme veya ENTER tuşuna basarak seçin.  
  
## <a name="using-xml-snippets"></a>XML parçacıkları  
 Bir XML parçacığını seçildikten sonra kod parçacığında metnin İmleç konumuna otomatik olarak eklenir. Kod parçacığını düzenlenebilir tüm alanlarda vurgulanır ve ilk düzenlenebilir bir alanı otomatik olarak seçilir. Seçili alanı Kutulu.  
  
 Bir alan seçildiğinde, alan için yeni bir değer yazabilirsiniz. Sekme döngüleri kod parçacığını düzenlenebilir alanlarından tuşuna basarak; bunları üst karakter + sekme dolaşma ters sırada tuşuna basın. Bir alan tıklatarak imleci alana koyar ve bir alan çift seçer. Bir alan vurgulanmış, alanın açıklamasını sunan bir araç ipucu görüntülenebilir.  
  
 Verilen alana yalnızca ilk örneği düzenlenemez. Bu alan vurgulanmış, diğer örneklerini alan özetlenmiştir. Düzenlenebilir bir alanı değerini değiştirdiğinizde, bu alan kod parçacığında kullanılan her yerde değiştirilir.  
  
 ENTER veya ESC tuşuna basarak alan düzenlemeyi iptal eder ve düzenleyici normal döndürür.  
  
 Kod parçacığı alanı ayarı değiştirerek düzenlenebilir kod parçacığını alanları için varsayılan renkleri değiştirilebilir **yazı tiplerini ve renkleri** bölmesinde **seçeneği**s iletişim kutusu. Daha fazla bilgi için bkz: [nasıl yapılır: değişiklik yazı tiplerini ve renkleri Düzenleyicisi'nde](../ide/reference/how-to-change-fonts-and-colors-in-the-editor.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML parçacıkları](../xml-tools/xml-snippets.md)   
 [Nasıl yapılır: XML şemasından bir XML parçacığını oluştur](../xml-tools/how-to-generate-an-xml-snippet-from-an-xml-schema.md)   
 [Nasıl yapılır: XML parçacıkları oluşturma](../xml-tools/how-to-create-xml-snippets.md)