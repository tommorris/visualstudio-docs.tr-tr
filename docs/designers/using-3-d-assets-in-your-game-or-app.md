---
title: Oyun veya uygulama 3B varlıkları kullanma
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: conceptual
f1_keywords:
- VC.Project.ImageContentTask.ContentOutput
- VC.Project.MeshContentTask.ContentOutput
- VC.Project.ImageContentTask.GeneratePremultipliedAlpha
- VC.Project.ImageContentTask.Compress
- VC.Project.ShaderGraphContentTask.ContentOutput
- VC.Project.ImageContentTask.GenerateMips
ms.assetid: ea587909-e434-46a8-abf8-9b3e95a58b4f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cfd757a88ebfddb9f86eb233ba407fd7eb9b27e9
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="use-3d-assets-in-your-game-or-app"></a>Oyun veya uygulama 3B varlıkları kullanın

Bu makalede, Visual Studio 3B varlıkları işlemek ve derlemeleriniz içinde eklemek için nasıl kullanabileceğinizi açıklar.

3B varlıklar oluşturmak için Visual Studio Araçları kullandıktan sonra sonraki adım bunları uygulamanızda kullanmaktır. Ancak varlıklarınızı kullanabilmek için önce DirectX anlayabileceği bir biçimine dönüştürülmesi gerekir. Varlıklarınızı dönüştürme yardımcı olmak için Visual Studio derleme özelleştirmeleri oluşturmak üzere varlık her türdeki sağlar. Varlıklar, yapı, tüm yapmanız gereken eklemektir projenizi derleme özelleştirmeleri, varlıkları projenize ekleyin ve varlıkları doğru yapı özelleştirme kullanmak için yapılandırmak için yapılandırın. Bundan sonra uygulamanıza varlıklar yükleyin ve bunları oluşturarak ve diğer bir DirectX uygulamada gibi DirectX kaynakları doldurma kullanın.

## <a name="configure-your-project"></a>Projenizi yapılandırın

3B varlıklarınızı yapınızın bir parçası olarak dağıtabilmeniz için önce Visual Studio, dağıtmak istediğiniz varlıklar türleri hakkında bilmesi gerekir. Visual Studio birçok ortak dosya türleri hakkında zaten bilir, ancak yalnızca belirli türdeki uygulama 3B varlıklar kullandığından, Visual Studio Proje bu tür dosyaları oluşturacaksınız varsayın değil. Visual Studio kullanarak uygulamanızı varlıklar bu tür kullandığını anlayabilirsiniz *özelleştirmeleri yapı*— Visual Studio farklı dosya türleri kullanışlı şekilde işlemek nasıl anlatın dosyaları — her varlık türü için sağlanan. Bu özelleştirmeler bir proje başına temelinde uygulandığından, yapmanız gereken tek şey uygun özelleştirmeleri projenize ekleyin.

### <a name="to-add-the-build-customizations-to-your-project"></a>Derleme özelleştirmeleri projenize eklemek için

1.  İçinde **Çözüm Gezgini**projesi için kısayol menüsünü açın ve ardından **derleme bağımlılıkları**, **derleme özelleştirmeleri**. **Visual C++ derleme özelleştirmeleri dosyaları** iletişim kutusu görüntülenir.

2.  Altında **kullanılabilir yapı özelleştirme dosyaları**, bu tabloda açıklandığı gibi projenizde, kullanmak istediğiniz varlık türlerine karşılık gelen onay kutularını seçin:

    |Varlık türü|Özelleştirme adı oluşturma|
    |----------------|------------------------------|
    |Dokular ve görüntüleri|**ImageContentTask (.targets, .props)**|
    |3B modelleri|**MeshContentTask (.targets, .props)**|
    |Gölgelendiriciler|**ShaderGraphContentTask (.targets, .props)**|

3.  Seçin **Tamam** düğmesi.

## <a name="include-assets-in-your-build"></a>Derlemenizde varlıkları içerir
 Projenizi değişik kullanmak istediğiniz 3B varlıklar hakkında bilir, sonraki adım, hangi dosyaların 3B varlıklar olduğunu ve hangi tür varlıklar bunlar bildirmektir.

### <a name="to-add-an-asset-to-your-build"></a>Derleme için bir varlık eklemek için

1.  İçinde **Çözüm Gezgini**, projenizin bir malın kısayol menüsünü açın ve ardından **özellikleri**. Varlığın **özellik sayfası** iletişim kutusu görüntülenir.

2.  Olduğundan emin olun **yapılandırma** ve **Platform** özellikleri değişikliklerinizi uygulamak istediğiniz değerlere ayarlanır.

3.  Altında **yapılandırma özellikleri**, seçin **genel**ve özellik ızgarasının altında **genel**ayarlayın **öğesi türü** özelliği uygun içerik ardışık düzen öğesi türü için. Örneğin, bir resim veya doku dosya için tercih **görüntü içerik ardışık düzen**.

    > [!IMPORTANT]
    > Varsayılan olarak, Visual Studio çok sayıda görüntü dosya kullanarak kategorilere olduğunu varsayar **görüntü** öğesi Visual Studio'ya yerleşik türü. Bu nedenle, değiştirmek zorunda **öğesi türü** görüntü içerik ardışık düzen tarafından işlenmek üzere istediğiniz her görüntü özelliği. Diğer içerik türlerine kanal 3B modeller ve görsel gölgelendirici grafik varsayılan doğru için kaynak dosyaları **öğesi türü**.

4.  Seçin **Tamam** düğmesi.

Üç İşte içerik ardışık düzen öğesi türleri ve ilişkili kaynak ve çıktı dosya türleri.

|Öğe türü|Kaynak dosya türleri|Çıkış dosyası biçimi|
|---------------|-----------------------|------------------------|
|**Görüntü içerik ardışık düzen**|Taşınabilir Ağ Grafikleri (.png)<br /><br /> JPEG (.jpg, .jpeg, .jpe, .jfif)<br /><br /> Doğrudan çizim yüzeyini (.dds)<br /><br /> Grafik Değişim Biçimi (.gif)<br /><br /> Bit eşlem (.bmp, .dib)<br /><br /> Etiketli Görüntü dosyası biçimi (.tif, .tiff)<br /><br /> Targa (.tga)|DirectDraw yüzeyini (.dds)|
|**İçerik ardışık düzen mesh**|AutoDesk FBX değişim dosyası (.fbx)<br /><br /> Collada DAE dosya (.dae)<br /><br /> Wavefront OBJ dosyasının (.obj)|3B Kafes dosyası (.cmo)|
|**Gölgelendirici içerik ardışık düzen**|Görsel gölgelendirici grafik (.dgsl)|Derlenmiş gölgelendirici çıktısı (.cso)|

## <a name="configure-asset-content-pipeline-properties"></a>Varlık içerik ardışık düzen özelliklerini yapılandırın

Her varlık dosyasının içeriği ardışık düzen özelliklerini, belirli bir şekilde oluşturulacak şekilde ayarlayabilirsiniz.

### <a name="to-configure-content-pipeline-properties"></a>İçerik ardışık düzen özelliklerini yapılandırmak için

1.  İçinde **Çözüm Gezgini**projenizdeki varlık dosyası için kısayol menüsünü açın ve ardından **özellikleri**. Varlığın **özellik sayfası** iletişim kutusu görüntülenir.

2.  Olduğundan emin olun **yapılandırma** ve **Platform** özellikleri değişikliklerinizi uygulamak istediğiniz değerlere ayarlanır.

3.  Altında **yapılandırma özellikleri**, içerik ardışık düzen düğümü seçin — örneğin, **görüntü içeriği ardışık düzen** doku ve görüntü varlıklar için — ve ardından özelliklerini özellik kılavuzunda ayarlamak uygun değerleri. Örneğin, derleme zamanında mipmaps için bir doku varlık oluşturmak için ayarlar **oluşturmak MIPS** özelliğine **Evet**.

4.  Seçin **Tamam** düğmesi.

### <a name="image-content-pipeline-configuration"></a>Görüntü içerik ardışık düzen yapılandırma

Doku varlık oluşturmak için görüntüyü içerik ardışık düzen aracını kullandığınızda, çeşitli yollarla doku sıkıştırmak, MIP düzeyleri derleme zamanında oluşturulan ve çıktı dosyası adını değiştirmek olup olmadığını gösterir.

|Özellik|Açıklama|
|--------------|-----------------|
|**Sıkıştır**|Çıktı dosyası için kullanılan sıkıştırma türünü belirtir.<br /><br /> Mevcut seçenekler şunlardır:<br /><br /> -   **Sıkıştırma yok**<br />-   **BC1_UNORM sıkıştırma**<br />-   **BC1_UNORM_SRGB sıkıştırma**<br />-   **BC2_UNORM sıkıştırma**<br />-   **BC2_UNORM_SRGB sıkıştırma**<br />-   **BC3_UNORM sıkıştırma**<br />-   **BC3_UNORM_SRGB sıkıştırma**<br />-   **BC4_UNORM sıkıştırma**<br />-   **BC4_SNORM sıkıştırma**<br />-   **BC5_UNORM sıkıştırma**<br />-   **BC5_SNORM sıkıştırma**<br />-   **BC6H_UF16 sıkıştırma**<br />-   **BC6H_SF16 sıkıştırma**<br />-   **BC7_UNORM sıkıştırma**<br />-   **BC7_UNORM_SRGB sıkıştırma**<br /><br /> Hangi sıkıştırma hakkında biçimleri DirectX farklı sürümleri desteklenir daha fazla bilgi için bkz [DXGI için Programlama Kılavuzu](http://go.microsoft.com/fwlink/p/?LinkId=246265).|
|Önceden çarpılan alfa biçimine Dönüştür|**Evet** görüntünün çıktı dosyasında; önceden çarpılan alfa biçimine dönüştürmek için Aksi halde, **Hayır**. Yalnızca çıktı dosyası değiştirildiğinde, kaynak görüntü değiştirilmez.|
|**MIPS oluştur**|**Evet** derleme zamanında tam MIP zinciri oluşturmak ve çıktı dosyasına; eklenecek Aksi halde, **Hayır**. Varsa **Hayır**ve bir mipmap zinciri kaynak dosyasını zaten içeriyor sonra çıktı dosyası MIP zincirine sahip olur; Aksi halde, çıktı dosyası hiçbir MIP zinciri sahip olacaktır.|
|**İçerik çıktı**|Çıktı dosyası adını belirtir. **Önemli:** çıkış dosyasının dosya adı uzantısı değiştirme üzerinde etkisi yoktur, dosya biçimi.|

### <a name="mesh-content-pipeline-configuration"></a>Mesh içerik ardışık düzen yapılandırma

Mesh varlık oluşturmak için Kafes içerik ardışık düzen aracını kullandığınızda, çıktı dosyası adını değiştirebilirsiniz.

|Özellik|Açıklama|
|--------------|-----------------|
|**İçerik çıktı**|Çıktı dosyası adını belirtir. **Önemli:** çıkış dosyasının dosya adı uzantısı değiştirme üzerinde etkisi yoktur, dosya biçimi.|

### <a name="shader-content-pipeline-configuration"></a>Gölgelendirici içerik ardışık düzen yapılandırma

Gölgelendirici varlık oluşturmak için gölgelendirici içerik ardışık düzen aracını kullandığınızda, çıktı dosyası adını değiştirebilirsiniz.

|Özellik|Açıklama|
|--------------|-----------------|
|**İçerik çıktı**|Çıktı dosyası adını belirtir. **Önemli:** çıkış dosyasının dosya adı uzantısı değiştirme üzerinde etkisi yoktur, dosya biçimi.|

## <a name="load-and-use-3d-assets-at-run-time"></a>Yük 3B varlıkları ve çalışma zamanında kullanma

### <a name="use-textures-and-images"></a>Kullanım dokuları ve görüntüleri

Direct3D Doku kaynakları oluşturmak için işlevleri sağlar. Direct3D 11 D3DX11 yardımcı programı kitaplığı doku kaynakları ve kaynak görünümlerini doğrudan görüntü dosyaları oluşturmak için ek işlevler sağlar. Doku kaynağı Direct3D 11 oluşturma hakkında daha fazla bilgi için bkz: [dokuları](http://go.microsoft.com/fwlink/p/?LinkID=246267). Bir doku kaynağı veya kaynak görünümü oluşturmak için D3DX11 kitaplığını kullanma hakkında daha fazla bilgi için bir görüntü dosyasından bkz [nasıl yapılır: bir doku bir dosyadan başlatmak](http://go.microsoft.com/fwlink/p/?LinkId=246268).

### <a name="use-3d-models"></a>3B modelleri kullanma

Direct3D 11, kaynakları 3B modellerinden oluşturma için işlevleri sağlamaz. Bunun yerine, 3B model dosyasını okur ve 3D modeli ve modelin gerektiren herhangi bir kaynağa temsil eden köşe ve dizin arabellekleri oluşturan kod yazmak zorunda — Örneğin, doku veya gölgelendiriciler.

### <a name="use-shaders"></a>Gölgelendiriciler kullanın

Direct3D gölgelendirici kaynakları oluşturma ve bunları programlanabilir grafik ardışık düzene bağlama işlevleri sağlar. Direct3D içinde bir gölgelendirici kaynak oluşturmak ve ardışık düzene bağlama hakkında daha fazla bilgi için bkz: [HLSL için Programlama Kılavuzu](http://go.microsoft.com/fwlink/p/?LinkID=261521).

Programlanabilir grafik ardışık düzeninde sonraki ardışık düzen aşaması anlayabileceği bir şekilde biçimlendirilmiş bir sonuç ardışık her aşamanın vermeniz gerekir. Gölgelendirici Tasarımcısı'nı yalnızca piksel gölgelendiriciler oluşturduğundan, bu da aldığı veri bekler biçiminde olduğundan emin olmak için uygulamanıza anlamına gelir. Birkaç programlanabilir gölgelendirici aşamaları önce piksel gölgelendirici oluşur ve geometrik dönüştürmeleri gerçekleştirebilirsiniz — köşe gölgelendirici, hull gölgelendirici, etki alanı gölgelendirici ve geometri gölgelendirici. Programlanabilir olmayan Mozaik döşeme aşama da piksel gölgelendirici önce oluşur. Bu aşamalar hangisinin doğrudan piksel gölgelendirici önündeki olsun, bu biçiminde sonucu vermeniz gerekir:

```hlsl
struct PixelShaderInput
{
    float4 pos : SV_POSITION;
    float4 diffuse : COLOR;
    float2 uv : TEXCOORD0;
    float3 worldNorm : TEXCOORD1;
    float3 worldPos : TEXCOORD2;
    float3 toEye : TEXCOORD3;
    float4 tangent : TEXCOORD4;
    float3 normal : TEXCOORD5;
};
```

Gölgelendirici kullanan gölgelendirici Tasarımcısı düğümleri bağlı olarak, bu tanımları göre biçiminde ek veri sağlamak olabilir:

```
Texture2D Texture1 : register( t0 );
Texture2D Texture2 : register( t1 );
Texture2D Texture3 : register( t2 );
Texture2D Texture4 : register( t3 );
Texture2D Texture5 : register( t4 );
Texture2D Texture6 : register( t5 );
Texture2D Texture7 : register( t6 );
Texture2D Texture8 : register( t7 );

TextureCube CubeTexture1 : register( t8 );
TextureCube CubeTexture2 : register( t9 );
TextureCube CubeTexture3 : register( t10 );
TextureCube CubeTexture4 : register( t11 );
TextureCube CubeTexture5 : register( t12 );
TextureCube CubeTexture6 : register( t13 );
TextureCube CubeTexture7 : register( t14 );
TextureCube CubeTexture8 : register( t15 );

SamplerState TexSampler : register( s0 );

cbuffer MaterialVars : register (b0)
{
    float4 MaterialAmbient;
    float4 MaterialDiffuse;
    float4 MaterialSpecular;
    float4 MaterialEmissive;
    float MaterialSpecularPower;
};

cbuffer LightVars : register (b1)
{
    float4 AmbientLight;
    float4 LightColor[4];
    float4 LightAttenuation[4];
    float3 LightDirection[4];
    float LightSpecularIntensity[4];
    uint IsPointLight[4];
    uint ActiveLights;
}

cbuffer ObjectVars : register(b2)
{
    float4x4 LocalToWorld4x4;
    float4x4 LocalToProjected4x4;
    float4x4 WorldToLocal4x4;
    float4x4 WorldToView4x4;
    float4x4 UVTransform4x4;
    float3 EyePosition;
};

cbuffer MiscVars : register(b3)
{
    float ViewportWidth;
    float ViewportHeight;
    float Time;
};
```

## <a name="related-topics"></a>İlgili konular

|Başlık|Açıklama|
|-----------|-----------------|
|[Nasıl yapılır: Mipmap'leri İçeren Dokuyu Dışa Aktarma](../designers/how-to-export-a-texture-that-contains-mipmaps.md)|Görüntü içerik ardışık düzen önceden hesaplanan mipmaps içeren bir doku dışarı aktarmak için nasıl kullanılacağını açıklar.|
|[Nasıl yapılır: Ön Çarpımlı Alfa kullanan Doku Dışa Aktarma](../designers/how-to-export-a-texture-that-has-premultiplied-alpha.md)|Görüntü içerik ardışık düzen önceden çoğaltılmış alfa değerleri içeren bir doku dışarı aktarmak için nasıl kullanılacağını açıklar.|
|[Nasıl yapılır: Direct2D veya Javascript Uygulamaları Kullanmak için Doku Dışa Aktarma](../designers/how-to-export-a-texture-for-use-with-direct2d-or-javascipt-apps.md)|Görüntü içerik ardışık düzen Direct2D veya JavaScript uygulamasında kullanılan bir doku dışarı aktarmak için nasıl kullanılacağını açıklar.|
|[3B varlıklarıyla oyunları ve uygulamaları için çalışma](../designers/working-with-3-d-assets-for-games-and-apps.md)|Visual Studio oluşturma ve düzenleme dokuları ve görüntüleri, 3B modeller ve gölgelendiriciler içeren 3B varlıklar sağlar düzenleme araçlarını açıklar.|
|[Nasıl Yapılır: Gölgelendiriciyi Dışarı Aktarma](../designers/how-to-export-a-shader.md)|Nasıl gölgelendirici gölgelendirici Tasarımcısı'ndan dışarı aktarılacağını açıklar.|