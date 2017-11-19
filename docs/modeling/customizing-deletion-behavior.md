---
title: "Silme davranışı özelleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.dsltools.dsldesigner.deletebehavior
helpviewer_keywords: Domain-Specific Language, deletion
ms.assetid: c6bf088d-52c6-4817-af45-ddae745bb5a9
caps.latest.revision: "23"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 159d6a7b3a381eeb5d6f92154e657de67c567a38
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="customizing-deletion-behavior"></a>Silme Davranışını Özelleştirme
Bir öğe genellikle silinmesi, ilgili öğeler de silinecek neden olur. Tüm ilişkiler ona bağlı ve herhangi bir alt öğe silindi. Bu davranış adlı *yayma silme*. Örneğin ek ilgili öğeler silinir düzenlemek silme yayma özelleştirebilirsiniz. Program kodunda yazarak delete yayma model durumuna bağlıdır yapabilirsiniz. Bir silme işlemi için yanıt gerçekleşmesi diğer değişiklikler de neden olabilir.  
  
 Bu konu aşağıdaki bölümleri içermektedir:  
  
-   [Varsayılan silme davranışı](#default)  
  
-   [Bir rolün yayılması Sil seçeneğini ayarlama](#property)  
  
-   [Silme Kapatılmak üzere geçersiz kılma](#closure) -silme öğeleri komşu silme işlemini burada açabilecek bu tekniği kullanın.  
  
-   [OnDeleting ve OnDeleted kullanarak](#ondeleting) -yanıtı veya mağaza dışındaki bir değer güncelleştirme gibi diğer eylemler burada içerebilir bu yöntemleri kullanın.  
  
-   [Silme kuralları](#rules) -güncelleştirmeleri nerede bir değişiklik sağlama başkalarına deposundaki herhangi bir türde yayılması için kuralları kullanın.  
  
-   [Silme olaylarını](#rules) -güncelleştirmelerini mağazaya, örneğin diğer dışında yaymak için kullanım deposu olayları [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] belgeleri.  
  
-   [Birleştirme](#unmerge) -bir alt öğesi kendi üst bağlı birleştirme işlemi geri almak için birleştirme işlemi kullanın.  
  
##  <a name="default"></a>Varsayılan silme davranışı  
 Varsayılan olarak, aşağıdaki kurallar delete yayma kapsar:  
  
-   Bir öğenin silinirse, tüm katıştırılmış öğeleri de silinir. Katıştırılmış bu öğe kaynağı olduğu ilişkileri katıştırma hedefleri olan öğelerdir. Örneğin, bir katıştırma ilişkiden ise **albüm** için **şarkı**, belirli bir albümü silindiğinde, tüm şarkıya de silinir.  
  
     Bunun aksine, bir şarkıyı silme albümü silmez.  
  
-   Varsayılan olarak, silme işlemi başvuru ilişkileri dağıtılmaz. Başvuru ilişkisi ise **ArtistPlaysOnAlbum** gelen **albüm** için **sanatçı**, albüm silinmesi tüm ilgili sanatçı silmez ve sanatçı silme yok Tüm albüm silin.  
  
     Ancak, silme bazı yerleşik ilişkiler yayılır. Örneğin, bir model öğesi silindiğinde, diyagramda şeklini de silinir. Öğe ve şekli ile ilişkilendirilen `PresentationViewsSubject` başvuru ilişkisi.  
  
-   Öğesine da kaynak veya hedef rolü bağlı her ilişki silinir. Ters rol öğede rol özelliği artık silinen öğe içeriyor.  
  
##  <a name="property"></a>Bir rolün yayılması Sil seçeneğini ayarlama  
 Başvuru ilişkisi boyunca veya katıştırılmış bir alt öğe üst yaymak silme işlemi neden olabilir.  
  
#### <a name="to-set-delete-propagation"></a>Delete yayma ayarlamak için  
  
1.  DSL tanımı diyagramda seçin *rol* yayma silmek istediğiniz. Rol satırı sol veya bir etki alanı ilişki kutusunun sağ tarafından temsil edilir.  
  
     Örneğin, albüm silindiğinde belirtmek istiyorsanız, ilgili Sanatçılar da silinir, sonra etki alanı sınıfı sanatçı bağlı rol seçin.  
  
2.  Özellikler penceresinde ayarlayın **yayar silme** özelliği.  
  
3.  F5 tuşuna basın ve doğrulayın:  
  
    -   Bu ilişki örneği silindiğinde, seçili rol öğesi de silinir.  
  
    -   Bir öğede karşıt rolü silindiğinde, bu ilişki örnekleri silinir ve ilgili öğeleri Bu roldeki silinir.  
  
 Ayrıca bkz **yayar silme** seçeneğini **DSL ayrıntıları** penceresi. Bir etki alanı sınıfı seçin ve DSL Ayrıntılar penceresi açın **silme davranışı** penceresi tarafındaki düğmesini tıklatarak sayfa. **Propagate** seçeneği her ilişki için ters rolü gösterilir. **Stili Sil'i** sütununda olup olmadığını **Propagate** seçeneği, varsayılan ayarı, ancak ayrı hiçbir etkisi yoktur.  
  
## <a name="delete-propagation-by-using-program-code"></a>Program kodunu kullanarak yayma silme  
 DSL tanım dosyasındaki seçenekleri, yalnızca silme işlemi için hemen bir komşu yayar olup olmadığını seçmenize izin verir. Daha karmaşık bir delete yayma düzenini uygulamak için program kodu yazabilirsiniz.  
  
> [!NOTE]
>  Program kodunu DSL tanımınızı eklemek için ayrı kod dosyasında oluşturma **Dsl** proje ve oluşturulan kod klasörü sınıflarda büyütmek için kısmi tanımları yazma. Daha fazla bilgi için bkz: [bir etki alanına özgü dil kişiselleştirmek için kod yazma](../modeling/writing-code-to-customise-a-domain-specific-language.md).  
  
##  <a name="closure"></a>Bir silme kapanışı tanımlama  
 Silme işlemi sınıfını kullanır *YourModel***DeleteClosure** , bir başlangıç seçimi silmek için hangi öğelerin belirlemek için. Çağırır `ShouldVisitRelationship()` ve `ShouldVisitRolePlayer()` tekrar tekrar ilişkileri grafik taramasını. Bu yöntemleri geçersiz kılabilirsiniz. ShouldVisitRolePlayer bir bağlantı ve bağlantının rollerinden birini konumundaki öğe kimliği ile birlikte sağlanır. Aşağıdaki değerlerden birini döndürmesi gerekir:  
  
-   **VisitorFilterResult.Yes**- öğenin silinip silinmeyeceği ve walker denemeye devam etmemelisiniz öğesi diğer bağlantılar kullanıcının.  
  
-   **VisitorFilterResult.DoNotCare** -başka bir sorgu, silinmesi gerektiğini yanıtlar sürece öğe silinmemelidir.  
  
-   **VisitorFilterResult.Never** -başka bir sorgu yanıtlar olsa bile öğesi, silinmemelidir **Evet**, ve walker değil denemelisiniz öğesi diğer bağlantılar kullanıcının.  
  
```  
// When a musician is deleted, delete their albums with a low rating.  
// Override methods in <YourDsl>DeleteClosure in DomainModel.cs  
partial class MusicLibDeleteClosure  
{  
  public override VisitorFilterResult ShouldVisitRolePlayer  
    (ElementWalker walker, ModelElement sourceElement, ElementLink elementLink,   
    DomainRoleInfo targetDomainRole, ModelElement targetRolePlayer)  
  {  
    ArtistAppearsInAlbum link = elementLink as ArtistAppearsInAlbum;  
    if (link != null   
       && targetDomainRole.RolePlayer.Id == Album.DomainClassId)  
    {  
      // Count other unvisited links to the Album of this link.  
      if (ArtistAppearsInAlbum.GetLinksToArtists(link.Album)  
              .Where(linkAlbumArtist =>   
                     linkAlbumArtist != link &&  
                     !walker.Visited(linkAlbumArtist))  
              .Count() == 0)  
      {  
        // Should delete this role player:  
        return VisitorFilterResult.Yes;   
      }  
      else  
        // Don't delete unless another relationship deletes it:  
        return VisitorFilterResult.DoNotCare;   
    }  
    else   
    {  
      // Test for and respond to other relationships and roles here.  
  
      // Not the relationship or role we're interested in.  
      return base.ShouldVisitRolePlayer(walker, sourceElement,   
             elementLink, targetDomainRole, targetRolePlayer);  
    }  
  }  
}  
  
```  
  
 Silme işlemi başlamadan önce öğeleri ve silinecek bağlantılar kümesini belirlenir kapatma teknik sağlar. Walker ayrıca sonuçları, kapatma, bu model diğer kısımlarından birleştirir.  
  
 Ancak, silme, komşularına yalnızca grafikte ilişkilerin etkiler tekniği varsayar: başka bir modelin parçası olarak bir öğeyi silmek için bu yöntemi kullanamazsınız. Öğeler ekleme veya silme işlemi için yanıt başka değişiklikler yapmak istiyorsanız, bunu kullanamazsınız.  
  
##  <a name="ondeleting"></a>OnDeleting ve OnDeleted kullanma  
 Geçersiz kılabilirsiniz `OnDeleting()` veya `OnDeleted()` bir etki alanı sınıf veya bir etki alanı ilişkisi.  
  
1.  <xref:Microsoft.VisualStudio.Modeling.ModelElement.OnDeleting%2A>bir öğenin silinmek üzere olduğunda, ancak ilişkileri kesilmeden adı verilir. İçin ve diğer öğeleri hala gezinebilir ve hala `store.ElementDirectory`.  
  
     Aynı anda birden fazla öğeleri sildiyseniz OnDeleting bunların tümünün için silme işlemleri gerçekleştirmeden önce çağrılır.  
  
     `IsDeleting`geçerlidir.  
  
2.  <xref:Microsoft.VisualStudio.Modeling.ModelElement.OnDeleted%2A>öğe silindiğinde adı verilir. Böylece bir geri alma gerekirse gerçekleştirilebilir, ancak diğer öğeleri bağlantısız ve kaldırılmasını CLR yığınında kalır `store.ElementDirectory`. İlişkileri için rolleri hala eski rol oyuncuları başvuru.`IsDeleted` geçerlidir.  
  
3.  Kullanıcı bir öğeyi oluşturduktan sonra geri çalıştırdığında ve bir önceki silme Yinele için tekrarlanırsa OnDeleting ve OnDeleted adı verilir. Kullanım `this.Store.InUndoRedoOrRollback` deposu öğeleri bu gibi durumlarda güncelleştirme önlemek için. Daha fazla bilgi için bkz: [nasıl yapılır: kullanım modeli güncelleştirmek için işlemleri](../modeling/how-to-use-transactions-to-update-the-model.md).  
  
 Örneğin, son alt şarkı silindiğinde, aşağıdaki kod bir albümü siler:  
  
```  
  
// Delete the parent Album when the last Song is deleted.  
// Override methods in the embedding relationship between Album and Song:  
partial class AlbumHasSongs  
{  
  protected override void OnDeleted()  
  {  
    base.OnDeleted();  
    // Don't perform in-store actions in undo:  
    if (this.Store.InUndoRedoOrRollback) return;  
    // Relationship source and target still work:  
    // Don't bother if source is already on its way out:  
    if (!this.Album.IsDeleting && !this.Album.IsDeleted)  
    {  
      if (this.Album.Songs.Count == 0)  
      {   
        this.Album.Delete();  
} } } }  
  
```  
  
 Genellikle daha yararlıdır yararlı tetikleyici rol öğeden ilişkinin silinmeye karşı öğesi silindiğinde bu her ikisi de çalıştığından ve ilişki silindiğinde. Ancak, bir başvuru ilişkisi için ilgili bir öğe silindiğinde, ancak ilişki silinmez silme yaymak isteyebilirsiniz. Bu örnek, kendi son katkıda bulunan sanatçı silinir, ancak silinen ilişkiler varsa yanıtlamıyor albüm siler:  
  
```  
using System.Linq; ...  
// Assumes a many-many reference relationship   
// between Artist and Album.    
partial class Artist  
{  
  protected override void OnDeleting()  
  {  
    base.OnDeleting();  
    if (this.Store.InUndoRedoOrRollback) return;  
    List<Album> toDelete = new List<Album>();  
    foreach (Album album in this.Albums)  
    {  
      if (album.Artists.Where(artist => !artist.IsDeleting)  
                        .Count() == 0)  
      {  
        toDelete.Add(album);  
      }  
    }  
    foreach (Album album in toDelete)  
    {  
      album.Delete();  
} } }  
  
```  
  
 Gerçekleştirdiğinizde <xref:Microsoft.VisualStudio.Modeling.ModelElement.Delete%2A> bir öğede OnDeleting ve OnDeleted çağrılır. Bu yöntemlerin her zaman gerçekleştirilen satır içi - diğer bir deyişle, hemen önce ve sonra gerçek silme olursunuz. Kodunuzu iki veya daha fazla öğe silerse, OnDeleting ve OnDeleted bunların tümünde değişim içinde sırayla çağrılır.  
  
##  <a name="rules"></a>Silme kuralları ve olaylar  
 OnDelete işleyicileri için alternatif olarak, silme kuralları ve silme olaylarını tanımlayabilirsiniz.  
  
1.  **Silme** ve **silmek** kuralları yalnızca bir işlem ve bir geri alma veya Yinele tetiklenir. Bunları silme gerçekleştirildiği işlem sonunda yürütmek için sıraya ayarlayabilirsiniz. Silme kurallar sırada olan tüm silinen kuralları önce her zaman yürütülür.  
  
     Yalnızca ilişkileri, diyagram öğeleri ve özellikleri dahil olmak üzere deposundaki öğeleri etkileyen değişiklikleri yaymak için kuralları kullanın. Genellikle, bir silme kural silme yaymak için kullanılır ve silme kuralı değiştirme öğe ve ilişki oluşturmak için kullanılır.  
  
     Daha fazla bilgi için bkz: [kuralları yayılması değişiklikleri içindeki Model](../modeling/rules-propagate-changes-within-the-model.md).  
  
2.  **Silinen** deposu olay bir işlem sonunda çağrılır ve bir geri alma veya yineleme sonra çağrılır. Bu nedenle silme dosyaları, veritabanı girişlerini veya diğer nesneleri gibi depo dışındaki nesnelere yaymak için kullanılabilmesi için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
     Daha fazla bilgi için bkz: [olay işleyicileri yayılması değişiklikleri dışında modeli](../modeling/event-handlers-propagate-changes-outside-the-model.md).  
  
    > [!WARNING]
    >  Bir öğenin silindiğinde, etki alanı özellik değerlerinin erişebilirsiniz, ancak ilişki bağlantılar gidemezsiniz. Ancak, bir ilişkiye silinmiş bir olay ayarlarsanız, kendi rol oyuncuları olan iki öğe de erişebilirsiniz. Bu nedenle, bir model öğesi silme işlemini yanıt ancak bağlı bir öğeyi erişmek istediğiniz istiyorsanız, delete olayı model öğenin etki alanı sınıfı yerine ilişki ayarlayın.  
  
### <a name="example-deletion-rules"></a>Örnek silme kuralları  
  
```  
[RuleOn(typeof(Album), FireTime = TimeToFire.TopLevelCommit)]  
internal class AlbumDeletingRule : DeletingRule  
{  
  public override void ElementDeleting(ElementDeletingEventArgs e)  
  {  
    base.ElementDeleting(e);  
    // ...perform tasks to propagate imminent deletion  
  }  
}  
[RuleOn(typeof(Album), FireTime = TimeToFire.TopLevelCommit)]  
internal class AlbumDeletedRule : DeleteRule  
{  
  public override void ElementDeleted(ElementDeletedEventArgs e)  
  {  
    base.ElementDeleted(e);  
    // ...perform tasks such as creating new elements  
  }  
}  
  
// The rule must be registered:  
public partial class MusicLibDomainModel  
{  
  protected override Type[] GetCustomDomainModelTypes()  
  {  
    List<Type> types = new List<Type>(base.GetCustomDomainModelTypes());  
    types.Add(typeof(AlbumDeletingRule));  
    types.Add(typeof(AlbumDeletedRule));  
    // If you add more rules, list them here.   
    return types.ToArray();  
  }  
}  
  
```  
  
### <a name="example-deleted-event"></a>Örnek olayı silindi  
  
```  
partial class NestedShapesSampleDocData  
{  
  protected override void OnDocumentLoaded(EventArgs e)  
  {  
    base.OnDocumentLoaded(e);  
    DomainRelationshipInfo commentRelationship =   
          this.Store.DomainDataDirectory  
          .FindDomainRelationship(typeof(CommentsReferenceComponents));  
  
    this.Store.EventManagerDirectory.ElementDeleted.Add(commentRelationship,  
      new EventHandler<ElementDeletedEventArgs>(CommentLinkDeleted));  
  }  
  
  private void CommentLinkDeleted (object sender, ElementDeletedEventArgs e)  
  {  
    CommentsReferenceComponents link = e.ModelElement as CommentsReferenceComponents;  
    Comment comment = link.Comment;  
    Component component = link.Subject;  
    if (comment.IsDeleted)  
    {  
      // The link was deleted because the comment was deleted.  
      System.Windows.Forms.MessageBox.Show("Removed comment on " + component.Name);  
    }  
    else  
    {  
      // It was just the link that was deleted - the comment itself remains.  
      System.Windows.Forms.MessageBox.Show("Removed comment link to "   
           + component.Name);  
    }  
  }  
}  
  
```  
  
##  <a name="unmerge"></a>Bölme  
 Bir alt öğesi kendi üst iliştirir işlemi çağrıldı *birleştirme*. Yeni bir öğe olduğunda oluşur veya öğeleri grubunu araç kutusu'ndan oluşturulan veya başka bir modelin parçası taşınmış veya Pano'dan kopyalanır. Üst ve yeni alt arasında katıştırma bir ilişki oluşturma yanı sıra, birleştirme işlemi ayrıca ek ilişkileri ayarlamanız, yardımcı öğeleri oluşturun ve öğeleri özellik değerlerini ayarlar. Birleştirme işlemi, bir öğenin birleştirme yönergesi (EMD) kapsüllenir.  
  
 Bir EMD de tamamlayıcı yalıtır *Çöz* veya `MergeDisconnect` işlemi. Bir birleştirme kullanılarak oluşturulan bir küme öğe varsa, ilişkili kullanmak için önerilir bu sınıftan bir öğeyi kaldırmak için kalan öğeleri tutarlı bir durumda bırakır istiyorsanız Çöz. Birleştirme işlemi genellikle önceki bölümlerde açıklanan teknikleri kullanır.  
  
 Daha fazla bilgi için bkz: [özelleştirme öğesi oluşturma ve taşıma](../modeling/customizing-element-creation-and-movement.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kopyalama davranışını özelleştirme](../modeling/customizing-copy-behavior.md)   
 [Öğe oluşturma ve taşıma özelleştirme](../modeling/customizing-element-creation-and-movement.md)   
 [Bir etki alanına özgü dil kişiselleştirmek için kod yazma](../modeling/writing-code-to-customise-a-domain-specific-language.md)