---
title: Birim Visual Studio'da Test etmek için onay sınıfları kullanma | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: article
helpviewer_keywords:
- Assert classes
- Assert statements
- unit tests, Assert statements
- unit tests, Assert classes
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: d9c6e2b62a32771b02c3244984eb8a59e2513635
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="use-the-assert-classes"></a>Onay sınıfları kullanma

Onay sınıfları UnitTestingFramework ad alanının belirli işlevselliğini doğrulamak için kullanın. Birim testi yöntemine geliştirme kodunuzu yönteminde kod uygular ancak yalnızca Assert deyimleri eklerseniz kodun davranışı doğruluğunu bildiriyor.

## <a name="kinds-of-asserts"></a>Tür, onaylar
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting> Ad alanı, çeşitli türlerde onay sınıfları sağlar:

 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>

 Assert sınıfının Assert.AreEqual() gibi yöntemlerini herhangi bir sayıda test yönteminize çağırabilirsiniz. Assert sınıfı aralarından seçim yapabileceğiniz birçok yöntem ve bu yöntemleri çoğunu birçok aşırı yüklemeye sahip.

 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.CollectionAssert>

 CollectionAssert sınıfı nesne koleksiyonları Karşılaştırılacak ve bir veya daha fazla koleksiyon durumunu doğrulamak için kullanın.

 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert>

 StringAssert sınıfı, dizeleri karşılaştırmak için kullanın. Bu sınıf, çeşitli StringAssert.Contains, StringAssert.Matches ve StringAssert.StartsWith gibi kullanışlı yöntemler içerir.

 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssertFailedException>

 Bir test başarısız olduğunda AssertFailedException özel durum oluşur. Zaman aşımına uğradı, beklenmeyen bir özel durum oluşturur veya başarısız sonucu üreten bir onay deyimi içeren bir sınama başarısız olur.

 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssertInconclusiveException>

 Bir test Inconclusive sonucunu üreten her AssertInconclusiveException atılır. Genellikle, bir Assert.Inconclusive deyimi hala henüz çalıştırılmaya hazır değil belirtmek için çalışmakta olduğunuz bir test ekleyin.

> [!NOTE]
>  Alternatif bir strateji Ignore özniteliği ile çalıştırmak hazır değil bir test işaretlemek için olur. Ancak, bu kolayca uygulamak üzere bıraktıysanız sınamaların sayısı raporda üretilemiyor olumsuz sahiptir.

 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.UnitTestAssertException>

 Yeni bir Assert özel durum sınıfı yazarsanız, UnitTestAssertException taban sınıftan devralın o sınıfın sahip özel bir onaylama işlemi hatasına yerine test veya üretim kodunuzdan durum beklenmeyen bir özel durum olarak tanımlamak kolaylaştırır.

 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ExpectedExceptionAttribute>

 Geliştirme kodunuzda yöntemi tarafından oluşturulan beklediğiniz gerçekten bu yöntemi özel durum olduğunu doğrulamak için test yöntemi istediğinizde bir test yöntemi ExpectedExceptionAttribute özniteliği ile işaretleme.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting>
- [Birim testi kodunuz](../test/unit-test-your-code.md)
