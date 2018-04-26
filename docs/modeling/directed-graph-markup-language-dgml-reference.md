---
title: Yönlendirilmiş Grafik İşaretleme Dili (DGML) başvurusu
ms.date: 11/04/2016
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 5afd8490f454efd1cb584670ed7c750359e329d7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="directed-graph-markup-language-dgml-reference"></a>Yönlendirilmiş Grafik İşaretleme Dili (DGML) başvurusu

Yönlendirilmiş Grafik Biçimlendirme Dili (DGML) Görselleştirme ve karmaşıklık analizi yapmak için kullanılan bilgileri açıklar ve biçimi Visual Studio'da kod haritalarına kalıcı hale getirmek için kullanılır. Döngüsel ve döngüsel olmayan yönlendirilmiş grafiklerini açıklamak için basit XML kullanır. Yönlendirilmiş bir grafik, bağlantılarla veya kenarlarla bağlanmış bir düğüm kümesidir. Düğümler ve bağlantılar, bir yazılım projesindeki öğeler gibi ağ yapılarını açıklamak için kullanılabilir.

Not bazı Visual Studio sürümleri yalnızca yeteneklerinin bir alt kümesini DGML destek, bkz: [mimari ve Modelleme Araçları sürüm desteği](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

> [!NOTE]
> Bir .dgml dosyasını düzenlerken, IntelliSense her öğe için kullanılabilen öznitelikleri ve değerlerini belirlemenize yardımcı olur. Bir öznitelikte renk belirlemek için "Mavi" gibi genel renklerin adlarını veya "#ffa0b1c3" gibi ARGB onaltılık değerlerini kullanın. DGML Windows Presentation Foundation (WPF) renk tanımı biçimlerinin küçük bir alt kümesini kullanır. Daha fazla bilgi için bkz: [renkleri sınıfı](http://go.microsoft.com/fwlink/?LinkId=182345).

##  <a name="DGML"></a> DGML sözdizimi

Aşağıdaki tabloda DGML içinde kullanılan öğelerinin türleri açıklanmaktadır:

-   `<DirectedGraph></DirectedGraph>`

     Bu öğe kod eşleme (.dgml) belgesinin kök öğesidir. Diğer tüm DGML öğeleri, bu öğe kapsamı içinde görünür.

     Aşağıdaki liste dahil edebileceğiniz isteğe bağlı öznitelikleri tanımlar:

     `Background` -Harita arka plan rengi

     `BackgroundImage` -Harita arka planı olarak kullanılacak bir görüntü dosyasının konumu.

     `GraphDirection` -Map ayarlandığında ağaç düzenine (`Sugiyama`), bağlantıların çoğu belirtilen yönde akması düğümleri düzenleyin: `TopToBottom`, `BottomToTop`, `LeftToRight`, veya `RightToLeft`. Bkz: [harita düzenini değiştirme](../modeling/browse-and-rearrange-code-maps.md#Selecting).

     `Layout` -Map şu düzenlere ayarlayın: `None`, `Sugiyama` (ağaç düzeni) `ForceDirected` (hızlı kümeler) veya `DependencyMatrix`. Bkz: [harita düzenini değiştirme](../modeling/browse-and-rearrange-code-maps.md#Selecting).

     `NeighborhoodDistance` Harita ağaç düzenine veya hızlı kümeler düzenine ayarlandığında, seçilen düğümlerdeki çıktığınızda bağlantılar belirtilen sayıda (1-7) olan düğümler gösterir. Bkz: [harita düzenini değiştirme](../modeling/browse-and-rearrange-code-maps.md#Selecting).

     Örnek:

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <DirectedGraph Title="DrivingTest" Background="Blue" xmlns="http://schemas.microsoft.com/vs/2009/dgml">
       <Nodes>
          ...
       </Nodes>
       <Links>
          ...
       </Links>
       <Categories>
          ...
       </Categories>
       <Properties>
          ...
       </Properties>
    </DirectedGraph>
    ```

-   `<Nodes></Nodes>`

     Bu isteğe bağlı öğe listesini içeren `<Node/>` düğümler haritada tanımlar öğeleri. Daha fazla bilgi için bkz: `<Node/>` öğesi.

    > [!NOTE]
    > Başvuru yaptığınızda tanımlanmamış bir düğümünde bir `<Link/>` harita öğesini oluşturur bir `<Node/>` öğesi otomatik olarak.

     Örnek:

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <DirectedGraph Title="DrivingTest" xmlns="http://schemas.microsoft.com/vs/2009/dgml">
       <Nodes>
          <Node ... />
       </Nodes>
       <Links>
          <Link ... />
       </Links>
    </DirectedGraph>
    ```

-   `<Node/>`

     Bu öğe tek bir düğümü tanımlar. İçinde göründüğü `<Nodes><Nodes/>` öğe listesi.

     Bu öğenin öznitelikleri şunlardır:

     `Id` -Benzersiz bir ad düğüm ve varsayılan değerini `Label` ayrı özniteliği `Label` özniteliği belirtildi. Bu adı eşleşmelidir `Source` veya `Target` başvurduğu bağlantı özniteliği.

     Aşağıdaki liste, dahil edebileceğiniz isteğe bağlı özniteliklerin bazılarını açıklar:

     `Label` -Düğüm görünen adı.

     Stil öznitelikleri. Bkz: [DGML dosyalarını düzenleyerek kod haritalarını özelleştirme](../modeling/customize-code-maps-by-editing-the-dgml-files.md).

     `Category` -Bu özniteliği paylaşan öğeleri tanımlayan bir kategori adı. Daha fazla bilgi için bkz: `<Category/>` öğesi.

     `Property` -Aynı özellik değerine sahip öğeleri tanımlayan bir özellik adı. Daha fazla bilgi için bkz: `<Property/>` öğesi.

     `Group` -Düğümü diğer düğümlere içeriyorsa, bu öznitelik ayarlanırsa `Expanded` veya `Collapsed` göstermek veya gizlemek içeriği. Olmalıdır bir `<Link/>` içeren öğe `Category="Contains"` özniteliği ve üst düğümü kaynak ve hedef düğüm olarak alt düğümlerini olarak belirtir. Bkz: [Grup kod öğeleri](../modeling/customize-code-maps-by-editing-the-dgml-files.md#OrganizeNodes).

     `Visibility` -Bu öznitelik ayarlanırsa `Visible`, `Hidden`, veya `Collapsed`. Kullanan `System.Windows.Visibility`. Bkz: [Gizle veya Göster düğümleri ve bağlantıları](../modeling/browse-and-rearrange-code-maps.md#HidingShowing).

     `Reference` -Bir belge veya URL bağlamak için bu özniteliği ayarlayın. Bkz: [bağlantı belgeler veya URL'ler kod öğeleri ve bağlantıları](../modeling/customize-code-maps-by-editing-the-dgml-files.md#AddReferences).

     Örnek:

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <DirectedGraph Title="DrivingTest" xmlns="http://schemas.microsoft.com/vs/2009/dgml">
       <Nodes>
          <Node Id="Driver" Label="Student" Category="Person" />
          <Node Id="Passenger" Label="Instructor" Category="Person" />
          <Node Id="Car" Label="Car" Category="Automobile" />
          <Node Id="Truck" Label="Truck" Category="Automobile" />
       </Nodes>
       <Links>
          <Link ... />
       </Links>
       <Categories>
          <Category Id="Person" Background="Orange" />
          <Category Id="Automobile" Background="Yellow"/>
       </Categories>
    </DirectedGraph>
    ```

-   `<Links></Links>`

     Bu öğe listesini içeren `<Link>` düğümler arasındaki bağlantıları belirleyen öğeleri. Daha fazla bilgi için bkz: `<Link/>` öğesi.

     Örnek:

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <DirectedGraph Title="DrivingTest" xmlns="http://schemas.microsoft.com/vs/2009/dgml">
       <Links>
          <Link ... />
       </Links>
    </DirectedGraph>
    ```

-   `<Link/>`

     Bu öğe, bir kaynak düğümünü hedef düğüme bağlayan tek bir bağlantıyı tanımlar. İçinde göründüğü `<Links></Links>` öğe listesi.

    > [!NOTE]
    > Bu öğe tanımsız bir düğüm başvuruyorsa, harita belge varsa belirtilen özniteliklere sahip bir düğümü otomatik olarak oluşturur.

     Bu öğenin öznitelikleri şunlardır:

     `Source` -Bağlantının kaynak düğümü

     `Target` -Bağlantının hedef düğüm

     Aşağıdaki liste, dahil edebileceğiniz isteğe bağlı özniteliklerin bazılarını açıklar:

     `Label` -Bağlantının görünen adı

     Stil öznitelikleri. Bkz: [DGML dosyalarını düzenleyerek kod haritalarını özelleştirme](../modeling/customize-code-maps-by-editing-the-dgml-files.md).

     `Category` -Bu özniteliği paylaşan öğeleri tanımlayan bir kategori adı. Daha fazla bilgi için bkz: `<Category/>` öğesi.

     `Property` -Aynı özellik değerine sahip öğeleri tanımlayan bir özellik adı. Daha fazla bilgi için bkz: `<Property/>` öğesi.

     Örnek:

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <DirectedGraph Title="DrivingTest" xmlns="http://schemas.microsoft.com/vs/2009/dgml">
       <Nodes>
          <Node Id="Driver" Label="Student" Category="Person" />
          <Node Id="Passenger" Label="Instructor" Category="Person" />
          <Node Id="Car" Label="Car" Category="Automobile" />
          <Node Id="Truck" Label="Truck" Category="Automobile" />
       </Nodes>
       <Links>
          <Category Id="Person" Background="Orange" />
          <Category Id="Automobile" Background="Yellow"/>
          <Link Source="Driver" Target="Car" Label="Passed" Stroke="Black" Background="Green" Category="PassedTest" />
          <Link Source="Driver" Target="Truck" Label="Failed" Stroke="Black" Background="Red" Category="PassedTest" />
       </Links>
    </DirectedGraph>
    ```

-   `<Categories></Categories>`

     Bu öğe listesini içeren `<Category/>` öğeleri. Daha fazla bilgi için bkz: `<Category/>` öğesi.

     Örnek:

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <DirectedGraph Title="DrivingTest" xmlns="http://schemas.microsoft.com/vs/2009/dgml">
       <Categories>
           <Category ... />
       </Categories>
    </DirectedGraph>
    ```

-   `<Category/>`

     Bu öğe tanımlayan bir `Category` bu özniteliği paylaşan öğeleri tanımlamak için kullanılan öznitelik. A `Category` özniteliği harita öğelerini düzenlemek, devralma yoluyla paylaşılan öznitelikler sağlamak veya ek meta verileri tanımlamak için kullanılabilir.

     Bu öğenin öznitelikleri şunlardır:

     `Id` -Benzersiz bir ad, kategori ve varsayılan değerini `Label` ayrı özniteliği `Label` özniteliği belirtildi.

     Aşağıdaki liste, dahil edebileceğiniz isteğe bağlı özniteliklerin bazılarını açıklar:

     `Label` -Kategori bir okuyucu kolay adı.

     `BasedOn` -Üst kategoriden `<Category/>` geçerli öğenin devralır.

     Bu öğe için örnekte `FailedTest` kategori devralır kendi `Stroke` özniteliğini `PassedTest` kategorisi. "Hiyerarşik kategoriler oluşturmak için" bölümüne bakın [Özelleştir kod eşlemeleri DGML dosyalarını düzenleyerek](../modeling/customize-code-maps-by-editing-the-dgml-files.md).

     Kategoriler de haritada görüntülendiğinde, düğümleri ve bağlantıları görünümünü denetleyen bazı temel şablon davranışı sağlar. Bkz: [DGML dosyalarını düzenleyerek kod haritalarını özelleştirme](../modeling/customize-code-maps-by-editing-the-dgml-files.md).

     Örnek:

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <DirectedGraph Title="DrivingTest" xmlns="http://schemas.microsoft.com/vs/2009/dgml">
       <Nodes>
          <Node Id="Driver" Label="Driver" Category="Person" />
          <Node Id="Car" Label="Car" Category="Automobile" />
          <Node Id="Truck" Label="Truck" Category="Automobile" />
          <Node Id="Passenger" Category="Person" />
       </Nodes>
       <Links>
          <Link Source="Driver" Target="Car" Label="Passed" Category="PassedTest" />
          <Link Source="Driver" Target="Truck" Label="Failed" Category="FailedTest" />
       </Links>
       <Categories>
          <Category Id="Person" Background="Orange" />
          <Category Id="Automobile" Background="Yellow"/>
          <Category Id="PassedTest" Label="Passed" Stroke="Black" Background="Green" />
          <Category Id="FailedTest" Label="Failed" BasedOn="PassedTest" Background="Red" />
       </Categories>
    </DirectedGraph>
    ```

-   `<Properties></Properties>`

     Bu öğe listesini içeren `<Property/>` öğeleri. Daha fazla bilgi için bkz: `<Property/>` öğesi.

     Örnek:

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <DirectedGraph Title="DrivingTest" xmlns="http://schemas.microsoft.com/vs/2009/dgml">
       <Properties>
           <Property ... />
       </Properties>
    </DirectedGraph>
    ```

-   `<Property/>`

     Bu öğe tanımlayan bir `Property` herhangi bir DGML öğe veya öznitelik kategorileri ve diğer özellikleri de dahil olmak üzere, bir değer atamak için kullanabileceğiniz özniteliği.

     Bu öğenin öznitelikleri şunlardır:

    -   `Id` -Benzersiz bir ad özelliği ve varsayılan değerini `Label` ayrı özniteliği `Label` özniteliği belirtildi.

    -   `DataType` -Özelliği tarafından depolanan veri türü

     Özellik görünmesini istiyorsanız **özellikleri** penceresi, kullanım `Label` özelliği Özelliğin görünen ad belirtin.

     Bkz: [kod öğeleri ve bağlantıları için kategoriler atayın](../modeling/customize-code-maps-by-editing-the-dgml-files.md#AssignCategories).

     Örnek:

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <DirectedGraph Title="DrivingTest" xmlns="http://schemas.microsoft.com/vs/2009/dgml">
       <Nodes>
          <Node Id="Driver" Label="Driver" Category="Person" DrivingAge="18"/>
          <Node Id="Car" Label="Car" Category="Automobile" />
          <Node Id="Truck" Label="Truck" Category="Automobile" />
          <Node Id="Passenger" Category="Person" />
       </Nodes>
       <Links>
          <Link Source="Driver" Target="Car" Label="Passed" Category="PassedTest" />
          <Link Source="Driver" Target="Truck" Label="Failed" Category="FailedTest" />
       </Links>
       <Categories>
          <Category Id="Person" Background="Orange" />
          <Category Id="Automobile" Background="Yellow"/>
          <Category Id="PassedTest" Label="Passed" Stroke="Black" Background="Green" />
          <Category Id="FailedTest" Label="Failed" BasedOn="PassedTest" Background="Red" />
       </Categories>
       <Properties>
           <Property Id="DrivingAge" Label="Driving Age" DataType="System.Int32" />
       </Properties>
    </DirectedGraph>
    ```

###  <a name="AddAlias"></a> Sık kullanılan yolları için diğer adlar

Yaygın olarak kullanılan yolların takma adlarla değiştirilmesi .dgml dosyasının boyutunu azaltır ve dosyayı yüklemek veya kaydetmek için gereken süreyi kısaltır. Bir diğer adı oluşturmak için Ekle bir `<Paths></Paths>` .dgml dosyanın sonunda bölüm. Bu bölümde, ekleme bir `<Path/>` öğe yolu için bir diğer ad tanımlayın:

```xml
<Paths>
   <Path Id="MyPathAlias" Value="C:\...\..." />
</Paths>
```

Diğer .dgml dosyasındaki bir öğeden başvurmak için içine `Id` , \<yol / > öğesi dolar işareti ($) ve parantez (()):

```xml
<Nodes>
   <Node Id="MyNode" Reference="$(MyPathAlias)MyDocument.txt" />
</Nodes>
<Properties>
   <Property Id="Reference" Label="My Document" DataType="System.String" IsReference="True" />
</Properties>
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Çözümlerinizdeki bağımlılıkları eşleme](../modeling/map-dependencies-across-your-solutions.md)
- [Uygulamalarınızda hata ayıklamak için kod haritalarını kullanma](../modeling/use-code-maps-to-debug-your-applications.md)
- [Kod haritası çözümleyicilerini kullanarak olası sorunları bulma](../modeling/find-potential-problems-using-code-map-analyzers.md)