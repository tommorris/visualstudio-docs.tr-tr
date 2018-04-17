---
title: DGML dosyalarını düzenleyerek kod haritalarını özelleştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency graphs, creating path aliases
- dependency graphs, linking items to nodes
- graph documents, creating path aliases
- dependency graphs, grouping nodes
- graph documents, editing
- graph documents, linking items to nodes
- graph documents, customizing
- graph documentings, assigning categories and properties
- dependency graphs, editing
- dependency graphs, customizing
- graph documents, grouping nodes
- dependency graphs, assigning categories and properties
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 2a23bc9b82941fda5a771f49a2aaf5c944a210bf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="customize-code-maps-by-editing-the-dgml-files"></a>DGML dosyalarını düzenleyerek kod haritalarını özelleştirme
Kod Haritası özelleştirmek için bir haritanın yönlendirilmiş grafik biçimlendirme dili (.dgml) dosyasını düzenleyebilirsiniz. Örneğin, özel stiller belirtin, özellikleri ve kategorileri kod öğeleri ve bağlantıları veya bağlantı belgeleri veya URL'leri kod öğeleri veya bağlantılar atamak için öğelerini düzenleyebilirsiniz. DGML öğeleri hakkında daha fazla bilgi için bkz: [yönlendirilmiş grafik biçimlendirme dili (DGML) başvurusu](../modeling/directed-graph-markup-language-dgml-reference.md).  
  
 Kod haritanın .dgml dosyasını bir metin veya XML Düzenleyicisi'ni düzenleyin. Harita Visual Studio çözümünün parçası ise seçin **Çözüm Gezgini**kısayol menüsünü açın ve seçin **birlikte Aç**, **(metin) XML Düzenleyicisi**.  
  
> [!NOTE]
>  Kod haritaları oluşturmak için Visual Studio Enterprise olması gerekir. Visual Studio'da kod Haritası düzenlediğinizde, kullanılmayan DGML öğelerini ve özniteliklerini .dgml dosyasını kaydettiğinizde, onları silerek temizler. Yeni bağlantıları el ile eklediğinizde ayrıca kod öğeleri otomatik olarak oluşturur. .dgml dosyasını kaydettiğinizde, bir öğeye eklediğiniz tüm öznitelikler kendilerini alfabetik sırada yeniden düzenleyebilir.  
  
##  <a name="OrganizeNodes"></a> Grup kod öğeleri  
 Yeni gruplar eklemek veya bir gruba varolan düğümleri dönüştürebilirsiniz.  
  
1.  .Dgml dosyasını bir metin veya XML düzenleyicisinde açın.  
  
2.  Kod öğesi için bir grubu dönüştürmek için Bul `<Node/>` bu kodu öğesinin öğesinin.  
  
     \- veya -  
  
     Yeni bir grup eklemek için Bul `<Nodes>` bölümü. Yeni bir ekleme `<Node/>` öğesi.  
  
3.  İçinde `<Node/>` öğesi ekleme bir `Group` öznitelik grubu genişletilmiş veya daraltılmış görüntülenip görüntülenmeyeceğini belirtin. Örneğin:  
  
    ```xml  
    <Nodes>  
       <Node Id="MyFirstGroup" Group="Expanded" />  
       <Node Id="MySecondGroup" Group="Collapsed" />  
    </Nodes>  
    ```  
  
4.  İçinde `<Links>` bölümünde, olduğundan emin olun bir `<Link/>` Grup code öğesi ve kendi alt kod öğeleri arasındaki her ilişki için varolan aşağıdaki özniteliklere sahip öğe:  
  
    -   A `Source` Grup code öğesi belirten özniteliği  
  
    -   A `Target` alt kod öğesi belirten özniteliği  
  
    -   A `Category` belirten özniteliği bir `Contains` Grup code öğesi ve kendi alt kod öğesi arasındaki ilişki  
  
     Örneğin:  
  
    ```xml  
    <Links>  
       <Link Category="Contains" Source="MyFirstNewGroup" Target="FirstGroupChildOne" />  
       <Link Category ="Contains" Source="MyFirstNewGroup" Target="FirstGroupChildTwo" />  
       <Link Category ="Contains" Source="MySecondNewGroup" Target="SecondGroupChildOne" />  
       <Link Category="Contains" Source="MySecondNewGroup" Target="SecondGroupChildTwo" />  
    </Links>  
    ```  
  
     Hakkında daha fazla bilgi için `Category` özniteliği için bkz: [kod öğeleri ve bağlantıları için kategoriler atayın](#AssignCategories).  
  
##  <a name="ChangeGraphStyle"></a> Harita stilini değiştirme  
 Haritanın .dgml dosyasını düzenleyerek haritanın kenarlık renk ve arka plan rengini değiştirebilirsiniz. Bağlantıların ve kod öğeleri stilini değiştirmek için bkz: [bağlantıların ve kod öğeleri stilini değiştirme](#Highlight).  
  
1.  .Dgml dosyasını bir metin veya XML düzenleyicisinde açın.  
  
2.  İçinde `<DirectedGraph>` öğesi, kendi stilini değiştirmek için aşağıdaki özniteliklerin herhangi birini ekleyin:  
  
     Arka plan rengi  
  
    ```xml  
    Background="ColorNameOrHexadecimalValue"  
    ```  
  
     Kenarlık rengi  
  
    ```xml  
    Stroke="StrokeValue"  
    ```  
  
     Örneğin:  
  
    ```xml  
    <DirectedGraph Background="Green" xmlns="http://schemas.microsoft.com/vs/2009/dgml" >  
       ...  
       ...  
    </DirectedGraph>  
    ```  
  
##  <a name="Highlight"></a> Bağlantıların ve kod öğeleri stilini değiştirme  
  
###  <a name="CreateCustomStyles"></a>   
 Aşağıdaki kod öğeleri özel stiller uygulayabilirsiniz:  
  
-   Tek kod öğeleri ve bağlantıları  
  
-   Kod öğeleri ve bağlantılar grupları  
  
-   Kod öğeleri ve belirli koşullara göre bağlantılar grupları  
  
> [!TIP]
>  Çok sayıda kod öğeleri veya bağlantılar stilleri yinelenen varsa, bu kod öğeleri veya bağlantılar için bir kategori uygulama ve sonra bu kategoriye stil uygulayarak düşünebilirsiniz. Daha fazla bilgi için bkz: [kod öğeleri ve bağlantıları için kategoriler atayın](#AssignCategories) ve [atamak özellikleri kod öğeleri ve bağlantıları](#AssignProperties).  
  
##### <a name="to-apply-a-custom-style-to-a-single-code-element"></a>Tek code öğesi için özel bir stil uygulamak için  
  
1.  .Dgml dosyasını bir metin veya XML düzenleyicisinde açın.  
  
2.  Kod öğenin Bul `<Node/>` öğesi. Stilini özelleştirmek için bu özelliklerden herhangi birini ekleyin:  
  
     Arka plan rengi  
  
    ```xml  
    Background="ColorNameOrHexadecimalValue"  
    ```  
  
     Anahat  
  
    ```xml  
    Stroke="ColorNameOrHexadecimalValue"  
    ```  
  
     Anahat kalınlığı  
  
    ```xml  
    StrokeThickness="StrokeValue"  
    ```  
  
     Metin rengi  
  
    ```xml  
    Foreground="ColorNameOrHexadecimalValue"  
    ```  
  
     Simge  
  
    ```xml  
    Icon="IconFilePathLocation"  
    ```  
  
     Metin boyutu  
  
    ```xml  
    FontSize="FontSizeValue"  
    ```  
  
     Metin türü  
  
    ```xml  
    FontFamily="FontFamilyName"  
    ```  
  
     Metin ağırlığı  
  
    ```xml  
    FontWeight="FontWeightValue"  
    ```  
  
     Metin stili  
  
    ```xml  
    FontStyle="FontStyleName"  
    ```  
  
     Örneğin, belirtebilirsiniz `Italic` metin stili.  
  
     Doku  
  
    ```xml  
    Style="Glass"  
    ```  
  
     - veya -  
  
    ```xml  
    Style="Plain"  
    ```  
  
     Şekil  
  
     Simge ile şeklini değiştirmek için `Shape` özelliğine `None` ve `Icon` simge dosyası yolu için özellik.  
  
    ```xml  
    Shape="ShapeFilePathLocation"  
    ```  
  
     Örneğin:  
  
    ```xml  
    <Nodes>  
       <Node Id="MyNode" Background="#FF008000" Stroke="#FF000000"  
       Foreground="#FFFFFFFF" Icon="...\Icons\Globe.png"/>  
    </Nodes>  
    ```  
  
##### <a name="to-apply-a-custom-style-to-a-single-link"></a>Özel bir stili tek bir bağlantıya uygulamak için  
  
1.  .Dgml dosyasını bir metin veya XML düzenleyicisinde açın.  
  
2.  Bul `<Link/>` hem kaynak kod öğesi hem de hedef code öğesi isimlerini içeren öğe.  
  
3.  İçinde `<Link/>` öğesi, stilini özelleştirmek için aşağıdaki özniteliklerin herhangi birini ekleyin:  
  
     Anahat ve ok ucu rengi  
  
    ```xml  
    Stroke="ColorNameOrHexadecimalValue"  
    ```  
  
     Anahat kalınlığı  
  
    ```xml  
    StrokeThickness="StrokeValue"  
    ```  
  
     Anahat stili  
  
    ```xml  
    StrokeDashArray="StrokeArrayValues"  
    ```  
  
     Örneğin:  
  
    ```xml  
    <Links>  
       <Link Source="MyFirstNode" Target="MySecondNode" Background="Green" Stroke="#FF000000" StrokeDashArray="2,2"/>  
    </Links>  
    ```  
  
##### <a name="to-apply-custom-styles-to-a-group-of-code-elements-or-links"></a>Kod öğeleri veya bağlantılar grubuna özel stiller uygulamak için  
  
1.  .Dgml dosyasını bir metin veya XML düzenleyicisinde açın.  
  
2.  Varsa bir `<Styles></Styles>` öğesi olmayabilir, altında bir tane ekleyin `<DirectedGraph></DirectedGraph>` öğeden sonra `<Links></Links>` öğesi.  
  
3.  İçinde `<Styles></Styles>` öğesi altında `<Style/>` öğesi ve aşağıdaki öznitelikleri belirtebilirsiniz:  
  
    -   `TargetType="Node` &#124; `Link | Graph"`  
  
    -   `GroupLabel="` *NameInLegendBox* `"`  
  
    -   `ValueLabel="` *NameInStylePickerBox* `"`  
  
     Tüm hedef türlere özel bir stil uygulamak için bir koşul kullanmayın.  
  
##### <a name="to-apply-a-conditional-style-to-groups-of-code-elements-or-links"></a>Kod öğeleri veya bağlantılar gruplarına koşullu bir stil uygulamak için  
  
1.  .Dgml dosyasını bir metin veya XML düzenleyicisinde açın.  
  
2.  İçinde `<Style/>` öğesi ekleme bir `<Condition/>` içeren öğe bir `Expression` bir Boole değeri döndüren bir ifadeye belirtmek için özniteliği.  
  
     Örneğin:  
  
    ```xml  
    <Condition Expression="MyCategory"/>  
    ```  
  
     - veya -  
  
    ```xml  
    <Condition Expression="MyCategory > 100"/>  
    ```  
  
     - veya -  
  
    ```xml  
    <Condition Expression="HasCategory('MyCategory')"/>  
    ```  
  
     Bu ifade aşağıdaki Backus-Naur Form (BNF) sözdizimini kullanır:  
  
     <Expression> ::= <BinaryExpression> &#124; <UnaryExpression> &#124; "("<Expression>")" &#124; <MemberBindings> &#124; <Literal> &#124; <Number>  
  
     <BinaryExpression> ::= <Expression> <Operator> <Expression>  
  
     <UnaryExpression> ::= "!" <Expression> &#124; "+" <Expression> &#124; "-" <Expression>  
  
     <Operator> :: = "<" &#124; "\<=" &#124; "=" &#124; "> =" &#124; ">" &#124; "! =" &#124; "veya" &#124; "ve" &#124; "+" &#124; "*" &#124; "/" &#124; "-"  
  
     <MemberBindings> ::= <MemberBindings> &#124; <MemberBinding> "." <MemberBinding>  
  
     <MemberBinding> ::= <MethodCall> &#124; <PropertyGet>  
  
     <MethodCall> ::= <Identifier> "(" <MethodArgs> ")"  
  
     <PropertyGet> :: Tanıtıcısı =  
  
     <MethodArgs> ::= <Expression> &#124; <Expression> "," <MethodArgs> &#124; <empty>  
  
     <Identifier> ::= [^. ]*  
  
     <Literal> :: = tek veya çift tırnak içine alınmış dize sabit değeri  
  
     <Number> :: isteğe bağlı bir ondalık ayırıcısı olan rakam dizesiyle =  
  
     Birden çok belirtebilirsiniz `<Condition/>` öğeleri tüm stil uygulamak için true olmalıdır.  
  
3.  Sonra bir sonraki satırdaki `<Condition/>` öğesi, bir veya daha çok eklemek `<Setter/>` belirtmek için öğesi bir `Property` özniteliğini ve bir sabit `Value` özniteliği ya da bir hesaplanan `Expression` harita, kod öğeleri ya da uyan bağlantılara uygulamak için özniteliği Koşul.  
  
     Örneğin:  
  
    ```xml  
    <Setter Property="BackGround" Value="Green"/>  
    ```  
  
 Kod öğesi yeşil görüntülenir veya kırmızı bağlı basit tam bir örnek, aşağıdaki iki koşul belirtir, `Passed` kategori ayarlanmış `True` veya `False`:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<DirectedGraph xmlns="http://schemas.microsoft.com/vs/2009/dgml">  
   <Nodes>  
      <Node Id="MyFirstNode" Passed="True" />  
      <Node Id="MySecondNode" Passed="False" />  
   </Nodes>  
   <Links>  
   </Links>  
   <Styles>  
      <Style TargetType="Node" GroupLabel="Passed" ValueLabel="True">  
         <Condition Expression="Passed='True'"/>  
         <Setter Property="Background" Value="Green"/>  
      </Style>  
      <Style TargetType="Node" GroupLabel="Passed" ValueLabel="False">  
         <Condition Expression="Passed='False'"/>  
         <Setter Property="Background" Value="Red"/>  
      </Style>  
   </Styles>  
</DirectedGraph>  
```  
  
 Aşağıdaki tabloda kullanabileceğiniz bazı örnek koşullar bulunmaktadır:  
  
 Yazı tipi boyutunu ayrıca Kod öğesi boyutunu değiştirir kod satırı sayısını bir işlevi olarak ayarlayın. Bu örnek, birden çok özelliği ayarlamak için tek bir koşullu ifade kullanır. `FontSize` ve `FontFamily`.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<DirectedGraph xmlns="http://schemas.microsoft.com/vs/2009/dgml">  
<Nodes>  
   <Node Id="Class1" LinesOfCode ="200" />  
   <Node Id="Class2" LinesOfCode ="1000" />  
   <Node Id="Class3" LinesOfCode ="20" />  
</Nodes>  
<Properties>  
   <Property Id="LinesOfCode" Label="LinesOfCode" Description="LinesOfCode" DataType="System.Int32" />  
</Properties>  
<Styles>  
   <Style TargetType="Node" GroupLabel="LinesOfCode" ValueLabel="Function">  
      <Condition Expression="LinesOfCode > 0" />  
      <Setter Property="FontSize" Expression="Math.Max(9,Math.Sqrt(LinesOfCode))" />  
      <Setter Property="FontFamily" Value="Papyrus" />  
   </Style>  
</Styles>  
</DirectedGraph>  
```  
  
 Temel bir kod öğesi arka plan rengini ayarlama `Coverage` özelliği. Stiller, benzer göründükleri sırada değerlendirilir `if-else` deyimleri.  
  
 Bu örnekte:  
  
1.  Varsa `Coverage` > 80, ardından `Background` yeşil özelliğine.  
  
2.  Else IF `Coverage` > 50 ardından `Background` turuncu gölgeye özelliğine dayalı değerine göre `Coverage` özelliği.  
  
3.  Else ayarlamak `Background` kırmızı gölgeye özelliğine dayalı değerine göre `Coverage` özelliği.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<DirectedGraph xmlns="http://schemas.microsoft.com/vs/2009/dgml">  
<Nodes>  
   <Node Id="Class1" Coverage="58" />  
   <Node Id="Class2" Coverage="95" />  
   <Node Id="Class3" Coverage="32" />  
</Nodes>  
<Properties>  
   <Property Id="Coverage" Label="Coverage" Description="Code coverage as a percentage of blocks" DataType="Double" />  
</Properties>  
<Styles>  
   <Style TargetType="Node" GroupLabel="Coverage" ValueLabel="Good">  
      <Condition Expression="Coverage > 80" />  
      <Setter Property="Background" Value="Green" />  
   </Style>  
   <Style TargetType="Node" GroupLabel="Coverage" ValueLabel="OK">  
      <Condition Expression="Coverage > 50" />  
      <Setter Property="Background" Expression="Color.FromRgb(180 * Math.Max(1, (80 - Coverage) / 30), 180, 0)" />  
   </Style>  
   <Style TargetType="Node" GroupLabel="Coverage" ValueLabel="Bad">  
      <Setter Property="Background" Expression="Color.FromRgb(180, 180 * Coverage / 50, 0)" />  
   </Style>  
</Styles>  
</DirectedGraph>  
```  
  
 Ayarlama `Shape` özelliğine `None` böylece simgesini şeklini değiştirir. Kullanım `Icon` simgenin konumunu belirtmek için özellik.  
  
```xml  
<DirectedGraph xmlns="http://schemas.microsoft.com/vs/2009/dgml">  
<Nodes>  
   <Node Id="Automation" Category="Test" Label="Automation" />  
   <Node Id="C# Provider" Category="Provider" Label="C# Provider" />  
</Nodes>  
<Categories>  
   <Category Id="Provider" Icon="...\Icons\Module.png" Shape="None" />  
   <Category Id="Test" Icon="...\Icons\Page.png" Shape="None" />  
</Categories>  
<Properties>  
   <Property Id="Icon" DataType="System.String" />  
   <Property Id="Label" Label="Label" Description="Displayable label of an Annotatable object" DataType="System.String" />  
   <Property Id="Shape" DataType="System.String" />  
</Properties>  
<Styles>  
   <Style TargetType="Node" GroupLabel="Group" ValueLabel="Has category">  
      <Condition Expression="HasCategory('Group')" />  
      <Setter Property="Background" Value="#80008080" />  
   </Style>  
   <Style TargetType="Node">  
      <Setter Property="HorizontalAlignment" Value="Center" />  
   </Style>  
</Styles>  
</DirectedGraph>  
```  
  
##  <a name="AssignProperties"></a> Kod öğeleri ve bağlantılara özellikler ata  
 Kod öğeleri ve bağlantıları özellikler atayarak düzenleyebilirsiniz. Örneğin, böylece bunları grup kendi stilini değiştirin veya gizleme belirli özelliklere sahip kod öğeleri seçebilirsiniz.  
  
#### <a name="to-assign-a-property-to-a-code-element"></a>Kod öğesi için bir özellik atamak için  
  
1.  .Dgml dosyasını bir metin veya XML düzenleyicisinde açın.  
  
2.  Bul `<Node/>` bu kodu öğesinin öğesinin. Özelliğin adını ve değerini belirtin. Örneğin:  
  
    ```xml  
    <Nodes>  
       <Node Id="MyNode" MyPropertyName="PropertyValue" />  
    </Nodes>  
    ```  
  
3.  Ekleme bir `<Property/>` öğesine `<Properties>` bölüm öznitelikleri gibi görünen adı ve veri türü belirtin:  
  
    ```xml  
    <Properties>  
       <Property Id="MyPropertyName" Label="My Property" DataType="System.DataType"/>  
    </Properties>  
    ```  
  
#### <a name="to-assign-a-property-to-a-link"></a>Bağlantıya bir özellik atamak için  
  
1.  .Dgml dosyasını bir metin veya XML düzenleyicisinde açın.  
  
2.  Bul `<Link/>` hem kaynak kod öğesi hem de hedef code öğesi isimlerini içeren öğe.  
  
3.  İçinde `<Node/>` öğesi, özelliğin adını ve değerini belirtin. Örneğin:  
  
    ```xml  
    <Links>  
       <Link Source="MyFirstNode" Target="MySecondNode" MyPropertyName="PropertyValue" />  
    </Links>  
    ```  
  
4.  Ekleme bir `<Property/>` öğesine `<Properties>` bölüm öznitelikleri gibi görünen adı ve veri türü belirtin:  
  
    ```xml  
    <Properties>  
       <Property Id="MyPropertyName" Label="My Property Name" DataType="System.DataType"/>  
    </Properties>  
    ```  
  
##  <a name="AssignCategories"></a> Kod öğeleri ve bağlantıları için kategoriler atayın  
 Aşağıdaki bölümlerde, kategoriler atayarak kod öğeleri nasıl düzenleyebilirsiniz göstermek ve hiyerarşik oluşturabilirsiniz nasıl yardımcı kategorileri kod öğelerini düzenlemek ve devralma kullanarak alt kategorileri öznitelikleri ekleyin.  
  
#### <a name="to-assign-a-category-to-a-code-element"></a>Kod öğesi için bir kategori atamak için  
  
-   .Dgml dosyasını bir metin veya XML düzenleyicisinde açın.  
  
-   Bul `<Node/>` istediğiniz kod öğesinin öğesinin.  
  
-   İçinde `<Node/>` öğesi ekleme bir `Category` özniteliği kategorisinin adını belirtin. Örneğin:  
  
    ```xml  
    <Nodes>  
       <Node Id="MyNode" Category="MyCategory" />  
    </Nodes>  
    ```  
  
     Ekleme bir `<Category/>` öğesine `<Categories>` kullanabileceğiniz bölümüne `Label` özniteliği bu kategori için görüntü metnini belirtin:  
  
    ```xml  
    <Categories>  
       <Category Id="MyCategory" Label="My Category" />  
    </Categories>  
    ```  
  
#### <a name="to-assign-a-category-to-a-link"></a>Bir bağlantıya kategori atamak için  
  
1.  .Dgml dosyasını bir metin veya XML düzenleyicisinde açın.  
  
2.  Bul `<Link/>` hem kaynak kod öğesi hem de hedef code öğesi isimlerini içeren öğe.  
  
3.  İçinde `<Link/>` öğesi ekleme bir `Category` özniteliği kategorisinin adını belirtin. Örneğin:  
  
    ```xml  
    <Links>  
       <Link Source="MyFirstNode" Target="MySecondNode" Category="MyCategory"  
    </Links>  
    ```  
  
4.  Ekleme bir `<Category/>` öğesine `<Categories>` kullanabileceğiniz bölümüne `Label` özniteliği bu kategori için görüntü metnini belirtin:  
  
    ```xml  
    <Categories>  
       <Category Id="MyCategory" Label="My Category" />  
    </Categories>  
    ```  
  
#### <a name="to-create-hierarchical-categories"></a>Hiyerarşik kategoriler oluşturmak için  
  
1.  .Dgml dosyasını bir metin veya XML düzenleyicisinde açın.  
  
2.  Ekleme bir `<Category/>` üst kategori öğesi ve ardından ekleyin `BasedOn` özniteliği çocuk kategorisinin `<Category/>` öğesi.  
  
     Örneğin:  
  
    ```xml  
    <Nodes>  
       <Node Id="MyFirstNode" Label="My First Node" Category= "MyCategory" />  
       <Node Id="MySecondNode" Label="My Second Node" />  
    </Nodes>  
    <Links>  
       <Link Source="MyFirstNode" Target="MySecondNode" />  
    </Links>  
    <Categories>  
       <Category Id="MyCategory" Label="My Category" BasedOn="MyParentCategory"/>  
       <Category Id="MyParentCategory" Label="My Parent Category" Background="Green"/>  
    </Categories>  
    ```  
  
     Bu örnekte, arka planını `MyFirstNode` yeşil olduğundan kendi `Category` öznitelik devralır `Background` özniteliği `MyParentCategory`.  
  
##  <a name="AddReferences"></a> Bağlantı belge veya kod öğeleri ve bağlantıları URL'leri  
 Belgeler veya URL'ler kod öğeleri veya bağlantılar haritanın .dgml dosyasını düzenleyerek ve ekleyerek bağlayabilirsiniz bir `Reference` özniteliğini `<Node/>` kod öğesinin öğesinin veya `<Link/>` öğesi için bir bağlantı. Ardından, açın ve bu içeriği code öğesi veya bağlantı görüntüleyin. `Reference` Özniteliği o içeriğin yolunu belirtir. Bu, .dgml dosya konumu veya mutlak yol ile göreli bir yol olabilir.  
  
> [!CAUTION]
>  Göreli yollar kullanıyorsanız ve .dgml dosyası farklı bir konuma taşınırsa, bu yollar artık çözümlenmez. Bağlantılı içeriği açmaya ve görüntülemeye çalıştığınızda, içeriğin görüntülenemediğini bildiren bir hata ortaya çıkar.  
  
 Örneğin, aşağıdaki kod öğeleri bağlamak isteyebilirsiniz:  
  
-   Bir sınıfa değişiklikleri açıklamak için kod öğesine bir sınıf için bir iş code öğesi, belge veya başka bir .dgml dosya URL'sini bağlayabilirsiniz.  
  
-   Yazılımın mantıksal mimarisi katmanda temsil eden bir grup kodu öğesi için bir bağımlılık diyagramı bağlayabilirsiniz.  
  
-   Bir arabirimi kullanıma sunan bir bileşen hakkında daha fazla bilgi göstermek için bu arabirimin kod öğesine bileşen diyagramı bağlayabilirsiniz.  
  
-   Kod öğesi bir Team Foundation Server iş öğesi, hataya veya kod öğesine ilgili diğer bazı bilgilere bağlayın.  
  
#### <a name="to-link-a-document-or-url-to-a-code-element"></a>Bir belge veya URL bir kod öğesine bağlamak için  
  
1.  .Dgml dosyasını bir metin veya XML düzenleyicisinde açın.  
  
2.  Bul `<Node/>` istediğiniz kod öğesinin öğesinin.  
  
3.  Aşağıdaki tabloda yer alan görevlerden birini gerçekleştirin:  
  
     Tek bir kod öğesi  
  
    -   İçinde `<Node/>` veya `<Link/>` öğesi ekleme bir `Reference` code öğesi konumunu belirtmek için öznitelik.  
  
        > [!NOTE]
        >  Yalnızca bir bulunabilir `Reference` öğesi başına öznitelik.  
  
     Örneğin:  
  
    ```xml  
    <Nodes>  
       <Node Id="MyNode" Reference="MyDocument.txt" />  
    </Nodes>  
    <Properties>  
       <Property Id="Reference" Label="My Document" DataType="System.String" IsReference="True" />  
    </Properties>  
    ```  
  
     Birden çok kod öğeleri  
  
    1.  İçinde `<Node/>` veya `<Link/>` öğesi, her başvurunun konumunu belirtmek için yeni bir öznitelik ekleyin.  
  
    2.  İçinde `<Properties>` bölümü:  
  
        1.  Ekleme bir `<Property/>` öğesi için her yeni başvuru türü.  
  
        2.  Ayarlama `Id` özniteliğini yeni başvuru özniteliği adını.  
  
        3.  Ekleme `IsReference` özniteliği ve ayarlamak `True` başvuruyu kod öğenin üzerinde görünür yapmak için **başvuru Git** kısayol menüsü.  
  
        4.  Kullanım `Label` kod öğenin üzerinde görüntülenecek metni belirtmek için özniteliği **başvuru gidin** kısayol menüsü.  
  
     Örneğin:  
  
    ```xml  
    <Nodes>  
       <Node Id="MyNode" SequenceDiagram="MySequenceDiagram.sequencediagram" ActiveBugs="MyActiveBugs.wiq"/>  
    </Nodes>  
    <Properties>  
       <Property Id="SequenceDiagram" Label="My Sequence Diagram" DataType="System.String" IsReference="True" />  
       <Property Id="ActiveBugs" Label="Active Bugs" DataType="System.String" IsReference="True" />  
    </Properties>  
    ```  
  
     Haritada kod öğesinin adı altı çizili olarak görünür. Kod öğesi veya bağlantı için kısayol menüsü açtığınızda göreceğiniz bir **başvuru Git** seçmenizi bağlantılı kod öğeleri içeren kısayol menüsü.  
  
4.  Kullanım `ReferenceTemplate` öznitelik başvurusu bu dizeyi yinelenen yerine birden çok başvuru tarafından kullanılan bir URL gibi ortak bir dize belirtin.  
  
     `ReferenceTemplate` Özniteliği başvuru değeri için bir yer tutucu belirtir. Aşağıdaki örnekte, `{0}` yer tutucu `ReferenceTemplate` öznitelik değerleri tarafından değiştirilecek `MyFirstReference` ve `MySecondReference` öznitelikleri `<Node/>` öğesinin tam yol üretmek için:  
  
    ```xml  
    <Nodes>  
       <Node Id="MyNode" MyFirstReference="MyFirstDocument" MySecondReference="MySecondDocument"/>  
       <Node Id="MySecondNode" MyFirstReference="AnotherFirstDocument" MySecondReference="AnotherSecondDocument"/>  
    </Nodes>  
    <Properties>  
       <Property Id="MyFirstReference" Label="My First Document" DataType="System.String" IsReference="True" ReferenceTemplate="http://www.Fabrikam.com/FirstDocuments/{0}.asp"/>  
       <Property Id="MySecondReference" Label="My Second Document" DataType="System.String" IsReference="True" ReferenceTemplate=" http://www.Fabrikam.com/SecondDocuments/{0}.asp"/>  
    </Properties>  
    ```  
  
5.  Başvurulan code öğesi veya eşlemesinden kod öğeleri görüntülemek için kod öğesi veya bağlantı için kısayol menüsünü açın. Seçin **başvuru Git** ve ardından kod öğesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çözümlerinizdeki bağımlılıkları eşleme](../modeling/map-dependencies-across-your-solutions.md)   
 [Uygulamalarınızda hata ayıklamak için kod haritalarını kullanma](../modeling/use-code-maps-to-debug-your-applications.md)   
 [Kod Haritası çözümleyicilerini kullanarak olası sorunları bulma](../modeling/find-potential-problems-using-code-map-analyzers.md)   
 [Gözat ve kod haritalarını bunları yeniden düzenleme](../modeling/browse-and-rearrange-code-maps.md)   
 [Yönlendirilmiş Grafik İşaretleme Dili (DGML) başvurusu](../modeling/directed-graph-markup-language-dgml-reference.md)
