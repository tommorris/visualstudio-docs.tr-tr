---
title: "İzlenecek yol: Metin şablonları kullanarak kod oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
helpviewer_keywords:
- walkthroughs [text templates], generating application code
- walkthroughs [text templates]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 46cbf0c6a28b10434ed364dffd77c4c01620d6ea
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="walkthrough-generating-code-by-using-text-templates"></a>İzlenecek Yol: Metin Şablonları Kullanarak Kod Oluşturma
Kod oluşturma, kesin türü belirtilmiş ve kaynak modeli değiştiğinde henüz kolayca değiştirilebilmesi için program kodunu üretmek sağlar. Bunu daha esnektir, bir yapılandırma dosyası kabul tamamen genel bir program yazma alternatif teknik ile karşılaştırın ancak ne kod sonuçlarında kadar kolay okumak ve değiştirmek ya da bu tür iyi bir performans sahiptir. Bu kılavuzda Bu avantajı gösterir.  
  
## <a name="typed-code-for-reading-xml"></a>XML okumak için yazılan kod  
 System.Xml ad alanı bir XML belgesi yüklenirken ve bellekte serbestçe gezinme için kapsamlı araçları sağlar. Ne yazık ki, tüm düğümlerin aynı XmlNode türü vardır. Bu nedenle alt düğüm ya da yanlış öznitelikleri yanlış türde bekleniyor gibi programlama hatalar yapmak çok kolaydır.  
  
 Bu örnek proje şablonu bir örnek XML dosyasını okur ve her düğüm türü için karşılık gelen sınıfları oluşturur. Elle yazılmış kodda XML dosyasını gitmek için bu sınıfları kullanabilirsiniz. Uygulamanız aynı düğüm türlerini kullanan tüm diğer dosyalar üzerinde de çalıştırabilirsiniz. Örnek XML dosyası amacı uğraşmanız uygulamanızın istediğiniz tüm düğüm türleri örnekleri sağlamaktır.  
  
> [!NOTE]
>  Uygulama [XSD.exe'nin](http://go.microsoft.com/fwlink/?LinkId=178765), birlikte bulunan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], türü kesin belirlenmiş sınıf XML dosyalarından oluşturabilirsiniz. Burada gösterilen şablon, örnek olarak sağlanır.  
  
 Örnek dosyayı şöyledir:  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<catalog>  
  <artist id ="Mike%20Nash" name="Mike Nash Quartet">  
    <song id ="MikeNashJazzBeforeTeatime">Jazz Before Teatime</song>  
    <song id ="MikeNashJazzAfterBreakfast">Jazz After Breakfast</song>  
  </artist>  
  <artist id ="Euan%20Garden" name="Euan Garden">  
    <song id ="GardenScottishCountry">Scottish Country Garden</song>  
  </artist>  
</catalog>  
```  
  
 Bu izlenecek yol oluşturur, aşağıdaki gibi kod yazabilirsiniz ve IntelliSense yazarken doğru özniteliği ve alt adlarıyla ister projesinde:  
  
```  
Catalog catalog = new Catalog(xmlDocument);  
foreach (Artist artist in catalog.Artist)  
{  
  Console.WriteLine(artist.name);  
  foreach (Song song in artist.Song)  
  {  
    Console.WriteLine("   " + song.Text);  
  }  
}  
```  
  
 Bu şablon yazabilir türsüz kod ile karşılaştırın.  
  
```  
XmlNode catalog = xmlDocument.SelectSingleNode("catalog");  
foreach (XmlNode artist in catalog.SelectNodes("artist"))  
{  
    Console.WriteLine(artist.Attributes["name"].Value);  
    foreach (XmlNode song in artist.SelectNodes("song"))  
    {  
         Console.WriteLine("   " + song.InnerText);  
     }  
}  
```  
  
 Kesin türü belirtilmiş sürümünde bir değişiklik XML şemasına sınıfları değişiklikleri neden olur. Derleyici değiştirilmelidir uygulama kodu bölümlerini vurgular. Genel XML kodunu kullanan türsüz sürümünde böyle desteği yoktur.  
  
 Bu projede bir tek şablon dosyası, yazılı sürüm mümkün kılar sınıfları oluşturmak için kullanılır.  
  
## <a name="setting-up-the-project"></a>Proje ayarlama  
  
### <a name="create-or-open-a-c-project"></a>C# projesi oluşturun veya açın  
 Bu teknik herhangi bir kod projesine uygulayabilirsiniz. Bu kılavuzda bir C# projesi kullanır ve sınama amacıyla bir konsol uygulaması kullanırız.  
  
##### <a name="to-create-the-project"></a>Proje oluşturmak için  
  
1.  Üzerinde **dosya** menüsünü tıklatın **yeni** ve ardından **proje**.  
  
2.  Tıklatın **Visual C#** düğümü ve ardından **şablonları** bölmesinde tıklatın **konsol uygulaması.**  
  
### <a name="add-a-prototype-xml-file-to-the-project"></a>Bir prototip XML dosyası projeye ekleyin  
 Bu dosyanın amacı okumak, uygulamanızın istediğiniz XML düğüm türleri örnekleri sağlamaktır. Uygulamanızı test etmek için kullanılacak bir dosya olabilir. Şablon bu dosyadaki her düğüm türü için C# sınıfı oluşturur.  
  
 Dosya, böylece şablonu okuyabilir, ancak bunu derlenmiş uygulamasına da yerleşik değil projenin bir parçası olması gerekir.  
  
##### <a name="to-add-an-xml-file"></a>Bir XML dosyası eklemek için  
  
1.  İçinde **Çözüm Gezgini**, projeye sağ tıklayın, **Ekle** ve ardından **yeni öğe**.  
  
2.  İçinde **Yeni Öğe Ekle** iletişim kutusunda **XML dosyası** gelen **şablonları** bölmesi.  
  
3.  Örnek içeriğinizi dosyasına ekleyin.  
  
4.  Bu kılavuz için dosya adı `exampleXml.xml`. Dosya içeriği, önceki bölümde gösterilen XML olarak ayarlayın.  
  
 .  
  
### <a name="add-a-test-code-file"></a>Bir test kodu dosyası ekleme  
 Bir C# dosyayı projenize ekleyin ve bunu yazabilmesi için istediğiniz kod örneği yazma. Örneğin:  
  
```  
using System;  
namespace MyProject  
{  
  class CodeGeneratorTest  
  {  
    public void TestMethod()  
    {  
      Catalog catalog = new Catalog(@"..\..\exampleXml.xml");  
      foreach (Artist artist in catalog.Artist)  
      {  
        Console.WriteLine(artist.name);  
        foreach (Song song in artist.Song)  
        {  
          Console.WriteLine("   " + song.Text);  
} } } } }  
```  
  
 Bu aşamada bu kodu derlemek başarısız olur. Şablon yazarken başarılı olması izin sınıfları oluşturur.  
  
 Bu örnek XML dosyasının bilinen içeriği karşı test işlevi çıktısını daha kapsamlı bir test denetleyebilirsiniz. Ancak test yöntemi derlediğinde bu kılavuzda, biz memnun görüntülenir.  
  
### <a name="add-a-text-template-file"></a>Metin şablonu dosyasını ekleme  
 Metin şablonu dosyasını ekleyin ve ".cs" için çıktı uzantısı ayarlayın.  
  
##### <a name="to-add-a-text-template-file-to-your-project"></a>Metin şablonu dosyasını projenize eklemek için  
  
1.  İçinde **Çözüm Gezgini**, projeye sağ tıklayın, **Ekle**ve ardından **yeni öğe**.  
  
2.  İçinde **Yeni Öğe Ekle** iletişim kutusu seç **metin şablonu** gelen **şablonları** bölmesi.  
  
    > [!NOTE]
    >  Metin şablonu ve şablon değil de bir ön işlemesi yapılan metin eklediğinizden emin olun.  
  
3.  Dosyasında şablon yönergesi değiştirme `hostspecific` özniteliğini `true`.  
  
     Bu değişiklik erişmek şablon kodu etkinleştirecek [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Hizmetleri.  
  
4.  Çıkış yönergesi, uzantısı özniteliği ".cs" değiştirin şablon bir C# dosyası oluşturur. Visual Basic projesinde ".vb" değiştirirsiniz.  
  
5.  Dosyayı kaydedin. Bu aşamada, metin şablonu dosyasını bu satırlar içermelidir:  
  
    ```  
    <#@ template debug="false" hostspecific="true" language="C#" #>  
    <#@ output extension=".cs" #>  
    ```  
  
 biçimindeki telefon numarasıdır.  
  
 .Cs dosyası bir şablon dosyası temsilcisine Çözüm Gezgini'nde görüntülendiğine dikkat edin. [+]'i tıklatarak şablon dosyası adının yanındaki görebileceğiniz. Bu dosyayı her kaydedin veya uzakta şablon dosyası odağı taşımak şablon dosyasından oluşturulur. Oluşturulan dosyanın projenizin bir parçası olarak derlenmiş.  
  
 Çalışırken kolaylık sağlamak için şablon dosyası geliştirmek, böylece bunları birbirinin yanına gördüğünüz pencereleri şablon dosyası ve oluşturulan dosya. Bu, hemen şablonunuzu çıktısını görmenizi sağlar. Ayrıca, şablonunuzu geçersiz C# kodu oluşturduğunda hataları hata ileti penceresinde görünür fark edeceksiniz.  
  
 Şablon dosyasını kaydetmek her doğrudan oluşturulan dosyasında gerçekleştirdiğiniz tüm düzenlemeleri kaybolur. Bu nedenle oluşturulan dosyanın düzenlemekten kaçının, veya yalnızca kısa denemeleri için Düzenle. Bazen, IntelliSense işlemde olduğu, dosyanın oluşturulan kodda kısa bir parçasını deneyin ve şablon dosyasını kopyalamak kullanışlıdır.  
  
## <a name="developing-the-text-template"></a>Metin şablonu geliştirme  
 Çevik Geliştirme üzerinde en iyi önerileri biz küçük adımları şablonunda test kodu derler ve düzgün çalıştığını kadar her artış hatalarını bazıları temizleme geliştireceksiniz.  
  
### <a name="prototype-the-code-to-be-generated"></a>Prototip oluşturulması için kodu  
 Test kodu dosyasındaki her düğüm için bir sınıf gerektirir. Şablona şu satırları ekleyin ve dosyayı kaydedin, bu nedenle, derleme hataları bazıları kaybolur:  
  
```  
class Catalog {}   
class Artist {}  
class Song {}  
```  
  
 Bu gerekenden görmenize yardımcı olur, ancak bildirimleri örnek XML dosyasında düğüm türlerinden oluşturulması gerekir. Bu Deneysel satırları şablondan silin.  
  
### <a name="generate-application-code-from-the-model-xml-file"></a>Uygulama kodu model XML dosyasından oluşturun  
 XML dosyasını okumak ve sınıf bildirimleri oluşturmak için aşağıdaki şablonu kodu ile içerik şablonu değiştirin:  
  
```  
<#@ template debug="false" hostspecific="true" language="C#" #>  
<#@ output extension=".cs" #>  
<#@ assembly name="System.Xml"#>  
<#@ import namespace="System.Xml" #>  
<#  
 XmlDocument doc = new XmlDocument();  
 // Replace this file path with yours:  
 doc.Load(@"C:\MySolution\MyProject\exampleXml.xml");  
 foreach (XmlNode node in doc.SelectNodes("//*"))  
 {  
#>  
  public partial class <#= node.Name #> {}  
<#  
 }  
#>  
```  
  
 Dosya yolu projeniz için doğru yolu değiştirin.  
  
 Kod bloğu ayırıcısı fark `<#...#>`. Bu sınırlayıcılar köşeli ayraç metni oluşturur program kodunun bir parçası. İfade blok sınırlayıcıları `<#=...#>` dizeye hesaplanan bir ifadenin köşeli ayraç.  
  
 Uygulamanız için kaynak kodu oluşturan bir şablon yazarken, iki ayrı program metni ile çalışıyorsanız. Program kod bloğu ayırıcısı içinde şablonu kaydetmek veya başka bir pencere odağı taşımak her zaman çalışır. Dışında sınırlayıcıları görüntülenen, oluşturduğu metin oluşturulan dosyaya kopyalanır ve uygulama kodunuz parçası haline gelir.  
  
 `<#@assembly#>` Yönergesi derleme şablonu kodu kullanılabilir hale getirir, bir başvuru gibi davranır. Şablon tarafından görülen bir derleme listesi, uygulama projesi başvuruları listesinde ayrıdır.  
  
 `<#@import#>` Yönergesi gibi davranan bir `using` deyimi, içeri aktarılan ad alanındaki sınıflar kısa adları kullanmanıza olanak sağlayan.  
  
 Ne yazık ki, bu örnek XML dosyası kümedeki her düğüm için bir sınıf bildirim üretir kod bu şablon oluşturur rağmen böylece birden çok örneği varsa `<song>` düğümü, çeşitli bildirimleri sınıfı şarkının görünür.  
  
### <a name="read-the-model-file-then-generate-the-code"></a>Model dosyası okuyun ve sonra kod oluşturma  
 Birçok metin şablonu şablon ilk bölümü kaynak dosyasını okur bir yol izler ve şablon ikinci bölümü oluşturur. Tüm içerdiği düğüm türleri özetlemek için örnek dosyasının okumak ve ardından sınıf bildirimleri üretmek gerekir. Başka bir `<#@import#>` biz kullanabilmesi için gereklidir`Dictionary<>:`  
  
```  
<#@ template debug="false" hostspecific="true" language="C#" #>  
<#@ output extension=".cs" #>  
<#@ assembly name="System.Xml"#>  
<#@ import namespace="System.Xml" #>  
<#@ import namespace="System.Collections.Generic" #>  
<#  
 // Read the model file  
 XmlDocument doc = new XmlDocument();  
 doc.Load(@"C:\MySolution\MyProject\exampleXml.xml");  
 Dictionary <string, string> nodeTypes =   
        new Dictionary<string, string>();  
 foreach (XmlNode node in doc.SelectNodes("//*"))  
 {  
   nodeTypes[node.Name] = "";  
 }  
 // Generate the code  
 foreach (string nodeName in nodeTypes.Keys)  
 {  
#>  
  public partial class <#= nodeName #> {}  
<#  
 }  
#>  
```  
  
### <a name="add-an-auxiliary-method"></a>Yardımcı bir yöntem ekleyin  
 Bir sınıf özelliği denetim bloğu taşıdır içinde tanımlayabilirsiniz yardımcı yöntemler. Blok virgülle ayrılan `<#+...#>` ve son blok dosya olarak görünmesi gerekir.  
  
 Sınıf adları büyük harfle başlayan tercih ederseniz, şablonunun son parçası aşağıdaki şablonu kod ile değiştirin:  
  
```  
// Generate the code  
 foreach (string nodeName in nodeTypes.Keys)  
 {  
#>  
  public partial class <#= UpperInitial(nodeName) #> {}  
<#  
 }  
#>  
<#+  
 private string UpperInitial(string name)  
 { return name[0].ToString().ToUpperInvariant() + name.Substring(1); }  
#>  
```  
  
 Bu aşamada, aşağıdaki bildirimlerini oluşturulan .cs dosya içerir:  
  
```  
public partial class Catalog {}  
public partial class Artist {}  
public partial class Song {}  
```  
  
 Alt düğümler, öznitelikleri ve iç metni özellikler gibi daha ayrıntılı bilgi, aynı yaklaşımı kullanılarak eklenebilir.  
  
### <a name="accessing-the-visual-studio-api"></a>Visual Studio API erişme  
 Ayarı `hostspecific` özniteliği `<#@template#>` yönergesi verir erişim sağlamak şablon [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] API. Şablon Şablon kodunda mutlak bir dosya yolu kullanmaktan kaçınmak için proje dosyalarının konumunu almak için bunu kullanabilirsiniz.  
  
```  
<#@ template debug="false" hostspecific="true" language="C#" #>  
...  
<#@ assembly name="EnvDTE" #>  
...  
EnvDTE.DTE dte = (EnvDTE.DTE) ((IServiceProvider) this.Host)  
                       .GetService(typeof(EnvDTE.DTE));  
// Open the prototype document.  
XmlDocument doc = new XmlDocument();  
doc.Load(System.IO.Path.Combine(dte.ActiveDocument.Path, "exampleXml.xml"));  
```  
  
## <a name="completing-the-text-template"></a>Metin şablonu Tamamlanıyor  
 Aşağıdaki şablonu içeriği derlemek ve çalıştırmak test kodu veren kod oluşturur.  
  
```  
<#@ template debug="false" hostspecific="true" language="C#" #>  
<#@ output extension=".cs" #>  
<#@ assembly name="System.Xml" #>  
<#@ assembly name="EnvDTE" #>  
<#@ import namespace="System.Xml" #>  
<#@ import namespace="System.Collections.Generic" #>  
using System;using System.Collections.Generic;using System.Linq;using System.Xml;namespace MyProject{  
<#  
 // Map node name --> child name --> child node type  
 Dictionary<string, Dictionary<string, XmlNodeType>> nodeTypes = new Dictionary<string, Dictionary<string, XmlNodeType>>();  
  
 // The Visual Studio host, to get the local file path.  
 EnvDTE.DTE dte = (EnvDTE.DTE) ((IServiceProvider) this.Host)  
                       .GetService(typeof(EnvDTE.DTE));  
 // Open the prototype document.  
 XmlDocument doc = new XmlDocument();  
 doc.Load(System.IO.Path.Combine(dte.ActiveDocument.Path, "exampleXml.xml"));  
 // Inspect all the nodes in the document.  
 // The example might contain many nodes of the same type,   
 // so make a dictionary of node types and their children.  
 foreach (XmlNode node in doc.SelectNodes("//*"))  
 {  
   Dictionary<string, XmlNodeType> subs = null;  
   if (!nodeTypes.TryGetValue(node.Name, out subs))  
   {  
     subs = new Dictionary<string, XmlNodeType>();  
     nodeTypes.Add(node.Name, subs);  
   }  
   foreach (XmlNode child in node.ChildNodes)  
   {  
     subs[child.Name] = child.NodeType;  
   }   
   foreach (XmlNode child in node.Attributes)  
   {  
     subs[child.Name] = child.NodeType;  
   }  
 }  
 // Generate a class for each node type.  
 foreach (string className in nodeTypes.Keys)  
 {  
    // Capitalize the first character of the name.  
#>  
    partial class <#= UpperInitial(className) #>  
    {      private XmlNode thisNode;      public <#= UpperInitial(className) #>(XmlNode node)       { thisNode = node; }  
  
<#  
    // Generate a property for each child.  
    foreach (string childName in nodeTypes[className].Keys)  
    {  
      // Allow for different types of child.  
      switch (nodeTypes[className][childName])  
      {  
         // Child nodes:  
         case XmlNodeType.Element:  
#>  
      public IEnumerable<<#=UpperInitial(childName)#>><#=UpperInitial(childName) #>      {         get         {            foreach (XmlNode node in                thisNode.SelectNodes("<#=childName#>"))              yield return new <#=UpperInitial(childName)#>(node);       } }  
<#  
         break;  
         // Child attributes:  
         case XmlNodeType.Attribute:  
#>  
      public string <#=childName #>      { get { return thisNode.Attributes["<#=childName#>"].Value; } }  
<#  
         break;  
         // Plain text:  
         case XmlNodeType.Text:  
#>  
      public string Text  { get { return thisNode.InnerText; } }  
<#  
         break;  
       } // switch  
     } // foreach class child  
  // End of the generated class:  
#>  
   }   
<#  
 } // foreach class  
  
   // Add a constructor for the root class   
   // that accepts an XML filename.  
   string rootClassName = doc.SelectSingleNode("*").Name;  
#>  
   partial class <#= UpperInitial(rootClassName) #>   {      public <#= UpperInitial(rootClassName) #>(string fileName){        XmlDocument doc = new XmlDocument();        doc.Load(fileName);        thisNode = doc.SelectSingleNode("<#=rootClassName#>");}   }}  
<#+  
   private string UpperInitial(string name)  
   {  
      return name[0].ToString().ToUpperInvariant() + name.Substring(1);  
   }  
#>  
```  
  
### <a name="running-the-test-program"></a>Test programı çalıştırma  
 Konsol uygulaması ana test yöntemine aşağıdaki satırları yürütülür. Program hata ayıklama modunda çalıştırmak için F5 tuşuna basın:  
  
```  
using System;  
namespace MyProject  
{ class Program  
  { static void Main(string[] args)  
    { new CodeGeneratorTest().TestMethod();  
      // Allow user to see the output:  
      Console.ReadLine();  
} } }  
```  
  
### <a name="writing-and-updating-the-application"></a>Yazma ve uygulama güncelleştiriliyor  
 Uygulama artık genel XML kodunu kullanarak yerine oluşturulan sınıflar, kesin türü belirtilmiş stilde yazılabilir.  
  
 XML Şeması değiştiğinde yeni sınıflar kolayca oluşturulabilir. Derleyici, uygulama kodu nereye güncelleştirilmelidir Geliştirici söyler.  
  
 Örnek XML dosyası değiştirildiğinde sınıfları yeniden oluşturmak için tıklatın **tüm şablonları dönüştürme** Çözüm Gezgini araç çubuğunda.  
  
## <a name="conclusion"></a>Sonuç  
 Bu anlatımda çeşitli teknikleri ve kod oluşturma avantajları gösterilir:  
  
-   *Kod oluşturma* uygulamanızın kaynak kodunu parçası oluşturma bir *modeli*. Model uygulama etki alanı için uygun bir biçimde bilgileri içerir ve uygulamanın ömrü boyunca değişebilir.  
  
-   Güçlü bir yararı kod oluşturma ' dir. Model bilgileri kullanıcıya daha uygun bir biçimde temsil ederken, oluşturulan kod türleri kümesi kullanarak bilgi ile mücadele etmek için uygulamanın diğer bölümleri sağlar.  
  
-   IntelliSense ve derleyici modeli şemasına yeni kodu yazarken hem şema güncelleştirildiğinde aynılarını kod oluşturmanıza yardımcı olur.  
  
-   Bir tek eylemlerin şablon dosyası projeye ek avantajlar sağlar.  
  
-   Metin şablonu geliştirilmiş ve hızlı bir şekilde ve artımlı olarak test.  
  
 Bu kılavuzda, program kodunu gerçekte bir model, temsili bir örnek uygulama işleyecek XML dosyalarının örneğinden oluşturulur. Daha resmi bir yaklaşım XML Şeması şablonda .xsd dosyası ya da bir etki alanına özgü dil tanımı girdisi olacaktır. Bu yaklaşımı bir ilişki Çokluk gibi özellikleri belirlemek için şablonu kolaylaştırmak.  
  
## <a name="troubleshooting-the-text-template"></a>Metin şablonu sorunlarını giderme  
 Şablon dönüştürme veya derleme hataları gördüyseniz **hata listesi**, veya çıktı dosyası doğru şekilde oluşturulmamış, açıklanan teknikleri ile metin şablonu giderebilirsiniz [oluşturma TextTransform yardımcı programı ile dosya](../modeling/generating-files-with-the-texttransform-utility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [T4 metin şablonları kullanarak tasarım zamanı kodu oluşturma](../modeling/design-time-code-generation-by-using-t4-text-templates.md)   
 [T4 Metin Şablonu Yazma](../modeling/writing-a-t4-text-template.md)