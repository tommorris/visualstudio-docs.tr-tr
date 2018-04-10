---
title: 'Nasıl yapılır: modeli güncelleştirmek için işlemleri kullanın | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: ecd9645bfb202d83bf672d03d3c6903a889677f9
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="how-to-use-transactions-to-update-the-model"></a>Nasıl yapılır: Modeli Güncelleştirmek için İşlemleri Kullanma
İşlemler deposuna yapılan değişiklikler bir grup olarak davranılır emin olun. Gruplandırılır değişiklikleri kaydedilmiş veya tek bir birim olarak geri alındı.  
  
 Her program kodunuzu değiştirir, ekler veya depoda herhangi bir öğeyi siler [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Görselleştirme ve modelleme SDK, bir işlem içinde bunu yapmalısınız. Etkin bir örneği olmalıdır <xref:Microsoft.VisualStudio.Modeling.Transaction> değişiklik olduğunda deposuyla ilişkili. Bu, tüm model öğelerini, ilişkileri, şekiller, diyagramları ve bunların özelliklerini için geçerlidir.  
  
 İşlem mekanizması tutarsız durumları önlemenize yardımcı olur. İşlem sırasında bir hata oluşursa, tüm değişiklikler geri alınır. Kullanıcı bir geri alma komut gerçekleştirirse, her son işlem tek bir adım kabul edilir. Açıkça bunları ayrı işlemlerde yerleştirdiğiniz sürece kullanıcı son zamanlarda bir değişiklik bölümlerini geri alamazsınız.  
  
## <a name="opening-a-transaction"></a>Bir işlem açma  
 Bir işlem yönetme en kolay yöntem olan bir `using` deyimi içine bir `try...catch` deyimi:  
  
```  
Store store; ...  
try  
{  
  using (Transaction transaction =  
    store.TransactionManager.BeginTransaction("update model"))  
    // Outermost transaction must always have a name.  
  {  
    // Make several changes in Store:  
    Person p = new Person(store);  
    p.FamilyTreeModel = familyTree;  
    p.Name = "Edward VI";  
    // end of changes to Store  
  
    transaction.Commit(); // Don't forget this!  
  } // transaction disposed here  
}  
catch (Exception ex)  
{  
  // If an exception occurs, the Store will be   
  // rolled back to its previous state.  
}  
```  
  
 En son engelleyen bir özel durum, `Commit()` deposu önceki durumuna geri sıfırlanacağı değişiklikleri sırasında oluşur. Bu, hataları modeli tutarsız bir durumda bırakmadığından emin olun yardımcı olur.  
  
 Herhangi bir sayıda bir işlem içinde değişiklikleri yapabilirsiniz. Yeni bir işlem etkin bir işlem içinde açabilirsiniz. İç içe geçmiş işlemler yürütün veya içeren işlem sona ermeden önce geri alma. Daha fazla bilgi için örnek için bkz: <xref:Microsoft.VisualStudio.Modeling.Transaction.TransactionDepth%2A> özelliği.  
  
 Değişikliklerinizi kalıcı yapmak için şunları yapmalısınız `Commit` bırakılana önce işlem. İşlem içinde yakalandı bir özel durum oluşursa, deposu değişiklikleri önce durumuna sıfırlar.  
  
## <a name="rolling-back-a-transaction"></a>Bir işlemi geri alınıyor  
 Mağaza kalır veya işlem önce durumuna döner emin olmak için bu taktiği birini kullanabilirsiniz:  
  
1.  İşlem kapsamı içinde yakalandı bir özel durum yükseltin.  
  
2.  Açıkça işlem geri alma:  
  
    ```  
    this.Store.TransactionManager.CurrentTransaction.Rollback();  
    ```  
  
## <a name="transactions-do-not-affect-non-store-objects"></a>İşlemler deposu olmayan nesneleri etkilemez  
 İşlemler yalnızca deposu durumunu yönetir. Bunlar, dosya, veritabanları veya DSL tanımının dışında sıradan türleriyle bildirilen nesneleri gibi dış öğelerine yapılan kısmi değişiklikleri geri alamazsınız.  
  
 Bir özel durum bu tür bir değişiklik deposuyla tutarsız bırakırsanız, bu olasılığı özel durum işleyici olarak çalışılabilecek. Dış kaynaklara deposu nesneler ile eşitlenmiş kalmasını emin olmak için bir olay işleyicilerini kullanarak bir mağazadaki öğeye her dış nesne eşleştiği yoldur. Daha fazla bilgi için bkz: [olay işleyicileri yayılması değişiklikleri dışında modeli](../modeling/event-handlers-propagate-changes-outside-the-model.md).  
  
## <a name="rules-fire-at-the-end-of-a-transaction"></a>Bir işlem sonunda kuralları yangın  
 İşlem atılmadan önce bir işlem sonunda deposundaki öğelere eklenen kurallar tetiklenir. Her kural değişen bir model öğeye uygulanan bir yöntemdir. Örneğin, model öğesi değiştiğinde bir şekli durumunu güncelleştir "Düzelt" kuralları vardır ve bir model öğesi oluşturulduğunda, bir şekil oluşturun. Hiçbir belirtilen tetikleme sırasını yoktur. Bir kural tarafından yapılan bir değişikliği, başka bir kural tetikleyebilir.  
  
 Kendi kurallarınızı tanımlayabilirsiniz. Kuralları hakkında daha fazla bilgi için bkz: [yanıtlama ve yayılıyor değişiklikleri](../modeling/responding-to-and-propagating-changes.md).  
  
 Kurallar, bir geri alma, bir yineleme veya geri alma komut sonrasında başlatılmaz.  
  
## <a name="transaction-context"></a>İşlem bağlamı  
 Her işlem, istediğiniz herhangi bir bilgi depolamak bir sözlük sahiptir:  
  
 `store.TransactionManager`  
  
 `.CurrentTransaction.TopLevelTransaction`  
  
 `.Context.Add(aKey, aValue);`  
  
 Bu kural arasında bilgi aktarmak için kullanışlıdır.  
  
## <a name="transaction-state"></a>İşlem durumu  
 Değişiklik nedeni geri alma veya bir işlem yineleme varsa önlemek için gereken bazı durumlarda bir değişiklik yayılıyor. Başka bir değer deposunda güncelleştirebilirsiniz bir özellik değeri işleyicisi yazma, örneğin, gerçekleşebilir. Geri alma işlemi önceki durumlarına deponun tüm değerleri sıfırlar olduğundan, güncelleştirilmiş değerleri hesaplamak gerekli değildir. Bu kodu kullanın:  
  
```  
if (!this.Store.InUndoRedoOrRollback) {...}  
```  
  
 Deponun bir dosyadan başlangıçta yüklenirken kuralları tetikleyebilir. Bu değişikliklere yanıt verme önlemek için kullanın:  
  
```  
if (!this.Store.InSerializationTransaction) {...}  
  
```