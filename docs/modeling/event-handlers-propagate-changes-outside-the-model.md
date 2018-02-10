---
title: "Olay işleyicileri Model dışındaki değişiklikleri yaymak | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, programming domain models
- Domain-Specific Language, events
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 8b5c957fbc3ae5eb3e71f087c57cbf07188de2ff
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="event-handlers-propagate-changes-outside-the-model"></a>Değişiklikleri Modelin Dışına Yayan Olay İşleyicileri
Görselleştirme ve modelleme SDK, depolama olmayan değişkenleri, dosyaları, diğer depoları veya başka modellerinin gibi mağazasının dışında bir kaynağa değişiklikleri yaymak için depolama olay işleyicileri tanımlayabilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] uzantıları. Mağaza olay işleyicileri tetikleme olayın oluştuğu işlem sonunda yürütülür. Bunlar, ayrıca bir geri alma veya yineleme işlemi yürütülür. Bu nedenle, depolama kurallarından farklı olarak, depolama olayların deponun dışında olan değerleri güncelleştirmek için en kullanışlıdır. Bir sınıfa dinlemek için kayıtlı .NET olaylarının tersine deposu olay işleyicileri: her örneği için ayrı bir işleyici kaydetmeniz gerekmez. Değişiklikleri yürütmek için farklı yollar arasında seçim yapma hakkında daha fazla bilgi için bkz: [yanıtlama ve yayılıyor değişiklikleri](../modeling/responding-to-and-propagating-changes.md).  
  
 Grafik yüzeyi ve diğer kullanıcı arabirimi denetimlerini deposu olayları tarafından işlenebilir dış kaynaklara örnekleridir.  
  
### <a name="to-define-a-store-event"></a>Bir mağaza olayı tanımlamak için  
  
1.  İzlemek istediğiniz olay türünü seçin. Tam bir listesi için özelliklerine bakmak <xref:Microsoft.VisualStudio.Modeling.EventManagerDirectory>. Her bir özellik olay türüne karşılık gelir. En sık türler olay kullanılır:  
  
    -   `ElementAdded`-bir model öğesi harekete, ilişki bağlantısı, Şekil veya bağlayıcı oluşturulur.  
  
    -   ElementPropertyChanged - tetiklenen değerini bir `Normal` etki alanı özelliği değiştirildi. Yalnızca eski ve yeni değerler eşit değilse olay tetiklenir. Olay hesaplanan ve özel depolama özelliklerine uygulanamaz.  
  
         İlişki bağlantılar karşılık gelen rol özellikleri uygulanamaz. Bunun yerine, kullanın `ElementAdded` etki alanı ilişkisinin izlemek için.  
  
    -   `ElementDeleted`-bir model öğesi sonra tetiklenen, ilişki, Şekil veya bağlayıcı silinmiş olabilir. Öğesinin özellik değerlerini erişmeye devam edebilirsiniz, ancak hiçbir ilişki diğer öğelere sahip olur.  
  
2.  İçin bir parçalı sınıf tanımı eklemek *YourDsl *** DocData** ayrı kod dosyasında **DslPackage** projesi.  
  
3.  Aşağıdaki örnekte olduğu gibi bir yöntem olarak olay kodunu yazın. Bu olabilir `static`erişmek istediğiniz sürece `DocData`.  
  
4.  Geçersiz kılma `OnDocumentLoaded()` işleyici kaydetmek için. Birden fazla işleyici varsa, bunların tümü aynı yerde kaydedebilirsiniz.  
  
 Kayıt kodu konumunu kritik değildir. `DocView.LoadView()`Alternatif bir konum değil.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using Microsoft.VisualStudio.Modeling;  
  
namespace Company.MusicLib  
{  
  partial class MusicLibDocData  
  {  
    // Register store events here or in DocView.LoadView().  
    protected override void OnDocumentLoaded()  
    {  
      base.OnDocumentLoaded(); // Don't forget this.  
  
      #region Store event handler registration.       
      Store store = this.Store;  
      EventManagerDirectory emd = store.EventManagerDirectory;  
      DomainRelationshipInfo linkInfo = store.DomainDataDirectory  
          .FindDomainRelationship(typeof(ArtistAppearsInAlbum));  
      emd.ElementAdded.Add(linkInfo,   
          new EventHandler<ElementAddedEventArgs>(AddLink));  
      emd.ElementDeleted.Add(linkInfo,   
          new EventHandler<ElementDeletedEventArgs>(RemoveLink));  
  
      #endregion Store event handlers.  
    }  
  
    private void AddLink(object sender, ElementAddedEventArgs e)  
    {  
      ArtistAppearsInAlbum link = e.ModelElement as ArtistAppearsInAlbum;  
      if (link != null)   
            ExternalDatabase.Add(link.Artist.Name, link.Album.Title);  
    }  
    private void RemoveLink(object sender, ElementDeletedEventArgs e)  
    {  
      ArtistAppearsInAlbum link = e.ModelElement as ArtistAppearsInAlbum;  
      if (link != null)   
            ExternalDatabase.Delete(link.Artist.Name, link.Album.Title);  
    }  
  }  
  
}  
  
```  
  
## <a name="using-events-to-make-undoable-adjustments-in-the-store"></a>Depoda geri alınamaz ayarlamalar yapmak için olaylarını kullanma  
 İşlem kaydedildikten sonra olay işleyicisi yürüttüğünden deposu olayları normalde deposu içinde değişiklikleri yayılıyor için kullanılmaz. Bunun yerine, bir depolama kural kullanırsınız. Daha fazla bilgi için bkz: [kuralları yayılması değişiklikleri içindeki Model](../modeling/rules-propagate-changes-within-the-model.md).  
  
 Ancak, ek güncelleştirmeler özgün olayı ayrı olarak geri almak kullanıcı istiyorsanız deposuna ek güncelleştirmeler yapmak için bir olay işleyicisi kullanabilirsiniz. Örneğin, küçük harfler albüm başlıklarını için normal kuralı olduğunu varsayalım. Kullanıcı büyük harfle yazılmış sonra küçük harflere başlığı düzelten bir depolama olay işleyicisi yazabilirsiniz. Ancak, kullanıcı, düzeltme büyük harf karakter geri yüklemeyi iptal etmek için geri alma komutunu kullanabilirsiniz. İkinci bir geri alma kullanıcının değişiklik kaldırabilirsiniz.  
  
 Aynı şey yapmak için bir depolama kural yazdıysanız, böylece kullanıcı ayarlama özgün değişiklik kaybetmeden geri alamadı aksine, kullanıcının değişiklik ve düzeltmenizi aynı işlemde olacaktır.  
  
```  
  
partial class MusicLibDocView  
{  
    // Register store events here or in DocData.OnDocumentLoaded().  
    protected override void LoadView()  
    {  
      /* Register store event handler for Album Title property. */  
      // Get reflection data for property:  
      DomainPropertyInfo propertyInfo =   
        this.DocData.Store.DomainDataDirectory  
        .FindDomainProperty(Album.TitleDomainPropertyId);  
      // Add to property handler list:  
      this.DocData.Store.EventManagerDirectory  
        .ElementPropertyChanged.Add(propertyInfo,  
        new EventHandler<ElementPropertyChangedEventArgs>  
             (AlbumTitleAdjuster));  
  
      /*  
      // Alternatively, you can set one handler for   
      // all properties of a class.  
      // Your handler has to determine which property changed.  
      DomainClassInfo classInfo = this.Store.DomainDataDirectory  
           .FindDomainClass(typeof(Album));  
      this.Store.EventManagerDirectory  
          .ElementPropertyChanged.Add(classInfo,  
        new EventHandler<ElementPropertyChangedEventArgs>  
             (AlbumTitleAdjuster));  
       */  
      return base.LoadView();  
    }  
  
// Undoable adjustment after a property is changed.   
// Method can be static since no local access.  
private static void AlbumTitleAdjuster(object sender,  
         ElementPropertyChangedEventArgs e)  
{  
  Album album = e.ModelElement as Album;  
  Store store = album.Store;  
  
  // We mustn't update the store in an Undo:  
  if (store.InUndoRedoOrRollback   
      || store.InSerializationTransaction)  
      return;  
  
  if (e.DomainProperty.Id == Album.TitleDomainPropertyId)  
  {  
    string newValue = (string)e.NewValue;  
    string lowerCase = newValue.ToLowerInvariant();  
    if (!newValue.Equals(lowerCase))  
    {  
      using (Transaction t = store.TransactionManager  
            .BeginTransaction("adjust album title"))  
      {  
        album.Title = lowerCase;  
        t.Commit();  
      } // Beware! This could trigger the event again.  
    }  
  }  
  // else other properties of this class.  
}  
  
```  
  
 Bir olay yazarsanız deposu güncelleştirmelerinin:  
  
-   Kullanım `store.InUndoRedoOrRollback` geri alma modeli öğelerinde değişiklik yapmasını önlemek için. İşlem Yöneticisi, özgün durumuna geri deposundaki her şeyi ayarlarsınız.  
  
-   Kullanım `store.InSerializationTransaction` dosyasından model yüklenirken değişiklik yapmaktan kaçınmak için.  
  
-   Yaptığınız değişiklikler, daha fazla tetiklenmesi olayları neden olur. Sonsuz bir döngüde kaçının emin olun.  
  
## <a name="store-event-types"></a>Mağaza olay türleri  
 Her olay türü Store.EventManagerDirectory koleksiyonunda karşılık gelir. Ekleyip olay işleyicileri dilediğiniz zaman kaldırabilirsiniz, ancak belge yüklendiğinde bunları eklemek için normal.  
  
|`EventManagerDirectory`Özellik adı|Yürütülmesi|  
|-------------------------------------------|-------------------|  
|ElementAdded|Bir etki alanı sınıfı, etki alanı ilişkisinin, şekil, bağlayıcı veya diyagramı örneği oluşturulur.|  
|ElementDeleted|Bir model öğesi deponun öğesi Directory'den kaldırıldı ve artık kaynak ya da herhangi bir ilişki hedefi değil. Öğe gerçekte bellekten silinmez, ancak gelecekteki bir geri alma durumunda korunur.|  
|ElementEventsBegun|Bir dış işlem sonunda çağrılır.|  
|ElementEventsEnded|Tüm diğer olaylar işlendiğinde çağrılır.|  
|ElementMoved|Bir model öğesi başka bir depolama bölümünden taşındı.<br /><br /> Bu diyagramda bir şekli konumunu ilgili değildir.|  
|ElementPropertyChanged|Bir etki alanı özelliğinin değeri değiştirildi. Bu, yalnızca eski ve yeni değerler eşit ise yürütülür.|  
|RolePlayerChanged|Bir ilişkinin (uçları) iki rollerinden biri, yeni bir öğe başvurur.|  
|RolePlayerOrderChanged|1'den büyük çokluğa sahip bir roldeki bağlantılar sırası değişti.|  
|TransactionBeginning||  
|TransactionCommitted||  
|TransactionRolledBack||  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yanıt vermek ve değişiklikleri yayma](../modeling/responding-to-and-propagating-changes.md)   
 [Örnek kod: hattı diyagramları](http://code.msdn.microsoft.com/Visualization-Modeling-SDK-763778e8)
 
[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
 
