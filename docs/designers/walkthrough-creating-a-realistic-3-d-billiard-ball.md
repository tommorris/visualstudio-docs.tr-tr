---
title: 'İzlenecek yol: bir gerçekçi 3B bilardo Top oluşturma'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: af8eb0f3-bf6a-4d1c-ab47-dcd88ab04efa
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4ced3059b516c7285d525666a69d2c63a654a83a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-create-a-realistic-3d-billiard-ball"></a>İzlenecek yol: bir gerçekçi 3B bilardo Top oluşturma

Bu kılavuz, Visual Studio'da gölgelendirici Tasarımcısı ve görüntü Düzenleyicisi'ni kullanarak bir gerçekçi 3B bilardo Top oluşturmak gösterilmiştir. Bilardo Top 3B görünümünü uygun doku kaynaklarla birkaç gölgelendirici teknikleri birleştirerek elde edilir.

## <a name="prerequisites"></a>Önkoşullar

Aşağıdaki bileşenler ve bu kılavuzu tamamlamak için yetenekler gerekir:

-   Dokular Haziran 2010'da dahil DirectX doku aracı gibi bir küp harita atayarak bir araç DirectX SDK.

-   Görüntü Düzenleyicisi Visual Studio ile benzer.

-   Visual Studio'da gölgelendirici Tasarımcısı hakkında bilgi.

## <a name="create-the-basic-appearance-with-shape-and-texture"></a>Şekil ve doku ile temel görünümü oluşturma

Bilgisayar grafiklerinde çoğu basic görünümünü şekli ve renk öğelerdir. Bir bilgisayar benzetimi gerçek nesnenin şeklini temsil etmek için 3B bir model kullanılacak yaygındır. Renk ayrıntı doku eşlem kullanarak model yüzeyine sonra uygulanır.

Genellikle, kullanabileceğiniz 3B bir model oluşturmak için bir sanatçı başvurmanız gerekebilir, ancak bilardo Top ortak şekil (küre) olduğundan, gölgelendirici Tasarımcısı zaten yerleşik olarak uygun bir modeli vardır.

Küre gölgelendirici Tasarımcısı'nı varsayılan Önizleme şeklinde olur; farklı bir şekil, gölgelendirici önizlemek için kullanmakta olduğunuz, kürenin geri çevirin.

### <a name="to-preview-the-shader-by-using-a-sphere"></a>Bir küre kullanarak gölgelendirici önizlemek için

-   Gölgelendirici Tasarımcısı araç çubuğundaki seçin **küre önizlemede.**

 Sonraki adımda modele bir doku uygular gölgelendirici program oluşturacaksınız, ancak ilk kullanabileceğiniz bir doku oluşturmanız gerekir. Bu anlatımda Visual Studio bir parçası görüntü düzenleyicisini kullanarak dokuyu oluşturmak nasıl gösterilir ancak doku uygun bir biçimde kaydedebilirsiniz herhangi bir görüntü Düzenleyicisi kullanabilirsiniz.

 Olduğundan emin olun **özellikleri** penceresi ve **araç** görüntülenir.

### <a name="to-create-a-billiard-ball-texture-by-using-the-image-editor"></a>Görüntü Düzenleyicisi'ni kullanarak bilardo Top doku oluşturmak için

1.  Çalışmak üzere bir doku oluşturun. Başlarken bölümünde bir doku projenize ekleme hakkında daha fazla bilgi için bkz: [görüntü Düzenleyicisi](../designers/image-editor.md).

2.  Böylece eni gerekse boyu iki kez görüntü boyutunu ayarlayın; Bu bir doku bilardo Top küresel yüzeyine eşlendi şekilde nedeniyle gereklidir. İçinde görüntüyü yeniden boyutlandırmak için **özellikleri** penceresinde, yeni değerlerini belirtin **genişliği** ve **yükseklik** özellikleri. Örneğin, genişliği 512 ve 256 yükseklik olarak ayarlayın.

3.  Bir doku bir küre nasıl eşleştiğini göz önünde bulundurarak bilardo Top için bir doku çizin.

     Doku şuna benzer görünmelidir:

     ![Doku bilardo Top için](../designers/media/gfx_shader_demo_billiard_art_ball_texture.png "gfx_shader_demo_billiard_art_ball_texture")

4.  İsteğe bağlı olarak, bu doku depolama gereksinimlerini azaltmak isteyebilirsiniz. Bunu kendi yüksekliğini eşleşecek şekilde doku genişliğini azaltarak yapabilirsiniz. Bu dokuyu eni boyunca sıkıştırır ancak bilardo Top işlendiğinde doku küre eşlendi yöntemi nedeniyle, genişletilecek. Yeniden boyutlandırma sonra doku şuna benzer görünmelidir:

     ![Kare sıkıştırılmış bilardo doku](../designers/media/gfx_shader_demo_billiard_art_ball_texture_square.png "gfx_shader_demo_billiard_art_ball_texture_square")

 Artık bu doku modeline uygulanan gölgelendirici oluşturabilirsiniz.

### <a name="to-create-a-basic-texture-shader"></a>Temel doku gölgelendirici oluşturmak için

1.  Çalışmak için DGSL gölgelendirici oluşturun. Başlarken bölümünde DGSL gölgelendirici projenize ekleme hakkında daha fazla bilgi için bkz: [gölgelendirici Tasarımcısı](../designers/shader-designer.md).

     Varsayılan olarak, bir gölgelendirici grafiği şuna benzer:

     ![Varsayılan gölgelendirici grafik](../designers/media/gfx_shader_demo_billiard_step_0.png "gfx_shader_demo_billiard_step_0")

2.  Bir doku örnek değeri geçerli piksel uygulanmasını varsayılan gölgelendirici değiştirin. Gölgelendirici grafiği aşağıdaki gibi görünmelidir:

     ![Doku bir nesne için geçerli bir gölgelendirici grafik](../designers/media/gfx_shader_demo_billiard_step_1.png "gfx_shader_demo_billiard_step_1")

3.  Doku özelliklerini yapılandırarak önceki yordamda oluşturduğunuz doku uygulayın. Değerini ayarlamak **doku** özelliği **doku örnek** düğüme **Texture1**, doku dosyasını kullanarak Calls **Filename**özelliği **Texture1** aynı özellik penceresinde özellik grubu.

 Gölgelendirici dokuyu uygulama hakkında daha fazla bilgi için bkz: [nasıl yapılır: temel bir doku gölgelendirici oluşturma](../designers/how-to-create-a-basic-texture-shader.md).

 Bilardo Top şuna benzer görünmelidir:

 ![Doku bilardo Top, closeup](../designers/media/gfx_shader_demo_.png "gfx_shader_demo_")

## <a name="create-depth-with-the-lambert-lighting-model"></a>Derinlik Lambert aydınlatma modeliyle oluşturma

Şu ana kadar bir anlaşılacak bilardo Top oluşturduğunuzu düşünün. Ancak, düz ve sizi ilgilendirmeyen görünür — bir ikna edici çoğaltma ister bilardo Top çizgi resmini daha. Her piksel bilardo Top yüzeyinde ışık aynı miktarda alırsa gibi davranır simplistic gölgelendirici düz görünüm sonuçlarından.

 Gerçek Hayatta, hafif parlak doğrudan ışık kaynağının yüz ve açık kaynak oblique açılı olan yüzeyleri üzerinde parlaklığını görüntülenen yüzey üzerinde görüntülenir. Yüzey doğrudan ışık kaynağının yüzler, hafif Işınları içinde enerji arasında en küçük yüzey alanını dağıtılmış olmasıdır. Yüzey ışık kaynağından uzakta kapatır gibi enerji ile aynı miktarda giderek daha büyük bir yüzey alanını arasında dağıtılır. Işık kaynağından uzakta bakarken yüzeyini tamamen koyu bir görünüm elde edilen hiçbir açık enerji hiç alır. Yüzey üzerinde parlaklığını bu varyans bir nesnenin bir nesnenin şeklini gösteren yardımcı olacak önemli bir görsel İpucu olur; Bu olmadan, nesne düz görünür.

 Bilgisayar grafik *aydınlatma modelleri*— Basitleştirilmiş karmaşık, gerçek aydınlatma etkileşimleri yakın — gerçek aydınlatma görünümünü çoğaltmak için kullanılan. Lambert aydınlatma modeline diffusely yansıtılan ışık miktarını nesneyi yüzeyde önceki paragrafta açıklanan değişir. Daha fazla ikna edici bir 3B görünüm bilardo Top vermek için gölgelendirici Lambert aydınlatma modeli ekleyebilirsiniz.

### <a name="to-add-lambert-lighting-to-your-shader"></a>Lambert aydınlatma, gölgelendirici eklemek için

-   Doku örnek değer Lambert aydınlatma değeriyle modulate, gölgelendirici değiştirin. Gölgelendirici grafiği aşağıdaki gibi görünmelidir:

     ![Gölgelendirici grafik eklenen Lambert aydınlatma ile](../designers/media/gfx_shader_demo_billiard_step_2.png "gfx_shader_demo_billiard_step_2")

-   İsteğe bağlı olarak yapılandırarak aydınlatma nasıl davranacağını ayarlayabilirsiniz **MaterialDiffuse** gölgelendirici grafik özelliği. Gölgelendirici grafik özelliklerine erişmek için tasarım yüzeyine boş alanı seçip erişmek istediğiniz özellik bulun **özellikleri** penceresi.

 Gölgelendirici Lambert aydınlatma uygulama hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir temel Lambert gölgelendirici oluşturma](../designers/how-to-create-a-basic-lambert-shader.md).

 Uygulanan Lambert aydınlatma ile bilardo Top şuna benzer görünmelidir:

 ![Doku ve aydınlatılmış bilardo Top, closeup](../designers/media/gfx_shader_demo_billiard_ball_2.png "gfx_shader_demo_billiard_ball_2")

## <a name="enhance-the-basic-appearance-with-specular-highlights"></a>Temel görünümünü aynasal vurgular geliştirmek

Şekil ve etmeksizin boyut duygusu Lambert aydınlatma modelidir yalnızca doku gölgelendirici içinde. Ancak, bilardo Top hala bir biraz görünüm donuk içeriyor.

 Gerçek bilardo Top genellikle üzerinde döner açık bir kısmı yansıtan parlak bitiş vardır. Bu bazıları açık bir yüzey yansıtıcı özelliklerini benzetimini aynasal vurgular sonuçlarında yansıtılır. Bitiş özelliklerini bağlı olarak önemli yerelleştirilmiş veya geniş, güçlü veya Zarif olabilir. Bir açık kaynak, surface ve kamera konumunu yönünü arasındaki ilişkiyi kullanarak bu aynasal yansımaları Modellenen — yüzey yönünü ışık kaynağının doğrudan yansıtan diğer bir deyişle, Vurgu en yoğun olduğunda Kamera ve yansıma daha az yoğun olduğunda daha az doğrudan numarasıdır.

 Önceki paragrafta açıklanan aynasal vurgular içerecek şekilde Lambert aydınlatma model üzerinde Phong aydınlatma modeli oluşturur. Daha ilginç bir görünüm elde benzetimli bitiş bilardo Top vermek için gölgelendirici Phong aydınlatma modeli ekleyebilirsiniz.

### <a name="to-add-specular-highlights-to-your-shader"></a>Aynasal vurgular, gölgelendirici eklemek için

1.  Ek karıştırma kullanarak aynasal katkı eklemek için gölgelendirici değiştirin. Gölgelendirici grafiği aşağıdaki gibi görünmelidir:

     ![Gölgelendirici grafik eklenen aynasal aydınlatma ile](../designers/media/gfx_shader_demo_billiard_step_3.png "gfx_shader_demo_billiard_step_3")

2.  İsteğe bağlı olarak, aynasal özellikleri yapılandırarak aynasal vurgu davranış biçimini de ayarlayabilirsiniz (**MaterialSpecular** ve **MaterialSpecularPower**) gölgelendirici grafik. Boş bir alana tasarım yüzeyi ve ardından gölgelendirici grafik erişim özelliklerine seçin **özellikleri** penceresinde erişmek istediğiniz özelliği bulunamadı.

 İçinde gölgelendirici aynasal vurgular uygulama hakkında daha fazla bilgi için bkz: [nasıl yapılır: temel Phong gölgelendirici oluşturma](../designers/how-to-create-a-basic-phong-shader.md).

 Aynasal uygulanan vurgulama, bilardo Top şuna benzer görünmelidir:

 ![Closeup aynasal ile bilardo Top, eklenen](../designers/media/gfx_shader_demo_billiard_ball_3.png "gfx_shader_demo_billiard_ball_3")

## <a name="create-a-sense-of-space-by-reflecting-the-environment"></a>Ortam yansıtma tarafından bir fikir alanı oluşturma

Uygulanan aynasal vurgular ile bilardo Top oldukça ikna edici arar. Sağ şekli, doğru boyama iş ve doğru bitiş var. Ancak, yoktur hala kendi ortamının bir parçası gibi daha fazla konum, bilardo Top yapacak bir daha fazla teknik.

 Gerçek bilardo Top yakından incelerseniz, parlak yüzeyini aynasal vurgular yalnızca sergilemesine değil ancak aynı zamanda faintly tüm dünyada görüntüsünü yansıtır görebilirsiniz. Doku olarak ortamı görüntüsünü kullanarak ve her piksel son rengi belirlemek için modelinin kendi doku ile birleştirerek bu yansıma benzetimini yapabilirsiniz. İstediğiniz bitiş türüne bağlı olarak, size daha birleştirebilir veya daha az yansıma doku gölgelendirici geri kalanı ile birlikte. Örneğin, bir yansıtma gibi yüksek oranda yansıtıcı yüzeyini benzetim gölgelendirici yalnızca yansıma doku ancak bilardo Top üzerinde bulunan bir yansıma yalnızca küçük bir kısmı birleştirebilirsiniz gibi daha hafif bir yansıma taklit eden bir gölgelendirici kullanabilirsiniz Gölgelendirici hesaplama geri kalanı ile birlikte doku'nın değeri.

 Elbette, yalnızca yansıtılan görüntüsünü modele modelinin eşlemi uyguladığınız aynı şekilde uygulayamazsınız. Kaldırdıysanız, yansıma kendisine yapışmış gibi dünya yansıma ile bilardo Top taşıyabilir. Bir yansıma herhangi bir yönde geldiğinden, herhangi bir açıda bir yansıma harita değer sağlamak için bir yol ve göre world yönelik yansıma eşlemini tutmak için bir yol gerekir. Bu gereksinimleri karşılamak için özel türde bir doku eşlemi kullanabilirsiniz — adlı bir *küp harita*— bir küp yanlarından oluşturmak için düzenlenmiş altı dokuları sağlar. Bu küpü içinde bir doku değeri bulmak için herhangi bir yönde gösterebilir. Her tarafında kübün dokuları ortamının görüntüleri içeriyorsa, küp doğru konumunu yüzeyinde örnekleyerek herhangi yansıma benzetimini yapabilirsiniz. Dünya hizalı küp tutarak, ortamın doğru bir yansımasını elde edersiniz. Küpün burada örneklenen belirlemek için yalnızca nesnenin yüzeyinin kapalı kamera vektör yansıma hesaplamak ve 3B doku koordinatları olarak kullanın. Küp maps raporları bu şekilde kullanmaktır olarak bilinen bir ortak teknik *ortam eşleme*.

 Ortam eşleme gerçek yansımaları verimli yaklaşık önceki paragrafta açıklanan sağlar. Daha fazla göründüğü bilardo Top yapan benzetimli bitiş Sahne topraklanmış bilardo Top vermek için gölgelendirici içine ortamı eşlenen yansımaları karıştırabilirsiniz.

 İlk adım, bir küp harita doku oluşturmaktır. Uygulamalar çok çeşitli küp harita içeriğini özellikle yansıma hafif olduğunda veya ekranında belirgin bir alan kaplar değil etkin, olmasını kusursuz olmak zorunda değildir. Örneğin, bu yansıma doğru olmadığını anlamına gelir ancak birçok oyun ortamı eşleme ve yalnızca kullanım bir yansıtıcı her nesnenin en yakın önceden hesaplanan küp eşlemeleri kullanın. Bile kaba yaklaşık genellikle bir ikna edici efekti yetecek kadar iyi olur.

### <a name="to-create-textures-for-an-environment-map-by-using-the-image-editor"></a>Görüntü Düzenleyicisi'ni kullanarak bir ortam eşlemesi için doku oluşturmak için

1.  Çalışmak üzere bir doku oluşturun. Başlarken bölümünde bir doku projenize ekleme hakkında daha fazla bilgi için bkz: [görüntü Düzenleyicisi](../designers/image-editor.md).

2.  Görüntü boyutu eni gerekse boyu eşit olduğundan ve iki boyutu gücünü şekilde ayarlayın; Bu bir küp harita dizinlenir şekilde nedeniyle gereklidir. İçinde görüntüyü yeniden boyutlandırmak için **özellikleri** penceresinde, yeni değerlerini belirtin **genişliği** ve **yükseklik** özellikleri. Örneğin, değerini **genişliği** ve **yükseklik** 256 özellikleri.

3.  Düz renk doku doldurmak için kullanın. Bu doku bilardo tablo yüzeye karşılık gelen küp harita alt olacaktır. Kullandığınız renk sonraki doku için göz önünde bulundurun.

4.  İlk olarak aynı boyutta ikinci bir doku oluşturun. Bu doku yüzeyini ve bilardo tablo yanlarından ve bilardo tablo etrafına karşılık gelen küp harita dört tarafına yinelenir. Alt doku olduğu gibi aynı renk kullanarak bu doku bilardo tablo yüzeyinin çizmek emin olun. Doku şuna benzer görünmelidir:

     ![Cubemap yanlarından doku](../designers/media/gfx_shader_demo_billiard_art_env_texture_side.png "gfx_shader_demo_billiard_art_env_texture_side")

     Bir yansıma harita etkili olması için fotoğraf kalitesinde olması gerekmez unutmayın; Örneğin, bu makaledeki görüntüleri oluşturmak için kullanılan küp eşlemesi altı yerine yalnızca dört cep içerir.

5.  Başkalarının aynı boyutta üçüncü bir doku oluşturun. Bu doku bilardo tablonun üstündeki tavan karşılık gelen küp haritanın üst olacaktır. Yansıma bu kısmı daha ilginç hale getirmek için gölgelendirici önceki yordamda eklediğiniz aynasal vurgular pekiştirmek için genel bir açık çizebilirsiniz. Doku şuna benzer görünmelidir:

     ![Doku cubemap üst](../designers/media/gfx_shader_demo_billiard_art_env_texture_top2.png "gfx_shader_demo_billiard_art_env_texture_top2")

 Küp harita yanlarından için tek tek doku oluşturduğunuza göre bunları tek .dds dokuyu depolanan bir küp harita halinde birleştirmek için bir aracı kullanabilirsiniz. Küp harita .dds doku biçiminde kaydedebilirsiniz sürece küp harita oluşturmak istediğiniz herhangi bir programı kullanabilirsiniz. Bu anlatımda Haziran 2010 bir parçası olan DirectX doku aracı kullanarak dokuyu oluşturmak nasıl gösterilir DirectX SDK.

### <a name="to-assemble-a-cube-map-by-using-the-directx-texture-tool"></a>DirectX doku Aracı'nı kullanarak bir küp harita derlemek için

1.  DirectX doku aracında ana menüdeki seçin **dosya**, **yeni doku**. **Yeni doku** iletişim kutusu görüntülenir.

2.  İçinde **doku türü** grubunda, seçin **Cubemap doku**.

3.  İçinde **boyutları** grubunda, doğru değerini girmeniz **genişliği** ve **yükseklik**ve ardından **Tamam**. Yeni bir doku belge görünür. Varsayılan olarak, karşılık gelen ilk doku belgede gösterilen doku **pozitif X** küp yüz.

4.  Doku küpün küp yüz üzerine tarafı için oluşturduğunuz doku yükleyin. Ana menüde seçin **dosya**, **açık üzerine bu Cubemap yüz**tarafındaki küp için oluşturulan doku seçin ve ardından **açık**.

5.  Yineleme 4. adım için **negatif X**, **pozitif Z**, ve **negatif Z** küp yüzeyleri. Bunu yapmak için yüklemek istediğiniz yüz görüntülemeniz gerekir. Ana menüde farklı küp harita yüz görüntülemek için seçin **Görünüm**, **küp harita yüz**ve ardından görüntülemek istediğiniz biçimi seçin.

6.  İçin **pozitif Y** küp yüz, doku küp üst için oluşturduğunuz doku yükleyin.

7.  İçin **negatif Y** küp yüz, doku küp alt için oluşturduğunuz doku yükleyin.

8.  Doku kaydedin.

 Bu gibi küp harita düzenini hayal edebildiğiniz:

 ![Ortam küp harita yerleşimini](../designers/media/gfx_shader_demo_billiard_art_env_texture_top.png "gfx_shader_demo_billiard_art_env_texture_top")

 Üst görüntü artı (+ Y) Y küp yüz durumundadır; soldan sağa, Orta olduğu -X + Z + X ve -Z, yüzler küp; alt kısmında -Y küp yüz vardır.

 Şimdi küp harita örnek gölgelendirici rest blend gölgelendirici değiştirebilirsiniz.

### <a name="to-add-environment-mapping-to-your-shader"></a>Ortam eşlemesi, gölgelendirici eklemek için

1.  Ek karıştırma kullanarak ortam eşleme katkı eklemek için gölgelendirici değiştirin. Gölgelendirici grafiği aşağıdaki gibi görünmelidir:

     ![Her iki tür yansıtıcı gölgelendirici düğümlerinin closeup](../designers/media/gfx_shader_demo_billiard_step_4b.png "gfx_shader_demo_billiard_step_4b")

     Kullanabileceğiniz Not bir **Çarp ekleme** gölgelendirici grafik basitleştirmek için düğüm.

     Daha ayrıntılı bir görünüm ortamı eşleme uygulamak gölgelendirici düğümlerin şöyledir:

     ![Eklenen ortamı eşleme ile gölgelendirici grafik](../designers/media/gfx_shader_demo_billiard_step_4a.png "gfx_shader_demo_billiard_step_4a")

2.  Küp harita doku özelliklerini yapılandırarak önceki yordamda oluşturduğunuz doku uygulayın. Değerini ayarlamak **doku** özelliği **Cubemap örnek** düğüme **Texture2**, doku dosyasını kullanarak Calls **Filename**özelliği **Texture2** özellik grubu.

3.  İsteğe bağlı olarak yapılandırarak bilardo Top yansımasını göre ayarlayabilirsiniz **çıkış** özelliği **sabit** düğümü. Düğüm erişim özelliklerine seçin ve ardından **özellikleri** penceresinde erişmek istediğiniz özelliği bulunamadı.

 Uygulanan ortamı eşlemesi ile bilardo Top şuna benzer görünmelidir:

 ![Ortamının closeup eşlenen bilardo top](../designers/media/gfx_shader_demo_billiard_ball_4.png "gfx_shader_demo_billiard_ball_4")

 Bu son görüntüde nasıl eklediğiniz etkilerini verici bilardo Top oluşturmak için araya gelmesi dikkat edin. Şekli, doku ve Aydınlatma 3B bir nesneyi temel görünümünü oluşturmak ve aynasal vurgular ve yansımalarını bilardo Top daha ilginç hale ve onun ortamının bir parçası gibi bakın.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl Yapılır: Gölgelendiriciyi Dışarı Aktarma](../designers/how-to-export-a-shader.md)
- [Nasıl yapılır: bir gölgelendirici 3B bir modeli için geçerlidir](../designers/how-to-apply-a-shader-to-a-3-d-model.md)
- [Gölgelendirici Tasarımcısı](../designers/shader-designer.md)
- [Görüntü Düzenleyicisi](../designers/image-editor.md)
- [Gölgelendirici Tasarımcısı Düğümleri](../designers/shader-designer-nodes.md)