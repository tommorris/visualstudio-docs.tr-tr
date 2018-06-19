---
title: Visual Studio için Düzen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: c19e3022-047c-43b6-a046-a82717efed4f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2e26caa6e47f0f2ee2a20611cf12e166832e007b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31149022"
---
# <a name="layout-for-visual-studio"></a>Visual Studio için düzeni
Visual Studio iletişim kutuları çoğunluğu olan [yardımcı programı iletişim düzeni](../../extensibility/ux-guidelines/layout-for-visual-studio.md#BKMK_UtilityDialogLayout), bu izleme standart iletişim kutuları unthemed olduğu [Windows Masaüstü iletişim düzeni ilkeleri](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742499\(v=vs.85\).aspx). Kullanıcı Arabiriminde yenilemek Visual Studio taşır gibi bazı daha belirgin iletişim kutuları gibi ürün tanımlama deneyimleri kurar yeni bir tasarım sahiptir. Bunlar [konulu iletişim düzeni](../../extensibility/ux-guidelines/layout-for-visual-studio.md#BKMK_ThemedDialogLayout) konulu bir görünümü vardır.  
  
##  <a name="BKMK_UtilityDialogLayout"></a> Yardımcı programı iletişim düzeni  
  
-   Bir yardımcı programı iletişim içindeki tüm denetimler üst/sol başlatmak ve aşağı akış gerekir.  
  
-   Hiçbir zaman merkezi denetimleri büyük alanını doldurmak için bir iletişim kutusu.  
  
-   Ortam yazı tipi tüm iletişim metni için kullanın. Görsel spec yazılırken bir özel yazı tipi ve boyutu seçmek yerine ortamı yazı tipi belirtin. Bkz: [ortam yazı tipi](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TheEnvironmentFont).  
  
-   Hedef craftsmanship kalite desteklemek için tutarlı denetim aralığı ve yerleştirme kullanın.  
  
-   İletişim kutuları daha büyük bir denetimleri, benzersiz juxtaposition denetimlerin veya her ikisini sayısından daha karmaşık hale gelebilir. Bu karmaşık durumlarda, kullanıcıya ayrıştırmak için mantıksal bir akışa vermek için Denetim gruplandırmaları arasında yeterli alana izin verir.  
  
### <a name="utility-dialog-layout-examples"></a>Yardımcı programı iletişim düzeni örnekleri  
 Tüm boyutlar piksel olarak ifade edilir.  
  
 ![Etiketleri yukarıda denetimleri için iletişim aralığı](../../extensibility/ux-guidelines/media/0801-a_utilityspacingabove.png "0801 a_UtilitySpacingAbove")  
  
 **Şekil 08.01-a: Aralığı yönergeleri denetimleri yukarıda etiketlerle yardımcı programı iletişim kutuları**  
  
 ![Etiketleri sol tarafındaki denetimleri için iletişim aralığı](../../extensibility/ux-guidelines/media/0801-b_utilityspacingleft.png "0801 b_UtilitySpacingLeft")  
  
 **Şekil 08.01-b: Aralığı yönergeleri denetimleri solundaki etiketlerle yardımcı programı iletişim kutuları**  
  
### <a name="layout-details"></a>Düzen ayrıntıları  
  
#### <a name="margins"></a>Kenar boşlukları  
  
-   Tüm iletişim kutularını kenarındaki 12 piksel kenarlığın olması gerekir.  
  
-   Bir grup çerçevesinde kenar boşluklarını çerçeve kenarından 9 piksel olmalıdır.  
  
-   Sekme denetimi içindeki kenar boşluklarını sekme denetimi kenarından 6 piksel olmalıdır.  
  
#### <a name="command-buttons"></a>Komut düğmeleri  
  
-   Komut düğmeleri içeriği değil, iletişim kutusu çerçevesi çalışmayabilir. Bunlar altındaki sağ yerleştirilmelidir ve düğmeleri ayrı ayrı olarak ayarlamak için yukarıdaki değişken yeterli alana sahip olmalıdır.  
  
-   İletişim kutusu içinde çalışan yatay düğmeleri varsa, diğer komut düğmesi dikey yığın sağ üst yapılandırmadır. Bkz: [iç komut düğmeleri](../../extensibility/ux-guidelines/layout-for-visual-studio.md#BKMK_InteriorCommandButtons) aşağıda.  
  
-   Komut düğmeleri (alt sol/Merkezi iletişim) solundaki alanı iletişim işlemi denetimleri "bant" bir parçası olarak kabul edilir. Bu alan intrude tek şey genel görev ya da iletişim ilgili Yardım bağlantıdır.  
  
-   Komut düğmeleri 75 x 23 piksel olmalıdır.  
  
-   Komut düğmeleri birbirinden 6 piksel olmalıdır.  
  
 ![Temel düğme hizalaması](../../extensibility/ux-guidelines/media/0801-c_buttonalign.png "0801 c_ButtonAlign")  
  
 **Şekil 08.01-c: Temel düğmesi hizalama**  
  
#### <a name="labels"></a>Etiketler  
  
-   Sola Hizala tüm etiketler.  
  
-   Denetim sit etiketler, bunlar sola altındaki denetimi ile tam olarak Hizala ve etiketinin alt diğer denetim (örneğin, bir birleşik giriş kutusu) üst yukarıda 5 piksel olmalıdır.  
  
-   Denetimler soldan sit etiketleri, etiket giriş denetiminin arasındaki en küçük genişliği 10 pikseldir. Metin kutuları, birleşik giriş kutuları veya diğer denetimleri hizalama için örtük bir ikinci sütun kurulmalıdır.  
  
-   Etiketler cümle olan ve iki nokta ile izlenir. Bkz: [metin stili](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TextStyle).  
  
#### <a name="distance-between-controls"></a>Denetimler arasındaki uzaklığı  
 Denetimleri makul yığın. Yığılmış denetimler arasındaki boşlukları için mutlak hiçbir kılavuz yoktur. Denetimler arasındaki tightness arasında iletişim kutuları biraz değişebilir. Önerilen boşluk dikey Denetim etiketi çiftleri için 20 piksel ve yatay Denetim etiketi çiftleri için 9 piksel olabilir. Yatay çiftleri için minimum denetimi aralığı 6 pikseldir.  
  
 ![Denetimler arasındaki uzaklığı önerilen](../../extensibility/ux-guidelines/media/0801-d_controldistance.png "0801 d_ControlDistance")  
  
 **Şekil 08.01-d: Denetimler arasındaki uzaklığı önerileri**  
  
#### <a name="control-indentation"></a>Denetim girinti  
 Denetimleri iç içe geçmiş, iç denetimleriyle yatay yukarıdaki denetimi, genellikle etiket sol köşesine hizalar.  
  
 ![İç içe geçmiş denetim hizalaması](../../extensibility/ux-guidelines/media/0801-e_controlalign.png "0801 e_ControlAlign")  
  
 **Şekil 08.01-e: İç içe denetimi hizalama**  
  
#### <a name="control-width"></a>Denetim genişliği  
 Bir metin kutusu veya başka benzer denetimler genişliğini ortalama giriş alanı için daha uzun olmalıdır. Ortalama İngilizce word beş karakterdir. Örneğin, bir uzun yol adı gerektiren bir metin kutusu yatay düzenini tanır, sürece olmalıdır çalışırken bir açılır platform adları yalnızca en uzun girişini sağlayan bir uzunluğu olmalıdır.  
  
#### <a name="helper-text"></a>Yardımcı metin  
  
-   Bir iletişim kutusu iletişim amacı hakkında daha fazla bilgi sağlayan yardımcı metin görüntüleyebilirsiniz. Bu genellikle en üstünde bulunur ve 1-2 cümleleri olabilir.  
  
-   Satır uzunluğu ayrıştırma ve okumak bir kullanıcı için bir rahat genişliği olmalıdır. Orta iletişim en fazla 550 piksel genişliğinde olmalıdır.  
  
####  <a name="BKMK_InteriorCommandButtons"></a> İç komut düğmeleri  
 Daha karmaşık iletişim kutularında, bir iç denetim iletişim kutusu yürütme düğmeleri bulunduğu etkileyebilecek kendi ilgili düğmeleri olabilir.  
  
-   Bir dikey hizalamasını (sütun) iç düğmeleri kullanın **Tamam**/**iptal** sağ alt köşedeki yatay olarak yerleştirilir.  
  
-   İç, yatay hizalama (satır) düğmeleri kullanın **Tamam**/**iptal** sağ üst köşedeki dikey olarak yerleştirilir. Bu daha az görülen bir durumdur.  
  
-   İç düğme boyutu 75 x 23 piksel cinsinden boyutu eşleşen standart düğme boyutunu hedef **Tamam**/**iptal** düğmeleri mümkün olduğunda. Düğme etiketi standart düğme boyutunu aşan düğmesi yaparsa, bu kümesindeki diğer düğmeleri bu daha geniş bir boyut ile uyumlu olmalıdır.  
  
 ![Yatay Tamam ve İptal düğmeleri](../../extensibility/ux-guidelines/media/0801-f_horizokcan.png "0801 f_HorizOKCan")  
  
 **Şekil 08.01-f: Dikey iç düğmelerini yatay Tamam/iptal ile**  
  
 ![Dikey Tamam ve İptal düğmeleri](../../extensibility/ux-guidelines/media/0801-g_vertokcan.png "0801 g_VertOKCan")  
  
 **Şekil 08.01-g: Yatay iç düğmeleriyle dikey Tamam/iptal**  
  
#### <a name="browse-button"></a>[Gözat...] düğmesi  
 **[Gözat...]**  bir metin kutusu izleyin düğmeleri üç nokta dahil olmak üzere, tam olarak "Gözat..." Yazım. Alan sıkı veya birden çok varsa **[Gözat...]**  düğmesi ekrandaki düğmeleri yalnızca üç nokta sınırlı.  
  
##  <a name="BKMK_ThemedDialogLayout"></a> Konulu iletişim düzeni  
 Visual Studio'da konulu iletişim kutuları açık bir görünümü vardır ve daha fazla boşluk sunar. Tipografi vurgu ve daha açık satır aralığı ve yazı tipi boyutlarını ve ağırlıklarını Çeşitleme sunumunun ilgi daha fazla sağlar. Mümkünse, chrome ve başlık çubukları azaltılmış veya kaldırılan. Bu iletişim kutularının düzenini temel bu deseni izlemelidir:  
  
1.  İletişim kutusunun arka plan Beyaz ' dir.  
  
2.  Orta değer gri olarak 1 piksel kural kenarlık yoktur.  
  
3.  İletişim kutusu başlığı artık bir başlık çubuğunda bulunur, ancak visual faiz ve daha büyük bir nokta boyutu Vurgu sağlar. (Yazı tipi boyutu bölümüne bakın [metin stili](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TextStyle).)  
  
4.  Bir açıklama gibi ek metinle birlikte etiketleri olmalıdır **ortam yazı tipi + kalın**.  
  
5.  İç sütunları açık gri 1 piksel kuralında ayrılmıştır.  
  
6.  Varsayılan, hiçbir alt çizgi bağlantınız. Renk değişikliği artı alt çizgi vurgulu ve basılı durumlar vardır.  
  
7.  Düğmeleri Yürüt (gibi **Tamam**/**iptal**) sağ alt köşedeki sit.  
  
### <a name="themed-dialog-layout-examples"></a>Konulu iletişim düzeni örnekleri  
 ![Konulu iletişim düzeni](../../extensibility/ux-guidelines/media/0801-h_themeddialog.png "0801 h_ThemedDialog")  
  
 **Şekil 08.01-y: Konulu iletişim**  
  
 ![Konulu iletişim boyutları](../../extensibility/ux-guidelines/media/0801-i_themeddialogdimensions.png "0801 i_ThemedDialogDimensions")  
  
 **Şekil 08.01-i: Konulu iletişim kutusu - boyutları**  
  
 ![Konulu iletişim yazı tipleri](../../extensibility/ux-guidelines/media/0801-j_themeddialogfonts.png "0801 j_ThemedDialogFonts")  
  
 **Şekil 08.01-j: Konulu iletişim kutusu - yazı tipleri**  
  
 ![Konulu iletişim renkleri](../../extensibility/ux-guidelines/media/0801-k_themeddialogcolors.png "0801 k_ThemedDialogColors")  
  
 **Şekil 08.01-k: Konulu iletişim kutusu - renkleri**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio için uygulama düzenleri](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md)   
 [Denetimleri (Windows)](https://msdn.microsoft.com/library/windows/desktop/dn742399.aspx)   
 [İletişim kutuları (Windows)](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742499\(v=vs.85\).aspx)