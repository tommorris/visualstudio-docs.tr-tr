---
title: Metin ve görüntü alanları özelleştirme | Microsoft Docs
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
ms.openlocfilehash: f577669c685d6f42b73c80f947e8edad0c7b9088
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="customizing-text-and-image-fields"></a>Metin ve Görüntü Alanlarını Özelleştirme
Bir şekli bir metin oluşturma öğesi tanımladığınızda, TextField temsil edilir. Başlatma TextFields ve diğer ShapeFields örnekler için Dsl\GeneratedCode\Shapes.cs DSL çözümünüzde inceleyin.  
  
 Bir TextField bir etikete atanan alanı gibi bir şekil içindeki bir alanı yöneten bir nesnedir. Bir TextField örneği aynı sınıfın birçok şekiller arasında paylaşılır. TextField örneği her örneği için ayrı ayrı etiket metnini depolamaz: bunun yerine, `GetDisplayText(ShapeElement)` yöntemi şekil bir parametre olarak alır ve geçerli durumunu şekli ve model öğesi üzerinde bağımlı metin bakabilirsiniz.  
  
## <a name="how-the-appearance-of-a-text-field-is-determined"></a>Bir metin alanı görünümünü nasıl belirlenir  
 `DoPaint()` Yöntemi çağrıldığında görüntüler için alan ekranda. Ya da varsayılan ayarlarını geçersiz kılabilir `DoPaint(),` veya çağırır yöntemlerin bazıları geçersiz kılabilirsiniz. Varsayılan yöntemlerini aşağıdaki Basitleştirilmiş sürümünü varsayılan davranışı geçersiz kılmak nasıl tasarlandığını anlamanıza yardımcı olabilir:  
  
```  
// Simplified version:  
public override void DoPaint(DiagramPaintEventArgs e, ShapeElement parentShape)  
{   
  string text = GetDisplayText(shape);   
  StringFormat format = GetStringFormat(parentShape);  
  Brush brush = GetTextBrush(e.View, shape);  
  using (Font font = GetFont(shape))  
  {  
    e.Graphics.DrawString(text, font, brush, format);  
  }  
}  
// StringFormat determines whether the string is centered etc.  
// To customize statically for all instances of this shape field,   
// assign to DefaultStringFormat.  
// To customize dynamically or per shape, override this:    
public virtual StringFormat GetStringFormat(ShapeElement shape)  
{ return DefaultStringFormat; }  
  
// Override to customize the displayed string:  
public virtual string GetDisplayText(ShapeElement shape)  
{ return this.GetValue(shape).ToString(); }  
  
// Brush determines the text color.  
// To change the brush for every field, change the shape's styleset.   
// To customize to a brush in the style set, override GetTextBrushId.  
// To change the brush to non-standard color, override this.  
// Should take account of whether selected.   
public virtual Brush GetTextBrush(DiagramClientView view, ShapeElement shape)  
{ return shape.StyleSet.GetBrush(this.GetTextBrushId(view, shape)); }  
  
// Brush ID selects a brush from a StyleSet.  
// Either return a member of DiagramBrushes   
// or add your own brush to the shape or application's styleset.  
// Override this to change dynamically or per instance.  
// To change statically, just assign to default values.   
public virtual StyleSetResourceId GetTextBrushId(DiagramClientView view, ShapeElement shape)  
{ return IsSelected(view, shape) ? (view.Focused ? DefaultSelectedTextBrushId  
: DefaultInactiveSelectedTextBrushId ) : DefaultTextBrushId ;  
}  
  
// Font determines the shape and size of the text.  
// To change the font for every field, change the shape's styleset.   
// To customize to a font in the style set, override GetFontId.  
// To change the font to a non-standard font, override this.   
public virtual Font GetFont(ShapeElement shape)  
{ return shape.StyleSet.GetFont(GetFontId(shape)); }  
  
// Selects a font from a styleset.  
// Either return a member of DiagramFonts or   
// add your own font to the shape or application's styleset.  
// To change statically for all instances of this field,   
// assign to DefaultFontId.  
// To change per shape or dynamically, override this.   
public virtual StyleSetResourceId GetFontId(ShapeElement parentShape)  
{ return DefaultFontId; }  
  
```  
  
 Diğer birçok çiftlerini vardır `Get` yöntemleri ve `Default` özellikleri gibi `DefaultMultipleLine/GetMultipleLine()`. Şekil alanı tüm örnekleri için bu değeri değiştirmek için varsayılan özellik için bir değer atayabilirsiniz. Başka bir ya da şekli veya model öğesi durumu bağımlı bir şekli örnekten farklılık değer yapmak için geçersiz kılma `Get` yöntemi.  
  
## <a name="static-customizations"></a>Statik özelleştirmeleri  
 Bu şekil alanı her örneğini değiştirmek istiyorsanız, ilk önce olup olmadığını, özelliği DSL tanımı'nda ayarlayabilirsiniz bulun. Örneğin, yazı tipi boyutunu ve stil özellikleri penceresinde ayarlayabilirsiniz.  
  
 Aksi takdirde, daha sonra geçersiz `InitializeShapeFields` yöntemi shape sınıfı ve atama için uygun bir değer `Default...` metin alanı özelliği.  
  
> [!WARNING]
>  Geçersiz kılmak için `InitializeShapeFields()`, ayarlamanız gerekir **oluşturur çift türetilmiş** şekli sınıfının özelliği `true` DSL tanımında.  
  
 Bu örnekte, bir şekli kullanıcı açıklamaları için kullanılacak bir metin alanı yok. Standart bir yorum font kullanmak istiyoruz. Standart bir yazı tipi stili kümesinde olduğundan, biz varsayılan yazı tipi kimliği ayarlayabilirsiniz:  
  
```  
  
 partial class ExampleShape  
{   protected override void InitializeShapeFields(IList<ShapeField> shapeFields)  
    {  
      // Fields set up according to DSL Definition:  
      base.InitializeShapeFields(shapeFields);  
      // Find and update comment field:  
      TextField commentField = ShapeElement.FindShapeField(shapeFields, "CommentDecorator") as TextField;  
      // Use the standard font for comments:  
      commentField.DefaultFontId = DiagramFonts.CommentText;  
  
```  
  
## <a name="dynamic-customizations"></a>Dinamik özelleştirmeleri  
 Farklılık görünüm bir şekli veya model öğesi durumu bağımlı yapmak için kendi alt türetilen `TextField` ve bir veya daha fazla geçersiz kılma `Get...` yöntemleri. Ayrıca, şeklin InitializeShapeFields yöntemini geçersiz kılın ve örnek alanının kendi sınıfının bir örneğini değiştirmek gerekir.  
  
 Aşağıdaki örnek, bir metin alanı yazı tipi şeklin model öğesi Boolean etki alanı özelliği durumunu bağımlı hale getirir.  
  
 Bu örnek kodu çalıştırmak için en az bir dil şablonu kullanarak yeni bir DSL çözüm oluşturun. Boole etki alanı özellik ekleme `AlternateState` ExampleElement etki alanı sınıfı. Bir simge oluşturma öğesi ExampleShape sınıfına ekleyin ve bir bit eşlem dosyası görüntüsünü ayarlayın. Tıklatın **tüm şablonları dönüştürme**. Yeni bir kod dosyası DSL projeye ekleyin ve aşağıdaki kodu ekleyin.  
  
 Kodu test etmek için F5 tuşuna basın ve hata ayıklama çözümde bir örnek diyagramı açın. Varsayılan durum simgesinin görüntülenmesi gerekir. Şekli seçin ve Özellikler penceresinde değerini değiştirin **AlternateState** özelliği. Yazı tipini öğe adını değiştirmeniz gerekir.  
  
```  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
...  
  
  partial class ExampleShape  
  {  
    /// <summary>  
    /// Compose a list of the fields in this shape.  
    /// Called once for each shape class.  
    /// </summary>  
    protected override void InitializeShapeFields(IList<ShapeField> shapeFields)  
    {  
      // Fields set up according to DSL Definition:  
      base.InitializeShapeFields(shapeFields);  
      // Replace the text field for NameDecorator:  
      TextField oldField = ShapeElement.FindShapeField(shapeFields, "NameDecorator") as TextField;  
      shapeFields.Remove(oldField);  
      // Replace with my text field based on DSL Definition values:  
      MyTextField newField = new MyTextField(oldField);  
      shapeFields.Add(newField);  
    }  
  }  
  /// <summary>  
  /// Dynamic font depends on state of model element.  
  /// </summary>  
  public class MyTextField : TextField  
  {  
    public MyTextField(TextField prototype)  
      : base(prototype.Name)  
    {  
      DefaultText = prototype.DefaultText;  
      DefaultFocusable = prototype.DefaultFocusable;  
      DefaultAutoSize = prototype.DefaultAutoSize;  
      AnchoringBehavior.MinimumHeightInLines = prototype.AnchoringBehavior.MinimumHeightInLines;  
      AnchoringBehavior.MinimumWidthInCharacters = prototype.AnchoringBehavior.MinimumWidthInCharacters;  
      DefaultAccessibleState = prototype.DefaultAccessibleState;  
    }  
  
    public override System.Drawing.Font GetFont(ShapeElement parentShape)  
    {  
      // Access the Boolean domain property of the model element:  
      if ((parentShape.ModelElement as ExampleElement).AlternateState)  
        return new System.Drawing.Font("Callisto", 14.0f,  
               System.Drawing.FontStyle.Italic |   
               System.Drawing.FontStyle.Bold);  
      else  
        return base.GetFont(parentShape);  
    }  
  
  }  
  
```  
  
## <a name="style-sets"></a>Stilini ayarlar  
 Önceki örnekte, metin alanı kullanılabilir olan herhangi bir yazı tipi için nasıl değiştirebileceğiniz gösterir. Ancak, bir şekli veya uygulama ile ilişkilendirilmiş bir dizi stilleri değiştirmek için tercih edilen bir yöntem gerekir. Bunu yapmak için geçersiz kılma <xref:Microsoft.VisualStudio.Modeling.Diagrams.TextField.GetFontId%2A> veya GetTextBrushId().  
  
 Alternatif olarak, şekliniz stil kümesi geçersiz kılarak değiştirmeyi göz önünde bulundurun <xref:Microsoft.VisualStudio.Modeling.Diagrams.ShapeElement.InitializeResources%2A>. Bu yazı tipleri ve tüm şekil alanlarının Fırçalar değiştirmenin etkisi yoktur.  
  
## <a name="customizing-image-fields"></a>Görüntü alanlarını özelleştirme  
 Bir şekli bir resim oluşturma öğesi tanımladığınızda ve bir resim şekli tanımladığınızda, Şekil görüntülendiği alan bir ImageField tarafından yönetilir. Başlatma ImageFields ve diğer ShapeFields örnekler için Dsl\GeneratedCode\Shapes.cs DSL çözümünüzde inceleyin.  
  
 Bir ImageField oluşturma öğesi için atanan alanı gibi bir şekil içindeki bir alanı yöneten bir nesnedir. Bir ImageField örneği aynı shape sınıfı birçok şekiller arasında paylaşılır. ImageField örneği her şekli için ayrı bir görüntü depolamaz: bunun yerine, `GetDisplayImage(ShapeElement)` yöntemi şekil bir parametre olarak alır ve görüntünün şekil ve model öğesi geçerli durumuna bağımlı bakabilirsiniz.  
  
 Bir değişken görüntüsü gibi özel bir davranış istiyorsanız ImageField'dan türetilen kendi sınıfı oluşturabilirsiniz.  
  
#### <a name="to-create-a-subclass-of-imagefield"></a>ImageField öğesinin bir alt kümesi oluşturmak için  
  
1.  Ayarlama **oluşturur çift türetilmiş** DSL tanımınızı üst şekli sınıfın özelliği.  
  
2.  Geçersiz kılma `InitializeShapeFields` şekli sınıfınızın yöntemi.  
  
    -   DSL projeye yeni bir kod dosyası oluşturun ve Şekil sınıf için bir parçalı sınıf tanımı yazma. Yöntem tanımı geçersiz.  
  
3.  Kodu incelemek `InitializeShapeFields` DSL\GeneratedCode\Shapes.cs içinde.  
  
     Geçersiz kılma yönteminizi temel yöntemini çağırın ve kendi görüntü alanı sınıfının bir örneğini oluşturun. Bu normal görüntü alanını değiştirmek için kullanmak `shapeFields` listesi.  
  
## <a name="dynamic-icons"></a>Dinamik simgeler  
 Bu örnek bir simge Değiştir şeklin model öğesi durumu bağımlı hale getirir.  
  
> [!WARNING]
>  Bu örnek, bir dinamik görüntü oluşturma öğesi olun gösterilmiştir. Ancak yalnızca bir model değişkeni durumunu bağlı olarak bir veya iki görüntü arasında geçiş yapmak istiyorsanız, birden fazla görüntü dekoratörler oluşturmak, şekli aynı konumda bulun ve ardından belirli model değerlerine bağımlı görünürlük filtre ayarlamak daha basit değişkeni. Bu filtre ayarlamak için Şekil harita DSL tanımında seçin, DSL ayrıntıları penceresini açın ve dekoratörler sekmesini tıklatın.  
  
 Bu örnek kodu çalıştırmak için en az bir dil şablonu kullanarak yeni bir DSL çözüm oluşturun. Boole etki alanı özellik ekleme `AlternateState` ExampleElement etki alanı sınıfı. Bir simge oluşturma öğesi ExampleShape sınıfına ekleyin ve bir bit eşlem dosyası görüntüsünü ayarlayın. Tıklatın **tüm şablonları dönüştürme**. Yeni bir kod dosyası DSL projeye ekleyin ve aşağıdaki kodu ekleyin.  
  
 Kodu test etmek için F5 tuşuna basın ve hata ayıklama çözümde bir örnek diyagramı açın. Varsayılan durum simgesinin görüntülenmesi gerekir. Şekli seçin ve Özellikler penceresinde değerini değiştirin **AlternateState** özelliği. Simge sonra bu şeklin 90 derece aracılığıyla Döndürülmüş görüntülenmelidir.  
  
```csharp  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
...  
partial class ExampleShape  
{  
    /// <summary>  
    /// Compose a list of the fields in this shape.  
    /// Called once for each shape class.  
    /// </summary>  
    /// <param name="shapeFields"></param>  
    protected override void InitializeShapeFields(IList<ShapeField> shapeFields)  
    {  
      // Fields set up according to DSL Definition:  
      base.InitializeShapeFields(shapeFields);  
  
      // Replace the image field:  
      ShapeField oldField = ShapeElement.FindShapeField(shapeFields, "IconDecorator");  
      shapeFields.Remove(oldField);  
      // Must keep the same name:  
      MyImageField newField = new MyImageField(oldField.Name);  
      shapeFields.Add(newField);  
      newField.DefaultImage = (oldField as ImageField).DefaultImage.Clone() as System.Drawing.Image;  
    }  
  }  
  
  public class MyImageField : ImageField  
  {  
    public MyImageField(string tag) : base(tag) { }  
  
    /// <summary>  
    /// Get the image for this field in the given shape.  
    /// </summary>  
    public override System.Drawing.Image GetDisplayImage(ShapeElement parentShape)  
    {  
      ExampleElement element = parentShape.ModelElement as ExampleElement;  
      if (element.AlternateState == true)  
        return AlternateImage;  
      else  
        return base.GetDisplayImage(parentShape);  
    }  
  
    private System.Drawing.Image alternateImage;  
    public System.Drawing.Image AlternateImage  
    {  
      get  
      {  
        if (alternateImage == null)  
        {  
          // Alternate image is a copy of the default, rotated by 90 degrees:  
          alternateImage = this.DefaultImage.Clone() as System.Drawing.Image;  
          alternateImage.RotateFlip(System.Drawing.RotateFlipType.Rotate90FlipNone);  
        }  
        return alternateImage;  
      }  
    }  
  }  
}  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Şekiller ve bağlayıcılar tanımlama](../modeling/defining-shapes-and-connectors.md)   
 [Diyagramdaki bir arka plan resmi ayarlama](../modeling/setting-a-background-image-on-a-diagram.md)   
 [Gezinme ve bir modeli Program kodunda güncelleştirme](../modeling/navigating-and-updating-a-model-in-program-code.md)   
 [Etki Alanına Özgü Dili Özelleştirmek için Kod Yazma](../modeling/writing-code-to-customise-a-domain-specific-language.md)