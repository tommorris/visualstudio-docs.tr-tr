---
title: "Onay sınıfları kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Assert classes
- Assert statements
- unit tests, Assert statements
- unit tests, Assert classes
ms.assetid: da1b7a0d-4f1d-4d50-a07e-7b3ff60053f9
caps.latest.revision: "27"
ms.author: douge
manager: douge
ms.openlocfilehash: 443c3fe0ece064993655895606ad8603b96f6286
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="using-the-assert-classes"></a>Onay Sınıfları Kullanma
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting>   
 [Oluşturma ve var olan kod için birim testleri çalıştırma](http://msdn.microsoft.com/en-us/e8370b93-085b-41c9-8dec-655bd886f173)
