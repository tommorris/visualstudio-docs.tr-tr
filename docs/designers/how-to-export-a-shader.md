---
title: 'Nasıl Yapılır: Gölgelendiriciyi Dışarı Aktarma'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 0bd48bf4-9792-4456-a545-e462a2be668d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 632cd61d3844dc6f405090081ef76e5a2d6967b7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-export-a-shader"></a>Nasıl Yapılır: Gölgelendiriciyi Dışarı Aktarma
Bu belgede gölgelendirici tasarımcının uygulamanızı kullanabilmeleri yönlendirilmiş grafik gölgelendirici dili (DGSL) gölgelendirici dışarı aktarmak için nasıl kullanılacağı gösterilmektedir.

 Bu belgede, bu etkinliği gösterir:

-   Gölgelendirici dışarı aktarma

## <a name="exporting-a-shader"></a>Gölgelendirici dışarı aktarma
 Gölgelendirici Tasarımcısı'nı kullanarak ve uygulamanızda kullanabilmeniz için önce bir gölgelendirici oluşturduktan sonra API grafiklerinizi özelliğini algılayan bir biçimde dışarı gerekir. Farklı gereksinimlerini karşılamak için farklı şekillerde gölgelendirici dışarı aktarabilirsiniz.

#### <a name="to-export-a-shader"></a>Gölgelendirici dışarı aktarmak için

1.  İçinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], açık bir **Visual gölgelendirici grafik (.dgsl)** dosyası.

     Yoksa bir **Visual gölgelendirici grafik (.dgsl)** açın, açıklandığı gibi oluşturmak için dosya [nasıl yapılır: temel bir renk gölgelendirici oluşturmak](../designers/how-to-create-a-basic-color-shader.md).

2.  Üzerinde **gölgelendirici Tasarımcısı** araç seçin **Gelişmiş**, **verme**, **verme olarak**. **Verme gölgelendirici** iletişim kutusu görüntülenir.

3.  İçinde **farklı türde Kaydet** aşağı açılan listesinde, dışa aktarmak istediğiniz biçimi seçin.

     Seçebileceğiniz biçimler şunlardır:

     **HLSL piksel gölgelendirici (\*.hlsl)** gölgelendirici yüksek düzey gölgelendirici dili (HLSL) kaynak kodu olarak dışa aktarır. Bu seçenek, bir uygulamada bile dağıtıldıktan sonra gölgelendirici daha sonra değiştirmek mümkün kılar. Bu, hata ayıklama ve son kullanıcı sorunları göre kod düzeltme eki daha kolay hale getirebilir, ancak aynı zamanda, gölgelendirici istenmeyen şekilde değiştirmek bir kullanıcı için kolaylaştırır — Örneğin, haksız avantajlı rekabetçi bir oyunda elde etmek için. Bu da gölgelendirici yükleme süresini artırabilir.

     **Derlenmiş piksel gölgelendirici (\*.cso)** gölgelendirici HLSL bayt dışa aktarır. Bu seçenek bir uygulamada bile dağıtıldıktan sonra gölgelendirici daha sonra değiştirmek yaptığı mümkündür. Bu, hata ayıklama ve son kullanıcı sorunları göre kod düzeltme eki kolaylaştırabilir, ancak gölgelendirici önceden derlenmiş olduğundan gölgelendirici uygulama tarafından yüklendiğinde, ek çalışma zamanı zahmetine değil. Yeterince deneyimli kullanıcılar hala istenmeyen şekilde gölgelendirici değiştirebilirsiniz ancak gölgelendirici derleme bu önemli ölçüde daha zor hale getirir.

     **C++ üstbilgi (\*.h)** gölgelendirici HLSL bayt içeren bir bayt dizisi tanımlayan C tarzı başlık olarak dışa aktarır. Bu seçenek hata ayıklamak ve düzeltme test etmek için uygulama yeniden derlenmesi için son kullanıcı sorunları göre kod düzeltme eki daha uzun süren yapabilirsiniz. Bu seçenek, imkansız olsa, bir uygulama dağıtıldıktan sonra gölgelendirici değiştirmek zorlaştırır olduğundan, ancak bu çoğu zorluk gölgelendirici istenmeyen şekilde değiştirmek için isteyen bir kullanıcıya gösterir.

4.  İçinde **dosya adı** birleşik giriş kutusu, dışarı aktarılan gölgelendirici için bir ad belirtin ve ardından **kaydetmek** düğmesi.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl Yapılır: Temel Renk Gölgelendiricisi Oluşturma](../designers/how-to-create-a-basic-color-shader.md)
- [Gölgelendirici Tasarımcısı](../designers/shader-designer.md)