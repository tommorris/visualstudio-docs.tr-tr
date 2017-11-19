---
title: "Bir etki alanına özgü dil kişiselleştirmek için kod yazma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, programming
ms.assetid: a4a17f5b-9c97-4575-b2d1-3182c1896b72
caps.latest.revision: "29"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 2d456f84078e54694deb11fda0082ac40d278dd2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="writing-code-to-customise-a-domain-specific-language"></a>Etki Alanına Özgü Dili Özelleştirmek için Kod Yazma
Bu bölümde özel kod erişim, değiştirme veya bir etki alanına özgü dil bir model oluşturmak için nasıl kullanılacağını gösterir.  
  
 DSL ile çalışan kod yazabilirsiniz birkaç bağlamları vardır:  
  
-   **Özel komutlar.** Kullanıcıların Diyagramı sağ tıklayarak çağırabileceği ve hangi model değiştirebilirsiniz bir komutu kullanabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: bir komut için kısayol menüsü ekleme](../modeling/how-to-add-a-command-to-the-shortcut-menu.md).  
  
-   **Doğrulama.** Model doğru bir durumda olduğunu doğrular kod yazabilirsiniz. Daha fazla bilgi için bkz: [bir etki alanına özgü dil doğrulama](../modeling/validation-in-a-domain-specific-language.md).  
  
-   **Varsayılan davranışı geçersiz kılma.** Birçok yönünü DslDefinition.dsl oluşturulan kodu değiştirebilirsiniz. Daha fazla bilgi için bkz: [geçersiz kılma ve oluşturulan sınıflar genişletme](../modeling/overriding-and-extending-the-generated-classes.md).  
  
-   **Metin dönüştürmeyi.** Bir model erişir ve bu örneğin program kodu oluşturmak bir metin dosyası oluşturur kodu içeren metin şablonları yazabilirsiniz. Daha fazla bilgi için bkz: [bir etki alanına özgü dil oluşturma koddan](../modeling/generating-code-from-a-domain-specific-language.md).  
  
-   **Diğer Visual Studio uzantıları.** Modelleri okumak ve değiştirmek ayrı VSIX uzantıları yazabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: Program kodundaki dosyasından bir Model açın](../modeling/how-to-open-a-model-from-file-in-program-code.md)  
  
 İçinde DslDefinition.dsl tanımlayan sınıflar örneklerini adlı bir veri yapısında tutulur *bellek içi deposu* (IMS) veya *deposu*. Her zaman bir DSL tanımlayın sınıfları mağaza oluşturucuya bağımsız değişken olarak alın. Örneğin, DSL örnek adlı bir sınıf tanımlar:  
  
 `Example element = new Example (theStore);`  
  
 nesneler (yerine yalnızca olarak normal nesneler) deposunda tutmak birkaç avantaj sağlar.  
  
-   **İşlemler**. Bir dizi ilgili değişikliği bir hareket halinde gruplayabilirsiniz.  
  
     `using (Transaction t = store.TransactionManager.BeginTransaction("updates"))`  
  
     `{`  
  
     `// make several changes to Store elements here`  
  
     `t.Commit();`  
  
     `}`  
  
     Bir özel durum değişiklikleri sırasında oluşursa, böylece son Commit() gerçekleştirilemiyor Store önceki durumuna geri sıfırlanır. Bu, hataları modeli tutarsız bir durumda bırakmadığından emin olmak için yardımcı olur. Daha fazla bilgi için bkz: [gezinme ve Program kodundaki bir modeli güncelleştirme](../modeling/navigating-and-updating-a-model-in-program-code.md).  
  
-   **İkili ilişkileri**. İki sınıf arasında bir ilişki tanımlamak, her iki örnek diğer uçtaki gider bir özelliği vardır. İki ucu her zaman eşitlenir. Örneğin, üst ve alt öğeleri adlı rolleriyle parenthood ilişki tanımlarsanız yazabilirsiniz:  
  
     `John.Children.Add(Mary)`  
  
     Aşağıdaki ifadeler her ikisi de true sunulmuştur:  
  
     `John.Children.Contains(Mary)`  
  
     `Mary.Parents.Contains(John)`  
  
     Aynı sonucu elde yazarak:  
  
     `Mary.Parents.Add(John)`  
  
     Daha fazla bilgi için bkz: [gezinme ve Program kodundaki bir modeli güncelleştirme](../modeling/navigating-and-updating-a-model-in-program-code.md).  
  
-   **Kurallar ve olayları**. Belirtilen değişiklik yapıldığında, yangın kurallar tanımlayabilirsiniz. Kurallar, örneğin, Şekil diyagramı bunlar sunmak model öğelerini ile güncel tutmak için kullanılır. Daha fazla bilgi için bkz: [yanıtlama ve yayılıyor değişiklikleri](../modeling/responding-to-and-propagating-changes.md).  
  
-   **Seri hale getirme**. Deponun bir dosyaya içindeki nesneleri serileştirmek için standart bir yol sağlar. Seri hale getirme ve seri durumdan kuralları özelleştirebilirsiniz. Daha fazla bilgi için bkz: [özelleştirme dosya depolama ve XML serileştirme](../modeling/customizing-file-storage-and-xml-serialization.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özelleştirme ve bir etki alanına özgü dil genişletme](../modeling/customizing-and-extending-a-domain-specific-language.md)