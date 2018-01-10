---
title: "En iyi uygulamalar için kodlanmış UI testleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: coded UI tests, best practices
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: faeaa6aaa6902e35e0b878bda91609ca12dbf248
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
---
# <a name="best-practices-for-coded-ui-tests"></a>Kodlanmış UI Testleri için En İyi Yöntemler
Bu konu kodlanmış UI testleri geliştirirken izlemek için en iyi uygulamaları açıklar.  
  
 **Gereksinimler**  
  
-   Visual Studio Enterprise  
  
## <a name="best-practices"></a>En İyi Yöntemler  
 Esnek bir kodlanmış UI testi oluşturmak için aşağıdaki kılavuzları kullanın.  
  
-   Kullanım **kodlanmış UI Test derleyicisini** mümkün olduğunda.  
  
-   Değişiklik yapmayın `UIMap.designer.cs` dosyasını doğrudan. Bunu yaparsanız, değişiklikleri dosyaya yazılır.  
  
-   Testinizi kaydedilen yöntemler dizisi olarak oluşturun. Bir yöntem kayıt hakkında daha fazla bilgi için bkz: [kodlanmış UI testleri oluşturma](../test/use-ui-automation-to-test-your-code.md#VerifyingCodeUsingCUITCreate).  
  
-   Kaydedilen her yöntem, tek sayfa, form veya iletişim kutusu üzerinde işlem yapmalıdır. Her yeni sayfa, form veya iletişim kutusu için yeni bir test yöntemi oluşturun.  
  
-   Bir yöntem oluştururken anlamlı bir yöntem adı yerine varsayılan adı kullanın. Anlamlı bir ad yöntemin amacını tanımlamaya yardım eder.  
  
-   Mümkün olduğunda, kaydedilen her yöntem 10'dan az eylemlerine sınırlayın. Modüler bu yaklaşım UI değişirse bir yöntemini değiştirmek kolaylaştırır.  
  
-   Her onaylama kullanarak oluşturduğunuz **kodlanmış UI Test derleyicisini**, bu da otomatik olarak ekler bir onay yöntemi `UIMap.Designer.cs` dosya.  
  
-   Kullanıcı Arabirimi (UI) değişirse, test yöntemleri veya onay yöntemlerini yeniden kaydedin veya varolan bir test yönteminin etkilenen bölümlerini yeniden kaydedin.  
  
-   Ayrı bir oluşturma <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap> her test altındaki uygulamanızı modülde dosyası. Daha fazla bilgi için bkz: [birden çok UI eşlemesi bulunan büyük uygulamaları sınama](../test/testing-a-large-application-with-multiple-ui-maps.md).  
  
-   Kullanıcı Arabirimi denetimlerini oluşturduğunuzda test uygulamada anlamlı adlar kullanın. Bu, otomatik olarak oluşturulan denetim adları daha fazla anlam ve kullanılabilirlik sağlar.  
  
-   API ile kodlayarak onaylar oluşturuyorsanız, parçasında her onay için bir yöntem oluşturma <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap> sınıfının `UIMap.cs` dosya. Bu yöntem, onaylama işlemi yürütmek için test yöntemi çağırın.  
  
-   Doğrudan API ile kodlama yapıyorsanız, özellikleri ve yöntemleri oluşturulan sınıfların kullanmak `UIMap.Designer.cs` , olabildiğince kodunuzda dosya. Bu sınıfların çalışmanızı yapacak daha kolay ve daha güvenilir ve daha üretken olmanıza yardımcı olur.  
  
 Kodlanmış UI testleri, kullanıcı arabiriminde birçok değişiklikler otomatik olarak uyarlayın. Örneğin, bir kullanıcı Arabirimi öğesi konum veya renk değiştiyse, çoğu zaman kodlanmış UI testi yine doğru öğeyi bulur.  
  
 Testi sırasında bir dizi tarafından oluşturulan tanımlarında her denetim sınıfına uygulanan arama özellikleri kullanarak UI denetimleri test çerçevesi tarafından bulunan **kodlanmış UI Test oluşturucusunu** içinde `UIMap.Designer.cs` dosya. Arama özellikleri özellik adları ve denetim gibi tanımlamak için kullanılan özellik değerlerini ad-değer çiftleri içeren <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.FriendlyName%2A>, <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.Name%2A>, ve <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.ControlType%2A> denetiminin özellikleri. Arama özellikleri değişmeden varsa, kodlanmış UI testi denetimi kullanıcı Arabiriminde başarıyla bulun. Arama özellikleri değiştirilirse, kodlanmış UI testleri denetimleri ve windows kullanıcı Arabiriminde bulmak için buluşsal yöntemler uyguladığı bir akıllı eşleşme algoritması bulunur. UI değiştiğinde, bunlar bulunduğundan emin olmak için önceden tanımlanmış öğelerin arama özelliklerini değiştirmek mümkün olabilir.  
  
## <a name="what-to-do-if-your-user-interface-changes"></a>Kullanıcı arabiriminiz değişirse yapmanız gerekenler  
 Kullanıcı arabirimleri sık geliştirme sırasında değiştirin. Bu değişikliklerin etkisini azaltmak için bazı yöntemler şunlardır:  
  
-   Bu denetim ve kullanım başvuran kayıtlı yöntemi bulun **kodlanmış UI Test derleyicisini** bu yöntem için eylemleri yeniden kaydetmek için. Varolan eylemlerin üzerine yazma yöntemi için aynı adı kullanabilirsiniz.  
  
-   Bir denetimin artık geçerli olmayan bir onaylama varsa:  
  
    -   Onaylamayı içeren yöntemi silin.  
  
    -   Bu yöntem çağrısı test yönteminden kaldırın.  
  
    -   Yeni bir onaylama çapraz hedef düğmesini UI denetiminin üzerine sürükleyerek ekleyin, UI haritasını açın ve yeni onayı ekleyin.  
  
 Kodlanmış UI testlerini nasıl kaydedileceği hakkında daha fazla bilgi için bkz: [kullanım UI Otomasyon için Test kodunuzu](../test/use-ui-automation-to-test-your-code.md).  
  
## <a name="what-to-do-if-a-background-process-needs-to-complete-before-the-test-can-continue"></a>Bir arka plan işlemi test devam etmeden önce tamamlanması gerekiyorsa yapmanız gerekenler  
 Sonraki UI eylemiyle devam etmeden önce bir işlem sonlanana kadar beklemeniz gerekebilir. Kullanabileceğiniz bunun için <xref:Microsoft.VisualStudio.TestTools.UITesting.PlaybackSettings.WaitForReadyLevel%2A> aşağıdaki örnekte olduğu gibi test devam etmeden önce beklenecek.  
  
```  
// Set the playback to wait for all threads to finish  
Playback.PlaybackSettings.WaitForReadyLevel = WaitForReadyLevel.AllThreads;  
  
// Press the submit button  
this.UIMap.ClickSubmit();  
  
// Reset the playback to wait only for the UI thread to finish  
Playback.PlaybackSettings.WaitForReadyLevel = WaitForReadyLevel.UIThreadOnly;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap>   
 <xref:Microsoft.VisualStudio.TestTools.UITesting>   
 [Kodunuzu test etmek için UI otomasyonunu kullanma](../test/use-ui-automation-to-test-your-code.md)   
 [Kodlanmış UI testleri oluşturma](../test/use-ui-automation-to-test-your-code.md#VerifyingCodeUsingCUITCreate)   
 [Birden çok UI eşlemesi bulunan büyük uygulamaları sınama](../test/testing-a-large-application-with-multiple-ui-maps.md)   
 [Kodlanmış UI Testleri ve Eylem Kayıtları için Desteklenen Yapılandırmalar ve Platformlar](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)
