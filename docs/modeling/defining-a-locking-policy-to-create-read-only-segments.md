---
title: "Salt okunur segmentleri oluşturmak için bir kilitleme ilkesi tanımlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa549c71-2bf6-4b08-b7b2-7756dd6f1dc8
caps.latest.revision: "12"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 0ac8ba75920c4b3b8964d473258c162c256139ca
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="defining-a-locking-policy-to-create-read-only-segments"></a>Salt Okunur Kesimler Oluşturmak için Kilitleme İlkesi Tanımlama
Girişi API'si [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Görselleştirme ve modelleme SDK böylece okuma ancak değişmez bir programa kilit bölümünü veya tümünü bir etki alanına özgü dil (DSL) modeli sağlar. Bu salt okunur seçeneği, örneğin, böylece kullanıcı açıklama ve DSL modeli gözden geçirmek için iş arkadaşlarınızı isteyebilir, ancak bunları özgün değiştirmesini engellemek kullanılabilir.  
  
 Ayrıca, bir DSL yazarı olarak tanımlayan bir *İlkesi kilitleme.* Kilitleme ilkesi, hangi kilitleri izin verilen, izin verilmiyor veya zorunlu tanımlar. Örneğin, bir DSL yayımladığınızda, yeni komutları ile genişletmek için üçüncü taraf geliştiriciler öneririz. Ancak bunları model belirtilen bölümleri salt okunur durumunu değiştirilmesini önlemek için kilitleme ilkesi de kullanabilirsiniz.  
  
> [!NOTE]
>  Yansıma kullanarak bir kilitleme ilkesi atlatılabilir. Üçüncü taraf geliştiriciler için Temizle sınırını sağlar, ancak güçlü güvenlik sağlamaz.  
  
 Daha fazla bilgi ve örnekler adresinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] [Görselleştirme ve modelleme SDK](http://go.microsoft.com/fwlink/?LinkId=186128) Web sitesi.  

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
  
## <a name="setting-and-getting-locks"></a>Ayarlama ve kilit alınıyor  
 Kilit deposu, bir bölüm veya tek bir öğe ayarlayabilirsiniz. Örneğin, bu deyim bir model öğesi silinmesini engellemek ve değiştirilmesini özelliklerini de engeller:  
  
```  
using Microsoft.VisualStudio.Modeling.Immutability; ...  
element.SetLocks(Locks.Delete | Locks.Property);  
```  
  
 Diğer kilit değerleri ilişkileri, öğe oluşturma, bölümler ve bir rolü yeniden sıralama bağlantıları arasında hareket değişiklikleri önlemek için kullanılabilir.  
  
 Kilitler hem kullanıcı eylemleri ve program kodunu için geçerlidir. Program kodunda bir değişiklik yapmak çalışırsa bir `InvalidOperationException` oluşturulur. Kilitleri, bir geri alma veya yineleme işlemi göz ardı edilir.  
  
 Bir öğenin herhangi bir kilit belirtilen bir kümede kullanarak sahip olup olmadığını bulmak `IsLocked(Locks)` ve kullanarak bir öğeyi kilitler geçerli kümesini edinebilirsiniz `GetLocks()`.  
  
 Bir işlem kullanmadan bir kilit ayarlayabilirsiniz. Kilit veritabanını deponun bir parçası değil. Örneğin T:System.Windows.PropertyChangedCallback içinde bir kilit yanıt olarak bir değer, bir değişiklik deposunda ayarlarsanız, bir geri alma işlemi parçası olan değişiklik sağlamalıdır.  
  
 Bu yöntemler tanımlanan genişletme yöntemleri şunlardır <xref:Microsoft.VisualStudio.Modeling.Immutability> ad alanı.  
  
### <a name="locks-on-partitions-and-stores"></a>Bölümler kilitler ve depolar  
 Kilitleri, bölümler ve deposuna uygulanabilir. Bir bölüme ayarlanan kilit bölümündeki tüm öğelere uygulanır. Bu nedenle, örneğin, aşağıdaki deyim bir bölümdeki tüm öğeler, kendi kilitleri durumları yedeklemiş silinmesini önler. Bununla birlikte, diğer gibi kilitler `Locks.Property` hala ayrı ayrı öğeler üzerinde ayarlanabilir:  
  
```  
partition.SetLocks(Locks.Delete);  
```  
  
 Mağaza'olarak ayarlanmış bir kilit tüm öğeleri, bölümler ve öğeleri üzerindeki bu kilit ayarlarını bağımsız olarak uygulanır.  
  
### <a name="using-locks"></a>Kilitleri kullanma  
 Aşağıdaki örneklerde olduğu gibi düzenleri uygulamak için kilitleri kullanabilirsiniz:  
  
-   Tüm öğeleri ve ilişkileri açıklamaları temsil eden olanlar dışında değişiklikleri izin vermeyecek. Bu, kullanıcıların bir model değiştirmeden açıklama olanak tanır.  
  
-   Varsayılan bölümü değişikliklere izin vermeyecek ancak diyagramı bölümünde yapılan değişikliklere izin. Kullanıcı diyagram düzenleyebilir, ancak temel model değiştirilemiyor.  
  
-   Değişiklikleri ayrı bir veritabanında kayıtlı kullanıcılar grubunun hariç özelliği engelleyin. Diğer kullanıcılar için diyagram ve model salt okunurdur.  
  
-   Diyagramın bir Boolean özelliği ayarlanmışsa değişikliklere model izin vermeyecek true. Bu özelliği değiştirmek için menü komutu sağlar. Bu, hale kullanıcılar değişiklikleri yanlışlıkla sağlamaya yardımcı olur.  
  
-   Ekleme ve silme öğelerinin ve belirli sınıfları ilişkilerini engellemek, ancak özellik değişikliklerine izin. Bu kullanıcılar özellikleri doldurabilir için sabit bir form sağlar.  
  
## <a name="lock-values"></a>Kilit değerleri  
 Kilit deposu, bölüm veya tek tek model öğesi ayarlayabilirsiniz. Kilitleri olan bir `Flags` numaralandırma: kullanarak kendi değerlerini birleştirebilirsiniz ' &#124;'.  
  
-   Bir model öğesi kilitler her zaman kendi bölümünün kilitler ekleyin.  
  
-   Bir bölümün kilitleri her zaman deposunun kilitler ekleyin.  
  
 Bölüm üzerinde bir kilit ayarlayın veya depolamak ve aynı anda tek bir öğe üzerinde kilit devre dışı olamaz.  
  
|Değer|Yani `IsLocked(Value)` geçerlidir|  
|-----------|------------------------------------------|  
|Yok.|Kısıtlama yok.|  
|Özellik|Öğelerin etki alanı özellikleri değiştirilemez. Bu etki alanı sınıfının bir ilişkide rol tarafından oluşturulan özellikler için geçerli değil.|  
|Ekle|Yeni öğe ve bağlantıları, bir bölüm oluşturulamıyor veya depolar.<br /><br /> Uygulanamaz `ModelElement`.|  
|Taşıma|Öğesini, bölümleri arasında taşınamaz `element.IsLocked(Move)` doğrudur veya `targetPartition.IsLocked(Move)` doğrudur.|  
|Sil|Bir öğenin öğelerine hiçbirinde silme, katıştırılmış öğeleri ve şekiller gibi yayar veya bu kilit öğede ayarlandıysa silinemiyor.<br /><br /> Kullanabileceğiniz `element.CanDelete()` öğenin silinmiş olup olmadığını bulmak için.|  
|Yeniden sıralama|Bir roleplayer bağlantıları sıralama değiştirilemez.|  
|RolePlayer|Bu öğede kaynaklanan bağlantılar kümesi değiştirilemez. Örneğin, yeni öğeler altında bu öğe katıştırılmış olamaz. Bu öğe hedef olduğu bağlantılar etkilemez.<br /><br /> Bu öğe bir bağlantı olması durumunda, kaynak ve hedef etkilenmez.|  
|Tümü|Diğer değerlerin Bitsel veya.|  
  
## <a name="locking-policies"></a>Kilitleme ilkeleri  
 DSL yazar olarak tanımladığınız bir *İlkesi kilitleme*. Kilitleme ilkesi SetLocks(), işlem moderates, böylece belirli kilitleri ayarlamak veya belirli kilitleri ayarlanmalıdır zorunlu kılabilir olmasını engelleyebilir. Genellikle, kullanıcıların veya yanlışlıkla bir değişken bildirebilir aynı şekilde kullanım amacı bir DSL contravening gelen geliştiriciler önlemek için kilitleme ilkesi kullanırsınız `private`.  
  
 Kilitleme ilkesi, tüm öğelerde kilitleri öğenin türü bağımlı ayarlamak için de kullanabilirsiniz. Bunun nedeni, `SetLocks(Locks.None)` bir öğenin ilk oluşturulduğunda veya dosyasından serisi her zaman çağrılır.  
  
 Ancak, bir öğede kilitler ömrü sırasında değiştirmek için bir ilke kullanamazsınız. Bu etkiyi elde etmek için çağrıları kullanmalısınız `SetLocks()`.  
  
 Kilitleme ilkesi tanımlamak için için gerekenler:  
  
-   Arabirimini uygulayan bir sınıf oluşturun <xref:Microsoft.VisualStudio.Modeling.Immutability.ILockingPolicy>.  
  
-   Bu sınıf, DSL DocData kullanılabilir hizmetlerini ekleyin.  
  
### <a name="to-define-a-locking-policy"></a>Kilitleme ilkesi tanımlamak için  
 <xref:Microsoft.VisualStudio.Modeling.Immutability.ILockingPolicy>Aşağıdaki tanımı vardır:  
  
```  
public interface ILockingPolicy  
{  
  Locks RefineLocks(ModelElement element, Locks proposedLocks);  
  Locks RefineLocks(Partition partition, Locks proposedLocks);  
  Locks RefineLocks(Store store, Locks proposedLocks);  
}  
```  
  
 İçin bir çağrı yapılır bu yöntemleri çağırılır `SetLocks()` deposu, bölüm veya model öğesi. Her bir yöntemin, kilit önerilen bir dizi birlikte sağlanır. Önerilen kümesi döndürebilir veya ekleyin ve kilitleri çıkarın.  
  
 Örneğin:  
  
```  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Immutability;  
namespace Company.YourDsl.DslPackage // Change  
{  
  public class MyLockingPolicy : ILockingPolicy  
  {  
    /// <summary>  
    /// Moderate SetLocks(this ModelElement target, Locks locks)  
    /// </summary>  
    /// <param name="element">target</param>  
    /// <param name="proposedLocks">locks</param>  
    /// <returns></returns>  
    public Locks RefineLocks(ModelElement element, Locks proposedLocks)  
    {  
      // In my policy, users can never delete an element,  
      // and other developers cannot easily change that:  
      return proposedLocks | Locks.Delete);  
    }  
    public Locks RefineLocks(Store store, Locks proposedLocks)  
    {  
      // Only one user can change this model:  
      return Environment.UserName == "aUser"   
           ? proposedLocks : Locks.All;  
    }  
  
```  
  
 Diğer kod çağırır olsa bile kullanıcılar öğeleri, her zaman silebilir emin olmak için`SetLocks(Lock.Delete):`  
  
 `return proposedLocks & (Locks.All ^ Locks.Delete);`  
  
 MyClass her öğesinin tüm özelliklerinde değişiklik izin vermeyecek şekilde:  
  
 `return element is MyClass ? (proposedLocks | Locks.Property) : proposedLocks;`  
  
### <a name="to-make-your-policy-available-as-a-service"></a>İlkeniz hizmet olarak kullanılabilir hale getirmek  
 İçinde `DslPackage` projesi, aşağıdaki örneğe benzer bir kod içeren yeni bir dosya ekleyin:  
  
```  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Immutability;  
namespace Company.YourDsl.DslPackage // Change  
{   
  // Override the DocData GetService() for this DSL.  
  internal partial class YourDslDocData // Change  
  {  
    /// <summary>  
    /// Custom locking policy cache.  
    /// </summary>  
    private ILockingPolicy myLockingPolicy = null;  
  
    /// <summary>  
    /// Called when a service is requested.  
    /// </summary>  
    /// <param name="serviceType">Service requested</param>  
    /// <returns>Service implementation</returns>  
    public override object GetService(System.Type serviceType)  
    {  
      if (serviceType == typeof(SLockingPolicy)   
       || serviceType == typeof(ILockingPolicy))  
      {  
        if (myLockingPolicy == null)  
        {  
          myLockingPolicy = new MyLockingPolicy();  
        }  
        return myLockingPolicy;  
      }  
      // Request is for some other service.  
      return base.GetService(serviceType);  
    }  
}  
```
