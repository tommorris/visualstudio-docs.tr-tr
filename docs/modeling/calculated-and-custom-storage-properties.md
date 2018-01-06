---
title: "Hesaplanan ve özel depolama özellikleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, programming domain properties
ms.assetid: 42b785f9-2b0f-4f13-a6b4-246e5e0d477a
caps.latest.revision: "19"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: cf841cf70f092fb38adc42bfa6271c6c3aa121d1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="calculated-and-custom-storage-properties"></a>Hesaplanan ve Özel Depolama Özellikleri
Bir etki alanına özgü dil (DSL) tüm etki alanı özelliklerinde diyagramında ve dil Gezgini'nde kullanıcıya görüntülenen ve program kodu tarafından erişilebilir. Ancak, Özellikler değerlerine depolanan şekilde farklılık gösterir.  
  
## <a name="kinds-of-domain-properties"></a>Etki alanı özellikleri türleri  
 DSL tanımı'nda ayarladığınız **türü** özelliğinin aşağıdaki tabloda listelendiği gibi bir etki alanı:  
  
|Etki alanı özellik türü|Açıklama|  
|--------------------------|-----------------|  
|**Standart** (varsayılan)|Kaydedilen bir etki alanı özelliği *depolamak* ve dosyaya serileştirilmiş.|  
|**Hesaplanan**|Depoda kaydedilmez, ancak diğer değerler hesaplanan bir salt okunur etki alanı özelliği.<br /><br /> Örneğin, `Person.Age` gelen hesaplanması `Person.BirthDate`.<br /><br /> Hesaplama yapan kodunu girmeniz gerekir. Genellikle, diğer etki alanı özellikleri değerinden hesaplayın. Bununla birlikte, dış kaynaklara de kullanabilirsiniz.|  
|**Özel depolama**|Doğrudan deposunda kaydedilmez, ancak hem get hem de kümesi olabilir bir etki alanı özelliği.<br /><br /> Alma ve değeri ayarlayın yöntemleri sağlamanız gerekiyor.<br /><br /> Örneğin, `Person.FullAddress` alanında depolanacak `Person.StreetAddress`, `Person.City`, ve `Person.PostalCode`.<br /><br /> Ayrıca, örneğin değerlerini almak ve bir veritabanından ayarlamak dış kaynaklara erişebilir.<br /><br /> Kodunuzu değerleri deposunda ayarlamalısınız değil, `Store.InUndoRedoOrRollback` doğrudur. Bkz: [işlemleri ve özel ayarlayıcıları](#setters).|  
  
## <a name="providing-the-code-for-a-calculated-or-custom-storage-property"></a>Hesaplanmış veya özel depo özelliği için kod sağlama  
 Hesaplanmış veya özel depolama alanına bir etki alanı özelliğin türünü ayarlarsanız, erişim yöntemleri sağlamak için gerekir. Çözümünüzü yapılandırdığınızda, bir hata raporu gerekenden söyler.  
  
#### <a name="to-define-a-calculated-or-custom-storage-property"></a>Hesaplanmış veya özel depolama özelliğini tanımlamak için  
  
1.  Diyagram veya etki alanı özelliği DslDefinition.dsl içinde seçin **DSL Explorer**.  
  
2.  İçinde **özellikleri** penceresindeki ayarlayın **türü** alanı **hesaplanan** veya **özel depolama**.  
  
     Ayrıca ayarladığınızdan emin olun, **türü** istediğiniz.  
  
3.  Tıklatın **tüm şablonları dönüştürme** araç çubuğundaki **Çözüm Gezgini**.  
  
4.  Üzerinde **yapı** menüsünde tıklatın **yapı çözümü**.  
  
     Aşağıdaki hata iletisini alıyorsunuz: "*YourClass* Get için tanım içermiyor*YourProperty*."  
  
5.  Hata iletisini çift tıklatın.  
  
     Dsl\GeneratedCode\DomainClasses.cs veya DomainRelationships.cs açar. Vurgulanan yöntem çağrısı yorum Get için bir uygulama sunmak amacıyla ister*YourProperty*().  
  
    > [!NOTE]
    >  Bu dosya DslDefinition.dsl oluşturulur. Bu dosyayı düzenlerseniz, değişikliklerinizi tıklattığınız sonraki kaybolacağını **tüm şablonları dönüştürme**. Bunun yerine, gerekli yöntemi ayrı bir dosyaya ekleyin.  
  
6.  Oluşturma veya ayrı bir klasöre, örneğin da bir sınıf dosyası açma\\*YourDomainClass*. cs.  
  
     Ad alanı oluşturulan kod ile aynı olduğundan emin olun.  
  
7.  Sınıf dosyasında, etki alanı sınıfının bir kısmi uygulama yazmak. Eksik bir tanımı sınıfında yazma `Get` aşağıdaki örneğe benzer yöntemi:  
  
    ```  
    namespace Company.FamilyTree  
    {  public partial class Person  
       {  int GetAgeValue()  
          { return System.DateTime.Today.Year - this.BirthYear; }  
    }  }  
    ```  
  
8.  Ayarlarsanız **türü** için **özel depolama**, sağlamanız gerekecektir bir `Set` yöntemi. Örneğin:  
  
    ```  
    void SetAgeValue(int value)  
    { if (!Store.InUndoRedoOrRollback)  
        this.BirthYear =   
            System.DateTime.Today.Year - value; }  
    ```  
  
     Kodunuzu değerleri deposunda ayarlamalısınız değil, `Store.InUndoRedoOrRollback` doğrudur. Bkz: [işlemleri ve özel ayarlayıcıları](#setters).  
  
9. Derleme ve çözümü çalıştırın.  
  
10. Test özelliği. Deneyin olduğundan emin olun **geri** ve **Yinele**.  
  
##  <a name="setters"></a>İşlemler ve özel ayarlayıcıları  
 Yöntem genellikle etkin bir işlem çağrıldığı için özel depolama özellik kümesi yönteminde, bir işlem açmak zorunda değildir.  
  
 Ancak, ayarlama yöntemi kullanıcı geri alma veya yineleme çağırırsa ya da bir işlemi geri alınıyor çağrılabilir. Zaman <xref:Microsoft.VisualStudio.Modeling.Store.InUndoRedoOrRollback%2A> kümesi yönteminizi davranır gibi doğrudur:  
  
-   Bu değişiklikler diğer etki alanı özellikleri değerler atama deposundaki yapmamanız gerekir. Geri alma yöneticisi değerlerini ayarlar.  
  
-   Ancak, veritabanı veya dosya içeriğini veya mağaza dışına nesneleri gibi herhangi bir dış kaynağa güncelleştirmeniz gerekir. Bu bunlar içinde synchronism deposundaki değerlerle tutulduğundan emin olmanızı sağlar.  
  
 Örneğin:  
  
```  
void SetAgeValue(int value)  
{   
  // If we are in Undo, no changes to Store objects:  
  if (!this.Store.InUndoRedoOrRollback)  
  {   
    this.BirthYear = System.DateTime.Today.Year - value;   
  }  
  // But always update external objects:  
  System.IO.File.WriteAllText(AgeFile, value);  
}  
```  
  
 İşlemler hakkında daha fazla bilgi için bkz: [gezinme ve Program kodundaki bir modeli güncelleştirme](../modeling/navigating-and-updating-a-model-in-program-code.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gezinme ve bir modeli Program kodunda güncelleştirme](../modeling/navigating-and-updating-a-model-in-program-code.md)   
 [Etki alanı özelliklerini](../modeling/properties-of-domain-properties.md)   
 [Nasıl yapılır: Etki Alanına Özgü bir Dili Tanımlama](../modeling/how-to-define-a-domain-specific-language.md)