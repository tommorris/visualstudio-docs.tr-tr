---
title: Program kodunda katman modellerini gezinme ve güncelleştirme
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- layer models, navigating in program code
- layer models, updating in program code
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 57ba3e2b2df938a41129fdf2d05bfa02690d2cce
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="navigate-and-update-layer-models-in-program-code"></a>Program kodunda katman modellerini gezinme ve güncelleştirme

Bu makalede öğeleri ve gezinme ve program kodunu kullanarak güncelleştirme katman modellerini ilişkilerde açıklanmaktadır. Kullanıcının bakış açısı bağımlılık diyagramlarından hakkında daha fazla bilgi için bkz: [bağımlılık diyagramları: başvuru](../modeling/layer-diagrams-reference.md) ve [bağımlılık diyagramları: yönergeler](../modeling/layer-diagrams-guidelines.md).

<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer> Bu konuda açıklanan cephesi daha genel üzerinde modeldir <xref:Microsoft.VisualStudio.GraphModel> modeli. Yazıyorsanız bir [menü komutu veya hareketi uzantısı](../modeling/add-commands-and-gestures-to-layer-diagrams.md), kullanın `Layer` modeli. Yazıyorsanız bir [katman doğrulama uzantısı](../modeling/add-custom-architecture-validation-to-layer-diagrams.md), kullanmayı daha kolay `GraphModel`.

## <a name="transactions"></a>İşlemler

Bir modeli güncelleştirme, değişiklikleri kapsayan göz önünde bir `ILinkedUndoTransaction`, değişikliklerinizi tek bir hareket halinde gruplandırır. Değişiklikleri başarısız olursa, tüm işlem geri alındı. Kullanıcı bir değişikliği geri alır, tüm değişiklikler birlikte geri alınır.

```
using (ILinkedUndoTransaction t =
        LinkedUndoContext.BeginTransaction("a name"))
{
    // Make changes here ....
    t.Commit(); // Don't forget this!
}
```

## <a name="containment"></a>Kapsama

![ILayer ve ILayerModel her ikisi de ILayers içerebilir.](../modeling/media/layerapi_containment.png)

Katmanlar (<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayer>) ve katman modeli (<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerModel>) açıklamaları ve Katmanlar içerebilir.

Bir katman (`ILayer`) bir katman modeli bulunabilir (`ILayerModel`) ya da onu içinde başka bir iç içe konabilir `ILayer`.

Açıklama veya bir katman oluşturmak için uygun bir kapsayıcı üzerinde oluşturma yöntemlerini kullanın.

## <a name="dependency-links"></a>Bağımlılık bağlantıları

Bir bağımlılık bağlantı bir nesne temsil edilir. Herhangi bir yönde gittiğinizde:

![Bir ILayerDependencyLink iki ILayers bağlanır.](../modeling/media/layerapi_dependency.png)

Bir bağımlılık bağlantı oluşturmak için arama `source.CreateDependencyLink(target)`.

## <a name="comments"></a>Açıklamalar

Açıklamalar Katmanlar veya katman modeli içinde bulunan ve aynı zamanda herhangi bir katman öğeye bağlanabilir:

![Herhangi bir katman öğeye açıklamalar eklenebilir.](../modeling/media/layerapi_comments.png)

Bir yorum öğelerin hiçbiri de dahil olmak üzere, herhangi bir sayıda bağlanabilir.

Bir katman öğesine bağlı yorumlar almak için kullanın:

```csharp
ILayerModel model = diagram.GetLayerModel();
IEnumerable<ILayerComment> comments =
   model.Comments.Where(comment =>
      comment.Links.Any(link => link.Target == layerElement));
```

> [!CAUTION]
> `Comments` Özelliği bir `ILayer` içinde bulunan açıklamaları alır `ILayer`. Ona bağlı yorumlar almaz.

Açıklama çağırarak oluşturmak `CreateComment()` uygun bir kapsayıcı üzerinde.

Bir bağlantıyı kullanarak oluşturursunuz `CreateLink()` açıklama üzerinde.

## <a name="layer-elements"></a>Katman öğeleri

Bir modeldeki bulunan öğe tüm türleri katman öğeler şunlardır:

![bağımlılık diyagramı içeriği ILayerElements olduğundan.](../modeling/media/layerapi_layerelements.png)

## <a name="properties"></a>Özellikler

Her `ILayerElement` adlı bir dize sözlük `Properties`. Herhangi bir katman öğeye rasgele bilgi eklemek için bu sözlük kullanabilirsiniz.

## <a name="artifact-references"></a>Yapı başvuruları

Bir yapı başvurusu (<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerArtifactReference>) bir katman ve dosya, sınıf veya klasör gibi bir proje öğesi arasındaki bağlantıyı temsil eder. Bunlar bir katman oluşturduğunuzda ya da Çözüm Gezgini'nde, sınıf görünümü ya da nesne tarayıcısı bir bağımlılık diyagramına öğeleri sürükleyerek ekleyin kullanıcı yapıtları oluşturur. Yapı başvuruları herhangi bir sayıda katmana bağlanabilir.

Katman Gezgini her satırda bir yapı başvurusu görüntüler. Daha fazla bilgi için bkz: [kodunuzdan bağımlılık diyagramları oluşturma](../modeling/create-layer-diagrams-from-your-code.md).

Asıl türleri ve yöntemleri yapı başvuruları ile ilgili aşağıdaki gibidir:

<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerArtifactReference>. Sınıfı, yürütülebilir dosya veya derleme gibi ne tür bir yapı başvuruluyor kategorileri özelliği gösterir. Kategoriler özellik tanımlayıcısı hedef yapı nasıl tanımlar belirler.

<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ArtifactReferenceExtensions.CreateArtifactReferenceAsync%2A> bir yapı başvurusundan oluşturur bir <xref:EnvDTE.Project> veya <xref:EnvDTE.ProjectItem>. Bu zaman uyumsuz bir işlemdir. Bu nedenle, genellikle oluşturma tamamlandıktan sonra çağrılan bir geri çağırma sağlar.

Kullanım örneği diyagramları yapılara katman yapı başvuruları farklıdır.

## <a name="shapes-and-diagrams"></a>Şekiller ve diyagramları

Her bir öğesinde bir katman modeli temsil etmek için kullanılan iki nesneleri: bir <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerElement>ve bir <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation.IShape>. `IShape` Konumu ve boyutu diyagramda şeklin temsil eder. Katman modelleri, her `ILayerElement` varsa `IShape`ve her `IShape` bir bağımlılığı diyagramı varsa `ILayerElement`. `IShape` UML modelleri için de kullanılır. Bu nedenle, her `IShape` bir katman öğeye sahip.

Aynı şekilde <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerModel> birinde görüntülenir <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation.IDiagram>.

Bir özel komut veya hareket işleyicisi kodda geçerli Diyagram ve şekillerden geçerli seçimi alabilirsiniz `DiagramContext` içeri aktarın:

```
public class ... {
[Import]
    public IDiagramContext DiagramContext { get; set; }
...
public void ... (...)
{ IDiagram diagram = this.DiagramContext.CurrentDiagram;
  ILayerModel model = diagram.GetLayerModel();
  if (model != null)
  { foreach (ILayer layer in model.Layers) { ... }}
  foreach (IShape selected in diagram.SelectedShapes)
  { ILayerElement element = selected.GetLayerElement();
    if (element != null) ... }}
```

![Her ILayerElement IShape tarafından sunulur.](../modeling/media/layerapi_shapes.png)

<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation.IShape> ve <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation.IDiagram> UML modellerini görüntülemek için de kullanılır.

## <a name="see-also"></a>Ayrıca Bkz.

- [Bağımlılık diyagramlarına komut ve hareket ekleme](../modeling/add-commands-and-gestures-to-layer-diagrams.md)
- [Bağımlılık diyagramlarına özel mimari doğrulaması ekleme](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)
- [Bağımlılık diyagramlarına özel özellikler ekleme](../modeling/add-custom-properties-to-layer-diagrams.md)
- [Bağımlılık Diyagramları: Başvuru](../modeling/layer-diagrams-reference.md)
- [Bağımlılık Diyagramları: Yönergeler](../modeling/layer-diagrams-guidelines.md)
