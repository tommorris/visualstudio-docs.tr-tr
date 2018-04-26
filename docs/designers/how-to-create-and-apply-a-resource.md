---
title: Oluşturma ve kaynak Uygula
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
f1_keywords:
- VS.XamlDesigner.CreateResource
- VS.XamlDesigner.EditResource
ms.assetid: 3ff4006d-659d-4073-9a41-06ff85e6cfdf
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a1a162c66f4a014d50da7ad7bd3cd5da9edd6e43
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-and-apply-a-resource"></a>Oluşturma ve kaynak Uygula
Yeniden kullanılabilir varlıklar kaynakları adlı stilleri ve şablonları öğelerin XAML Tasarımcısı'nda depolanır. Stilleri öğesi özelliklerini ayarlamak ve çoklu öğeler arasında tutarlı bir görünüm için bu ayarları yeniden etkinleştirin. A [ControlTemplate](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.controltemplate.aspx) denetiminin görünümünü tanımlar ve ayrıca bir kaynak olarak uygulanabilir. Daha fazla bilgi için bkz: [hızlı başlangıç: stil denetimleri](http://go.microsoft.com/fwlink/?LinkID=248239) ve [hızlı başlangıç: denetim şablonları](http://go.microsoft.com/fwlink/?LinkID=247982).

 Varolan bir özelliğinden yeni bir kaynak oluşturduğunuzda [stili](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.style.aspx), veya `ControlTemplate`, **oluşturma kaynak** iletişim kutusu, uygulama düzeyinde belge düzeyinde kaynak tanımlamanızı sağlar veya öğe düzeyi. Bu düzeyler, kaynak burada kullanabileceğiniz belirler. Örneğin, kaynak öğe düzeyinde tanımlarsanız, kaynak üzerinde oluşturduğunuz öğesine uygulanabilir. Ayrıca, yeniden başka bir projede kullanabileceğiniz ayrı bir dosya olan bir kaynak sözlüğünde kaynağı saklamayı da seçebilirsiniz.

### <a name="to-create-a-new-resource"></a>Yeni bir kaynak oluşturmak için

1.  XAML Tasarımcısı'nda açık bir XAML dosyası, içeren bir öğe oluşturun veya Belge Anahattı penceresi içinde bir öğe seçin.

2.  Özellikleri penceresinde bir özellik değeri sağındaki kutu simgesi olarak görünür, özellik işaretçisi seçin ve ardından **yeni kaynağına dönüştürme**. Beyaz kutu simgesi varsayılan bir değer gösterir ve siyah kutu simgesi genellikle bir yerel kaynağı uygulandığını gösterir

     Bir kaynak oluşturmak için uygun bir iletişim kutusu görüntülenir. Bir kaynak bir fırça oluşturduğunuzda bu iletişim kutusu görüntülenir:

     ![Kaynak Oluştur iletişim kutusu](../designers/media/xaml_create_resource.png "xaml_create_resource")

3.  İçinde **adı (anahtar)** kutusunda, bir anahtar adı girin. Bu kaynağa başvuran diğer öğeleri istediğinizde kullanabileceğiniz addır.

4.  Altında **tanımlayın**, tanımlanmamış kaynak istediğiniz belirten seçeneği belirleyin:

    -   Kaynak uygulamanızda herhangi bir belgeyi kullanılabilir hale getirmek için seçin **uygulama**.

    -   Kaynak yalnızca geçerli belgede kullanılabilir hale getirmek için tercih **bu belgeyi**.

    -   Kaynak kaynak oluşturulmuş veya alt öğeleri için yalnızca öğede kullanılabilir hale getirmek için seçin **bu belgeyi**, aşağı açılan listesinde seçin *öğesi*: *adı* .

    -   Kaynak başka projelerde yeniden kullanılabilir bir kaynak sözlüğü dosya tanımlamak için tıklatın **kaynak sözlüğü**ve var olan bir kaynak sözlüğü dosya gibi seçin **StandardStyles.xaml**, aşağı açılan listesinde.

5.  Seçin **Tamam** kaynak oluşturmak ve kendisinden oluşturduğunuz bu öğeye uygulamak için düğmesi.

### <a name="to-apply-a-resource-to-an-element-or-property"></a>Bir kaynak bir öğe veya özellikte uygulamak için

1.  Belge Anahattı penceresi bir kaynağa uygulanmasını istediğiniz öğeyi seçin.

2.  Aşağıdakilerden birini yapın:

    -   Bir kaynak özelliği için geçerlidir. Özellikleri penceresinde, özellik değeri yanındaki özelliği işaretçisi seçin, seçin **yerel kaynak** veya **sistem kaynağı**ve ardından görüntülenen listesinden kullanılabilir bir kaynak seçin.

         Görmeyi beklediğiniz bir kaynak görmüyorsanız, kaynak türünü özelliğinin türü ile eşleşmediği için olabilir.

    -   Stil veya denetim şablonu kaynak denetimi uygulayın. Açık bir Belge Anahattı penceresi denetiminde bağlam menüsünü seçin **Şablonu Düzenle** veya **Düzenle ek şablonlar**, seçin **geçerli kaynak**ve ardından seçin Görüntülenen listede denetim şablonu adı.

        > [!NOTE]
        >  **Şablon düzenleme** denetim şablonları uygulamak için kullanılır. **Ek şablonlar Düzenle** diğer şablon türlerini uygulamak için kullanılır.

     Uyumlu her yerde kaynaklara uygulanabilir. Örneğin, bir fırça kaynak için uygulanabilir **ön plan** özelliği bir <xref:Windows.UI.Xaml.Controls.TextBox> denetim.

### <a name="to-edit-a-resource"></a>Bir kaynak düzenlemek için

1.  Çalışma yüzeyi veya Belge Anahattı penceresi bir öğe seçin.

2.  Özellikler penceresinde varsayılan veya yerel özellik işaretçisi özelliği sağındaki seçin ve ardından **Düzenle kaynak** açmak için **Düzenle kaynak** iletişim kutusu.

3.  Kaynak seçeneklerini değiştirin.

## <a name="see-also"></a>Ayrıca bkz.

- [XAML Tasarımcısı kullanarak bir kullanıcı Arabirimi oluşturma](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md)