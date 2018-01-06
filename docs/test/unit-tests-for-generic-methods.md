---
title: "Genel yöntemler için birim testleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- generics, and unit tests
- unit tests, and generics
ms.assetid: ffc89814-a7df-44fc-aef5-dd3dfeb28a9b
caps.latest.revision: "47"
ms.author: douge
manager: douge
ms.workload: multiple
ms.openlocfilehash: 4e0afbcf6ff12376e3fcdf10925a20a4a7228130
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="unit-tests-for-generic-methods"></a>Genel Metotlar için birim testleri
Tam olarak, diğer yöntemleri için yaptığınız gibi açıklandığı gibi genel yöntemler için birim testleri oluşturabilir [nasıl yapılır: oluşturmak ve birim testi çalıştırma](http://msdn.microsoft.com/en-us/5e0f43cf-5e51-48e2-9c98-0eb9324bdc48). Aşağıdaki bölümler ve genel yöntemler için birim testleri oluşturma örnekler hakkında bilgi sağlar.  
  
## <a name="type-arguments-and-type-constraints"></a>Tür bağımsız değişkenleri ve tür kısıtlamaları  
 Zaman [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] gibi genel bir sınıf için bir birim testi oluşturur `MyList<T>`, iki yöntem oluşturur: Genel Yardımcısı ve test yöntemi. Varsa `MyList<T>` bir veya daha fazla tür kısıtlamaları vardır, tür bağımsız değişkeni tür kısıtlamaları karşılaması gerekir. Tüm izin verilen girişler için beklendiği gibi genel'ın altında test works kod emin olmak için test yöntemi test etmek istediğiniz tüm kısıtlamalarına sahip genel yardımcı yöntemini çağırır.  
  
## <a name="examples"></a>Örnekler  
 Aşağıdaki örneklerde genel türler için birim testleri gösterilmektedir:  
  
-   [Oluşturulan Test kodu düzenleme](#EditingGeneratedTestCode). Bu örnekte oluşturulan Test kod ve düzenlenebilir Test kodu olmak üzere iki bölümden oluşur. Genel yönteminden yararlı test yönteme oluşturulan ham test kodu düzenlemek nasıl gösterir.  
  
-   [Tür sınırlaması kullanarak](#TypeConstraintNotSatisfied). Bu örnek, bir tür sınırlaması kullanan bir genel yöntem için birim testi gösterir. Bu örnekte, tür sınırlaması gerçekleşmedi.  
  
###  <a name="EditingGeneratedTestCode"></a>Örnek 1: Oluşturulan Test kod düzenleme  
 Bu bölümdeki test kodu adlı bir kod altında test yöntemi testleri `SizeOfLinkedList()`. Bu yöntem bağlantılı listesinde düğüm sayısını belirten bir tamsayı döndürür.  
  
 Visual Studio kuruluş tarafından oluşturulan gibi ilk kod örneği bölümünde oluşturulan Test kodu düzenlenmemiş test kodu gösterir. Düzenlenen Test kodu bölümündeki ikinci örneği, iki farklı veri türleri için SizeOfLinkedList yöntemi çalışmasını test nasıl yapabilir gösterir `int` ve `char`.  
  
 Bu kod iki yöntem gösterilmektedir:  
  
-   bir test yardımcı yöntemi `SizeOfLinkedListTestHelper<T>()`. Varsayılan olarak, test yardımcı yöntemi "TestHelper" adına sahip.  
  
-   bir test yöntemi `SizeOfLinkedListTest()`. Her test yöntemi TestMethod özniteliği ile işaretlenir.  
  
#### <a name="generated-test-code"></a>Oluşturulan Test kodu  
 Aşağıdaki test kodunu kaynaklandığı `SizeOfLinkedList()` yöntemi. Bu düzenlenmemiş oluşturulan test olduğundan, doğru SizeOfLinkedList yöntemi test etmek için değiştirilmelidir.  
  
```  
public void SizeOfLinkedListTestHelper<T>()  
{  
    T val = default(T); // TODO: Initialize to an appropriate value  
    MyLinkedList<T> target = new MyLinkedList<T>(val); // TODO: Initialize to an appropriate value  
    int expected = 0; // TODO: Initialize to an appropriate value  
    int actual;  
    actual = target.SizeOfLinkedList();  
    Assert.AreEqual(expected, actual);  
    Assert.Inconclusive("Verify the correctness of this test method.");  
}  
  
[TestMethod()]  
public void SizeOfLinkedListTest()  
{  
   SizeOfLinkedListTestHelper<GenericParameterHelper>();  
}  
```  
  
 Genel tür parametresi önceki kodda olduğu `GenericParameterHelper`. Aşağıdaki örnekte gösterildiği gibi belirli veri türlerini sağlamak üzere düzenleyebilirsiniz ancak bu bildirimi düzenlemeden test çalışabilir.  
  
#### <a name="edited-test-code"></a>Sınama kodu düzenlenmiş  
 Aşağıdaki kodda test yöntemi ve test yardımcı yöntem bunları test test altında kod yöntemi başarıyla yapmak için düzenlendi `SizeOfLinkedList()`.  
  
##### <a name="test-helper-method"></a>Test yardımcı yöntemi  
 Test yardımcı yöntemi, adım 1'den 5 etiketli kodda satırlar karşılık gelen aşağıdaki adımları gerçekleştirir.  
  
1.  Genel bağlı bir liste oluşturur.  
  
2.  Dört düğüm bağlantılı listeye ekleyin. Bu düğümler içeriğini veri türü bilinmiyor.  
  
3.  Bağlantılı listesinin beklenen boyutu değişkenine atamak için `expected`.  
  
4.  Bağlantılı listesinin gerçek boyutu işlem ve değişkene atayın `actual`.  
  
5.  Karşılaştırma `actual` ile `expected` bir onay deyimi içinde. Gerçek beklenen için eşit değilse, sınama başarısız olur.  
  
##### <a name="test-method"></a>Test yöntemi  
 Test yöntemi SizeOfLinkedListTest adlı testi çalıştırdığınızda, çağrılan koda derlenir. Adım 6 ve 7. adım etiketli kodda satırlar karşılık gelen aşağıdaki adımları gerçekleştirir.  
  
1.  Belirtin `<int>` test için çalıştığını doğrulamak için test yardımcı yöntemini çağırdığınızda `integer` değişkenleri.  
  
2.  Belirtin `<char>` test için çalıştığını doğrulamak için test yardımcı yöntemini çağırdığınızda `char` değişkenleri.  
  
```  
  
public void SizeOfLinkedListTestHelper<T>()  
{  
    T val = default(T);   
    MyLinkedList<T> target = new MyLinkedList<T>(val); // step 1  
    for (int i = 0; i < 4; i++) // step 2  
    {  
        MyLinkedList<T> newNode = new MyLinkedList<T>(val);  
        target.Append(newNode);  
    }  
    int expected = 5; // step 3  
    int actual;  
    actual = target.SizeOfLinkedList(); // step 4  
    Assert.AreEqual(expected, actual); // step 5  
}  
  
[TestMethod()]  
public void SizeOfLinkedListTest()   
{  
    SizeOfLinkedListTestHelper<int>();  // step 6  
    SizeOfLinkedListTestHelper<char>(); // step 7  
}  
```  
  
> [!NOTE]
>  Her zaman SizeOfLinkedListTest test çalışmaları, kendi TestHelper yöntemi iki kez çağrılır. Onay deyimi geçirmek test için her zaman true olarak değerlendirmeniz gerekir. Sınama başarısız olursa, çağrı belirtilen olup olmadığını, açık olmayabilecek `<int>` veya belirtilen çağrı `<char>` başarısız olmasına neden. Yanıt bulmak için çağrı yığınını incelemek veya test yönteminde kesme noktalarını ayarlayın ve ardından test çalıştırılırken hata ayıklama. Daha fazla bilgi için bkz: [nasıl yapılır: ASP.NET çözümü'nde bir Test çalıştırılırken hata ayıklama](http://msdn.microsoft.com/Library/de4d7aa1-4a1e-467e-a19b-4a85ec245b8b).  
  
###  <a name="TypeConstraintNotSatisfied"></a>Örnek 2: bir tür sınırlaması kullanma  
 Bu örnek sağlanmıyorsa bir tür sınırlaması kullanan bir genel yöntem için birim testi gösterir. İlk bölüm kod altında test projesinin koddan gösterir. Tür sınırlaması vurgulanır.  
  
 İkinci bölümü test projesinin koddan gösterir.  
  
#### <a name="code-under-test-project"></a>Kod altında Test projesi  
  
```  
using System;  
using System.Linq;  
using System.Collections.Generic;  
using System.Text;  
  
namespace ClassLibrary2  
{  
    public class Employee  
    {  
        public Employee(string s, int i)  
        {  
        }  
    }  
  
    public class GenericList<T> where T : Employee  
    {  
        private class Node  
        {  
            private T data;  
            public T Data  
            {  
                get { return data; }  
                set { data = value; }  
            }  
        }  
    }  
}  
```  
  
#### <a name="test-project"></a>Test projesi  
 Tüm yeni oluşturulan birim testlerinde olduğu gibi yetersiz olmayan Assert deyimleri yararlı sonuçlar döndürebilir yapmak için bu birim testi eklemeniz gerekir. Bunları TestMethod özniteliğiyle işaretlenmiş yöntemi ancak bu test için adlı "TestHelper" yöntemini eklemeyin `DataTestHelper<T>()`.  
  
 Bu örnekte, genel tür parametresi `T` kısıtlamasına sahip `where T : Employee`. Bu kısıtlama test yöntemine gerçekleşmedi. Bu nedenle, `DataTest()` yöntemi üzerine yerleştirilen tür sınırlaması sağlamak için gereksinim uyarır bir onay deyimi içeren `T`. Bu onay deyimi ileti aşağıdaki gibidir:`("No appropriate type parameter is found to satisfies the type constraint(s) of T. " + "Please call DataTestHelper<T>() with appropriate type parameters.");`  
  
 Çağırdığınızda diğer bir deyişle, `DataTestHelper<T>()` test yöntemi yönteminden `DataTest()`, türünde bir parametre geçmelidir `Employee` veya türetilmiş bir sınıf `Employee`.  
  
 `using ClassLibrary2;`  
  
 `using Microsoft.VisualStudio.TestTools.UnitTesting;`  
  
 `namespace TestProject1`  
  
```  
{  
    [TestClass()]  
    public class GenericList_NodeTest  
    {  
  
        public void DataTestHelper<T>()  
            where T : Employee  
        {  
            GenericList_Shadow<T>.Node target = new GenericList_Shadow<T>.Node(); // TODO: Initialize to an appropriate value  
            T expected = default(T); // TODO: Initialize to an appropriate value  
            T actual;  
            target.Data = expected;  
            actual = target.Data;  
            Assert.AreEqual(expected, actual);  
            Assert.Inconclusive("Verify the correctness of this test method.");  
        }  
  
        [TestMethod()]  
        public void DataTest()  
        {  
            Assert.Inconclusive("No appropriate type parameter is found to satisfies the type constraint(s) of T. " +  
            "Please call DataTestHelper<T>() with appropriate type parameters.");  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birim testinin anatomisi](http://msdn.microsoft.com/en-us/a03d1ee7-9999-4e7c-85df-7d9073976144)   
 [Kodunuza Birim Testi Uygulama](../test/unit-test-your-code.md)
