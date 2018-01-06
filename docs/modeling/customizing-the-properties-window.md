---
title: "Özellikler penceresini özelleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, Properties window
ms.assetid: b6658de5-4e85-4628-93b2-5cc12f63d25b
caps.latest.revision: "20"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: 2c11cf4d8fb8d913c1d288b5daeb110b9003f7b6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="customizing-the-properties-window"></a>Özellikler Penceresini Özelleştirme
İçinde etki alanına özgü dil (DSL) penceresinin davranış ve görünümünü özelleştirebilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. DSL tanımınızı her etki alanı sınıf üzerinde etki alanı özellikleri tanımlayın. Sınıfının bir örneği, diyagram veya Model Gezgini'nde seçtiğinizde varsayılan olarak, her etki alanı özelliği Özellikler penceresinde listelenir. Bunları diyagramda şekli alanlara eşlenmedi olsa bile bu bakın ve etki alanı özelliklerinin değerlerini düzenlemenizi sağlar.  
  
## <a name="names-descriptions-and-categories"></a>Adları ve açıklamaları kategorileri  
 **Ad ve görünen ad**. Bir etki alanı özelliği tanımı içinde özellik görünen adı Özellikler penceresinde çalışma zamanında görüntülenen addır. Bunun aksine, özelliği güncelleştirmek için program kodu yazarken adı kullanılır. Adın doğru bir CLR alfasayısal adı olması gerekir, ancak görünen ad boşluk içeremez.  
  
 Bir özelliğin adını DSL tanımında ayarladığınızda, görünen adını bir kopyası adı otomatik olarak ayarlanır. "FuelGauge" gibi bir Pascal cased adı yazarsanız, görünen adı otomatik olarak bir boşluk içerir: "Yakıt ölçer". Ancak, görünen adı başka bir değere açıkça ayarlayabilirsiniz.  
  
 **Açıklama**. Bir etki alanı özellik açıklaması iki yerde görüntülenir:  
  
-   Kullanıcı özelliği seçtiğinde penceresinin alt. Hangi özelliği temsil eden kullanıcıya açıklamak için kullanabilirsiniz.  
  
-   Oluşturulan program kodu içinde. API belgelerine ayıklamak için belge özelliklerini kullanıyorsanız, bu özellikte API açıklaması olarak görünür.  
  
 **Kategori**. Bir kategori, Başlık Özellikleri penceresinde grubudur.  
  
## <a name="exposing-style-features"></a>Stil özellikleri gösterme  
 Dinamik özelliklerin bir grafik öğelerinin temsil edilebilir veya *açığa* etki alanı özellikleri olarak. Bu şekilde kullanıma sunulan bir özellik kullanıcı tarafından güncelleştirilebilir ve daha fazla program kodu tarafından kolayca güncelleştirilebilir.  
  
 Shape sınıfı DSL tanımında sağ tıklayın, fareyle **eklemek açığa**ve ardından bir özellik seçin.  
  
 Şekilleri, getirebilir **FillColor**, **OutlineColor**, **TextColor**, **OutlineDashStyle**,  **OutlineThickness** ve **FillGradientMode** özellikleri. Bağlayıcıların, getirebilir **renk**`,`**TextColor**, **DashStyle**, ve **kalınlığı** özellikleri. Diyagramlar üzerinde getirebilir **FillColor** ve **TextColor** özellikleri.  
  
## <a name="forwarding-displaying-properties-of-related-elements"></a>İletme: İlgili öğelerin özelliklerini görüntüleme  
 DSL kullanıcı bir model öğeyi seçtiğinde, bu öğenin özellikleri Özellikler penceresinde görüntülenir. Ancak, belirtilen ile ilgili öğeleri özelliklerini görüntüleyebilirsiniz. Birlikte çalışan öğeleri grubunu tanımladıysanız, bu yararlıdır. Örneğin, bir ana öğesi ve isteğe bağlı eklenti öğenin tanımlayabilirsiniz. Main öğesi şekle eşlenen ve diğer değil, bir öğede değilmiş gibi tüm özelliklerini görmek yararlıdır.  
  
 Bu etkiyi adlı *özelliği iletme*, ve bazı durumlarda otomatik olarak gerçekleşir. Diğer durumlarda, bir etki alanı tür tanımlayıcı tanımlayarak iletme özelliği elde edebilirsiniz.  
  
### <a name="default-property-forwarding-cases"></a>Varsayılan özellik iletme durumları  
 Kullanıcı Explorer'ın bir şekli veya Bağlayıcısı veya bir öğe seçtiğinde, aşağıdaki özellikleri Özellikler penceresinde görüntülenir:  
  
-   Temel sınıflarda tanımlanan dahil olmak üzere model öğesi etki alanı sınıfının üzerinde tanımlanan etki alanı özellikleri. Etki alanı özellikleri için ayarlanmış bir istisnadır **olan gözatılamaz** için `False`.  
  
-   0.. 1 çokluğa çokluğu olan ilişkileri bağlı öğeleri adları. İlişki için bir bağlayıcı eşlemesi tanımlı değil olsa bile bu öğeleri, isteğe bağlı olarak görülmesi için kullanışlı bir yöntem bağlı sağlar.  
  
-   Öğesini hedefleyen katıştırma ilişkisinin özelliklerini etki alanı. Katıştırma ilişkileri genellikle açıkça görüntülenmez olduğundan, bu kullanıcının kendi özelliklerine bakın sağlar.  
  
-   Seçilen şekil veya bağlayıcı üzerinde tanımlanan etki alanı özellikleri.  
  
### <a name="adding-property-forwarding"></a>Özellik iletme ekleme  
 Bir özellik iletmek için bir etki alanı tür tanımlayıcı tanımlayın. İki etki alanı sınıf arasında bir etki alanı ilişkisi varsa, ikinci etki alanı sınıfının bir etki alanı özelliği ilk sınıfının değeri için bir etki alanı özelliği ayarlamak için bir etki alanı tür tanımlayıcı kullanabilirsiniz. Arasında bir ilişki varsa, örneğin, bir **defteri** etki alanı sınıfı ve bir **Yazar** etki alanı sınıfı bir etki alanı tür tanımlayıcı yapmak için kullanabileceğiniz **adı** özelliğinin bir Kitaptaki **Yazar** kullanıcı rehberi seçtiğinde Özellikler penceresinde görünür.  
  
> [!NOTE]
>  Kullanıcı bir model düzenlerken özelliği iletme sadece Özellikler penceresinde etkiler. Alıcı sınıf üzerinde bir etki alanı özelliği tanımlamıyor. İletilen etki alanı özelliği DSL tanımı diğer bölümleri veya program kodunun erişmek isterseniz, iletme öğesi erişmeniz gerekir.  
  
 Aşağıdaki yordam, DSL oluşturduğunuzu varsayar. İlk birkaç adımda önkoşulları özetler.  
  
##### <a name="to-forward-a-property-from-another-element"></a>Bir özellik başka bir öğeden iletmek için  
  
1.  Oluşturma bir [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] olarak adlandırılır, bu örnekte en az iki sınıf içeren çözüm **defteri** ve **Yazar**. Her iki tür arasında bir ilişki olmalıdır **defteri** ve **Yazar**.  
  
     Kaynak role çokluğu (rolde **defteri** yan) olmalıdır 0.. 1 çokluğa veya 1..1, bu nedenle, her **defteri** varsa **Yazar**.  
  
2.  İçinde **DSL Explorer**, sağ **kitap** etki alanı sınıfı ve ardından **ekleme yeni DomainTypeDescriptor**.  
  
     Adlı bir düğüm **özel özellik tanımlayıcılarının yolları** altında görünür **özel tür tanımlayıcı** düğümü.  
  
3.  Sağ **özel tür tanımlayıcı** düğümünü ve ardından **ekleme yeni PropertyPath**.  
  
     Yeni bir özellik yolu altında görünür **özel özellik tanımlayıcılarının yolları** düğümü.  
  
4.  Yeni özellik yolu seçin ve **özellikleri** penceresindeki ayarlayın **özelliğe yol** uygun model öğesi yolu.  
  
     Bu özellik sağındaki aşağı oka tıklayarak ağaç görünümünde yolu düzenleyebilirsiniz. Etki alanı yolları hakkında daha fazla bilgi için bkz: [etki alanı yolu sözdizimi](../modeling/domain-path-syntax.md). Düzenlediğinizde, yolun benzemelidir **BookReferencesAuthor.Author/! Yazar**.  
  
5.  Ayarlama **özelliği** için **adı** etki alanı özelliği **Yazar**.  
  
6.  Ayarlama **görünen adı** için **yazar adı**.  
  
7.  Tüm Şablonları dönüştürme, yapı ve DSL çalıştırın.  
  
8.  Bir model diyagramı kitap, bir yazarın oluşturabilir ve bunları başvuru ilişkisi kullanarak bağlayabilirsiniz. Kitap öğesini seçin ve Özellikler penceresinde kitap özelliklerine ek olarak yazar adı görmeniz gerekir. Bağlantılı yazarının adını değiştirin veya başka bir yazar kitap bağlayın ve rehberi yazar adı değiştiğini gözlemleyin.  
  
## <a name="custom-property-editors"></a>Özel özellik düzenleyiciler  
 Özellik penceresi düzenleme deneyimi her bir etki alanı özellik türü için uygun bir varsayılan sağlar. Örneğin, numaralandırılmış bir türü için kullanıcı aşağı açılan listesini görür ve bir sayısal özellik için kullanıcı basamak girebilirsiniz. Bu yalnızca yerleşik türleri için geçerlidir. Bir dış türe belirtirseniz, kullanıcı özellikte bakın, ancak düzenlemek değil mümkün olacaktır.  
  
 Ancak, aşağıdaki düzenleyicileri ve türlerini belirtebilirsiniz:  
  
1.  Standart bir türüyle kullanılan başka bir düzenleyici. Örneğin, bir dize özelliği için bir dosya yolu Düzenleyici belirtebilirsiniz.  
  
2.  Bir dış türe etki alanı özelliği ve bunun için bir düzenleyici.  
  
3.  Dosya yolu Düzenleyicisi'ni veya gibi bir .NET Düzenleyicisi, kendi özel özellik düzenleyici oluşturabilirsiniz.  
  
     Bir dış türe ve varsayılan düzenleyici sahip dize gibi bir türü arasında dönüştürme.  
  
 Bir DSL içinde bir *dış türü* basit türleri (örneğin, Boole veya Int32) veya dize biri değil herhangi bir tür.  
  
#### <a name="to-define-a-domain-property-that-has-an-external-type"></a>Bir dış türe sahip bir etki alanı özelliği tanımlamak için  
  
1.  İçinde **Çözüm Gezgini**, dış türü içeren derleme (DLL) için bir başvuru ekleyin **Dsl** projesi.  
  
     Derleme bir .NET derlemesi veya tarafından sağlanan bir derleme olabilir.  
  
2.  Türüne ekleme **etki alanı türleri** bunu yapmış olduğunuz sürece listeleyin.  
  
    1.  DslDefinition.dsl, açın ve **DSL Explorer**, kök düğüme sağ tıklayın ve ardından **yeni dış türü Ekle**.  
  
         Altında yeni bir giriş belirir **etki alanı türleri** düğümü.  
  
        > [!WARNING]
        >  Menü öğesi DSL kök düğümde değil **etki alanı türleri** düğümü.  
  
    2.  Ad ve yeni türünün ad alanını Özellikler penceresinde ayarlayın.  
  
3.  Bir etki alanı özelliği normal şekilde bir etki alanı sınıfına ekleyin.  
  
     Özellikler penceresinde dış aşağı açılan listeden seçin **türü** alan.  
  
 Bu aşamada, kullanıcıların özelliği değerlerini görüntüleyebilir, ancak bunlar düzenleyemezsiniz. Görüntülenen değerleri elde edilen `ToString()` işlevi. Özelliğinin değeri, örneğin bir komut veya kural ayarlar program kodu yazabilirsiniz.  
  
### <a name="setting-a-property-editor"></a>Özellik Düzenleyici ayarlama  
 Etki alanı özelliği aşağıdaki biçimde bir CLR özniteliği ekleyin:  
  
```  
[System.ComponentModel.Editor (  
   typeof(AnEditor),  
   typeof(System.Drawing.Design.UITypeEditor))]  
  
```  
  
 Öznitelik, bir özellik kullanarak ayarlayabileceğiniz **özel öznitelik** Özellikleri penceresinde girişi.  
  
 Türü `AnEditor` ikinci parametresinde belirtilen türünden türetilmelidir. İkinci parametre aşağıdakilerden biri olması gerekir <xref:System.Drawing.Design.UITypeEditor> veya <xref:System.ComponentModel.ComponentEditor>. Daha fazla bilgi için bkz. <xref:System.ComponentModel.EditorAttribute>.  
  
 Kendi Düzenleyicisi veya, sağlanan bir düzenleyici belirtebilirsiniz [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], gibi <xref:System.Windows.Forms.Design.FileNameEditor> veya <xref:System.Drawing.Design.ImageEditor>. Örneğin, kullanıcının bir dosya adı girebileceği bir özellik olması için aşağıdaki yordamı kullanın.  
  
##### <a name="to-define-a-file-name-domain-property"></a>Bir dosya adı etki alanı özelliği tanımlamak için  
  
1.  Bir etki alanı özelliği DSL tanımında bir etki alanı sınıfına ekleyin.  
  
2.  Yeni özellik seçin. İçinde **özel öznitelik** alanında Özellikler penceresinde, aşağıdaki öznitelik girin. Bu öznitelik girmek için üç nokta düğmesine **[...]**  öznitelik adı ve parametreleri ayrı ayrı girin:  
  
    ```  
    [System.ComponentModel.Editor (  
       typeof(System.Windows.Forms.Design.FileNameEditor)  
       , typeof(System.Drawing.Design.UITypeEditor))]  
  
    ```  
  
3.  Etki alanı özelliğinin türü, kendi varsayılan ayarını bırakın **dize**.  
  
4.  Düzenleyici sınamak için kullanıcılar, etki alanı özelliği düzenlemek için dosya adı Düzenleyicisi'ni açabilir doğrulayın.  
  
    1.  CTRL + F5'e veya F5 tuşuna basın. Hata ayıklama çözümde test dosyasını açın. Etki alanı sınıfının bir öğe oluşturun ve bunu seçin.  
  
    2.  Özellikler penceresinde etki alanı özelliğini seçin. Değer alanı üç nokta gösterir **[...]** .  
  
    3.  Üç nokta işaretine tıklayın. Dosya iletişim kutusu görünür. Bir dosya seçin ve iletişim kutusunu kapatın. Dosya yolu, etki alanı özelliğinin değeri bir sunulmuştur.  
  
### <a name="defining-your-own-property-editor"></a>Kendi özellik Düzenleyici tanımlama  
 Kendi Düzenleyicisi tanımlayabilirsiniz. Kullanıcı ya da tanımladığınız bir türü düzenlemek için bir standart türü özel bir yolla düzenlemek için izin vermek için bunu. Örneğin, bir formül temsil eden bir dize giriş kullanıcıya izin verebilir.  
  
 Türetilmiş bir sınıf yazarak bir düzenleyici tanımladığınız <xref:System.Drawing.Design.UITypeEditor>. Sınıfınızda geçersiz kılmanız gerekir:  
  
-   <xref:System.Drawing.Design.UITypeEditor.EditValue%2A>, kullanıcıyla etkileşim ve özellik değerini güncelleştirmek için.  
  
-   <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A>, düzenleyicinizi bir iletişim kutusunu açın veya bir açılır menü sağlamak belirtin.  
  
 Özellik kılavuzunda görüntülenecek özelliğin değerini grafik gösterimi sağlar. Bunu yapmak için geçersiz kılma `GetPaintValueSupported`, ve `PaintValue`.  Daha fazla bilgi için bkz. <xref:System.Drawing.Design.UITypeEditor>.  
  
> [!NOTE]
>  Ayrı kod dosyasında aşağıdaki kodu ekleyip **Dsl** projesi.  
  
 Örneğin:  
  
```  
internal class TextFileNameEditor : System.Windows.Forms.Design.FileNameEditor  
{  
  protected override void InitializeDialog(System.Windows.Forms.OpenFileDialog openFileDialog)  
  {  
    base.InitializeDialog(openFileDialog);  
    openFileDialog.Filter = "Text files(*.txt)|*.txt|All files (*.*)|*.*";  
    openFileDialog.Title = "Select a text file";  
  }  
}  
  
```  
  
 Bu düzenleyici kullanmak üzere ayarlanmış **özel öznitelik** bir etki alanı özelliği:  
  
```  
[System.ComponentModel.Editor (  
   typeof(MyNamespace.TextFileNameEditor)  
   , typeof(System.Drawing.Design.UITypeEditor))]  
  
```  
  
 Daha fazla bilgi için bkz. <xref:System.Drawing.Design.UITypeEditor>.  
  
## <a name="providing-a-drop-down-list-of-values"></a>Aşağı açılan liste değerlerinin sağlama  
 Aralarından seçim yapabileceğiniz bir kullanıcı için değerler listesini sağlayabilirsiniz.  
  
> [!NOTE]
>  Bu teknik çalışma zamanında değiştirebilirsiniz değerler listesini sağlar. Değişmeyen bir listesi sağlamak istiyorsanız, bunun yerine göz önünde bulundurun Numaralandırılmış türe, etki alanı özellik türü olarak kullanma.  
  
 Standart bir değer listesi tanımlamak için aşağıdaki biçime sahiptir bir CLR öznitelik etki alanı özelliğinizi ekleyin:  
  
```  
[System.ComponentModel.TypeConverter   
(typeof(MyTypeConverter))]  
  
```  
  
 Türeyen bir sınıf tanımlama <xref:System.ComponentModel.TypeConverter>. Ayrı bir dosyada aşağıdaki kodu ekleyip **Dsl** projesi. Örneğin:  
  
```csharp  
/// <summary>  
/// Type converter that provides a list of values   
/// to be displayed in the property grid.  
/// </summary>  
/// <remarks>This type converter returns a list   
/// of the names of all "ExampleElements" in the   
/// current store.</remarks>  
public class MyTypeConverter : System.ComponentModel.TypeConverter  
{  
  /// <summary>  
  /// Return true to indicate that we return a list of values to choose from  
  /// </summary>  
  /// <param name="context"></param>  
  public override bool GetStandardValuesSupported  
    (System.ComponentModel.ITypeDescriptorContext context)  
  {  
    return true;  
  }  
  
  /// <summary>  
  /// Returns true to indicate that the user has   
  /// to select a value from the list  
  /// </summary>  
  /// <param name="context"></param>  
  /// <returns>If we returned false, the user would   
  /// be able to either select a value from   
  /// the list or type in a value that is not in the list.</returns>  
  public override bool GetStandardValuesExclusive  
      (System.ComponentModel.ITypeDescriptorContext context)  
  {  
    return true;  
  }  
  
  /// <summary>  
  /// Return a list of the values to display in the grid  
  /// </summary>  
  /// <param name="context"></param>  
  /// <returns>A list of values the user can choose from</returns>  
  public override StandardValuesCollection GetStandardValues  
      (System.ComponentModel.ITypeDescriptorContext context)  
  {  
    // Try to get a store from the current context  
    // "context.Instance"  returns the element(s) that   
    // are currently selected i.e. whose values are being  
    // shown in the property grid.   
    // Note that the user could have selected multiple objects,   
    // in which case context.Instance will be an array.  
    Store store = GetStore(context.Instance);  
  
    List<string> values = new List<string>();  
  
    if (store != null)  
    {  
      values.AddRange(store.ElementDirectory  
        .FindElements<ExampleElement>()  
        .Select<ExampleElement, string>(e =>   
      {  
        return e.Name;  
      }));  
    }  
    return new StandardValuesCollection(values);  
  }  
  
  /// <summary>  
  /// Attempts to get to a store from the currently selected object(s)  
  /// in the property grid.  
  /// </summary>  
  private Store GetStore(object gridSelection)  
  {  
    // We assume that "instance" will either be a single model element, or   
    // an array of model elements (if multiple items are selected).  
  
    ModelElement currentElement = null;  
  
    object[] objects = gridSelection as object[];  
    if (objects != null && objects.Length > 0)  
    {  
      currentElement = objects[0] as ModelElement;  
    }  
    else  
    {  
        currentElement = gridSelection as ModelElement;  
    }  
  
    return (currentElement == null) ? null : currentElement.Store;  
  }  
  
}  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Program Kodunda Modeli Gezinme ve Güncelleştirme](../modeling/navigating-and-updating-a-model-in-program-code.md)