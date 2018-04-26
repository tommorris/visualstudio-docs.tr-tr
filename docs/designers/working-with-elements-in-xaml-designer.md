---
title: XAML Tasarımcısı'nda öğeleri ile çalışma
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: a29690bf-f212-4ac6-a77a-adc53d14102e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 3a3b45d8714c72e588f64cd5c1830cc97b9f136e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="working-with-elements-in-xaml-designer"></a>XAML Tasarımcısı'nda öğeleri ile çalışma
Öğeleri ekleyebilirsiniz — denetimleri, düzenleri ve şekiller — uygulamanıza kod ya da XAML Tasarımcısı kullanarak XAML'de. Bu konu Visual Studio veya Visual Studio için Blend'de XAML Tasarımcısı'nda öğeleri ile nasıl çalışılacağını açıklar.

## <a name="adding-an-element-to-a-layout"></a>Bir öğenin bir düzene ekleme
 *Düzen* boyutlandırma ve bir kullanıcı Arabiriminde öğeleri konumlandırma işlemidir. Görsel öğeleri yerleştirmek için bunları bir düzende konulmalıdır [Masası](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.panel.aspx). A `Panel` koleksiyonu olan bir alt özelliğine sahiptir, [FrameworkElement](http://msdn.microsoft.com/library/windows/apps/br208706.aspx) türleri. Çeşitli kullanabilirsiniz `Panel` alt öğeleri gibi [tuvale](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.canvas.aspx), [StackPanel](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.stackpanel.aspx), ve [kılavuz](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.grid.aspx), Düzen kapsayıcılar olarak hizmet verecek ve getirin ve öğeleri düzenlemek için bir sayfa üzerinde.

 Varsayılan olarak, bir `Grid` paneli, üst düzey düzeni kapsayıcı bir sayfaya veya forma içinde olarak kullanılır. Düzen panelleri, denetimleri veya üst düzey sayfa düzeni içindeki diğer öğeler ekleyebilirsiniz.

#### <a name="to-add-an-element-to-a-layout"></a>Bir düzene bir öğe eklemek için

-   XAML Tasarımcısı'nda, aşağıdakilerden birini yapın:

    -   Bir öğedeki çift **araç** (veya araç kutusunda bir öğe seçin ve Enter tuşuna basın).

    -   Bir öğeyi sürükleyin **araç** çalışma yüzeyi için.

    -   İçinde **araç**, çizim araçları birini seçin (örneğin, [elips](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.shapes.ellipse.aspx) veya [dikdörtgen](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.shapes.rectangle.aspx)) ve ardından öğeyi etkin panelinde çizin.

## <a name="changing-the-layering-order-of-elements"></a>Öğeleri katmanlama sırasını değiştirme
 XAML Tasarımcısı'nda yüzeyinde iki öğe olduğunda, tek bir öğede katmanlama sırayla diğer önünde görünür. Belge Anahattı öğelerinde listesinin altındaki en öndeki öğe penceredir (zaman dışında **bölmenin** özelliği bir öğe için ayarlanır). Bir öğe bir sayfa, form ya da düzen kapsayıcı eklediğinizde, öğe otomatik olarak active kapsayıcı öğe diğer öğeleri önüne yerleştirilir. Öğelerin sırasını değiştirmek için kullanabileceğiniz **sipariş** komutları veya Belge Anahattı penceresi nesne ağacında öğeleri sürükleyin.

#### <a name="to-change-the-layering-order"></a>Katmanlama sırasını değiştirmek için

-   Aşağıdakilerden birini yapın:

    -   İçinde **belge anahattı** penceresinde öğeleri yukarı veya istenen katmanlama sipariş oluşturmak için aşağı sürükleyin.

    -   Belge Anahattı penceresi veya katmanlama sırasını değiştirmek için işaret istediğiniz çalışma yüzeyi öğesinde sağ **sipariş**ve ardından aşağıdakilerden birini tıklatın:

        -   **Öne** öğesi bu süreç boyunca tüm siparişi öne getirmek için.

        -   **Öne** öğesi getirmek için sırada bir düzey ileri.

        -   **Geri göndermek** öğesi geri bir düzey sıraya göndermek için.

        -   **Geri Gönder** öğesi bu süreç boyunca tüm sırasını geri göndermek için.

     Değişiklik **bölmenin** özelliğinde **düzeni** Özellikleri penceresinde bölümü. Öğeleri, çakışan için **bölmenin** özelliği önceliklidir Belge Anahattı penceresinde gösterilen öğelerin sırasını. Düşük olan bir öğeyi **bölmenin** değerinin göründüğü önde öğeleri çakıştığında.

## <a name="changing-the-alignment-of-an-element"></a>Bir öğenin değiştirme
 Dayama çizgileri için öğeleri sürükleyerek veya menü komutlarını kullanarak çalışma yüzeyi öğelerinde hizalanmasını sağlayabilirsiniz.

 A *snapline* yardımcı olan görsel bir ipucu bir öğe diğer öğeleri uygulamasında göre hizalamak değil.

#### <a name="to-align-two-or-more-elements-by-using-menu-commands"></a>Menü komutlarını kullanarak iki veya daha fazla öğe hizalamak için

1.  Hizalamak istediğiniz öğeleri seçin. Tuşuna basarak ve öğeleri seçerken Ctrl tuşunu basılı tutarak birden çok öğe seçebilirsiniz.

2.  Altında aşağıdaki özelliklerden birini **HorizontalAlignment** içinde **düzeni** Özellikler penceresini bölümünü: **sol**, **Merkezi**, **Sağ**, veya **Esnetme**.

3.  Altında aşağıdaki özelliklerden birini **VerticalAlignment** içinde **düzeni** Özellikler penceresini bölümünü: **üst**, **Merkezi**, **Alt**, veya **Esnetme**.

#### <a name="to-align-two-or-more-elements-by-using-snaplines"></a>Dayama çizgileri kullanarak iki veya daha fazla öğe hizalamak için

-   En az iki öğe içeren bir düzende XAML Tasarımcısı'nda sürükleyin veya başka bir öğesiyle kenarına hizalanır şekilde öğelerden birini yeniden boyutlandırın.

     Kenarları hizalanır, bir *hizalama sınır* hizalama göstermek için görünür. Kırmızı kesikli çizgi hizalama sınırıdır. Hizalama sınırları yalnızca görünür **dayama çizgileri için tutturma** etkinleştirilir. Hizalama sınır gösteren yüzeyinin çizim için bkz: [XAML Tasarımcısını kullanarak bir kullanıcı Arabirimi oluşturma](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md).

## <a name="changing-the-an-elements-margins"></a>Değiştirme bir öğenin kenar boşlukları
 XAML Tasarımcısı'nda kenar boşluklarını öğenin yüzeyinde geçici boş alan miktarını belirler. Örneğin, bir öğenin dış kenarları ve sınırlarının arasındaki boşluk miktarı kenar boşluklarını belirtin bir `Grid` öğeyi içeren paneli. Kenar boşlukları bulunan öğeler arasında boşluk miktarını da belirtmeniz bir `StackPanel`.

#### <a name="to-change-an-elements-margins-in-the-properties-window"></a>Bir öğenin kenar boşluklarını Özellikleri penceresinde değiştirmek için

1.  Kenar boşlukları değiştirmek istediğiniz öğeyi seçin.

2.  Altında **düzeni** Özellikler penceresinde değeri (piksel veya yaklaşık 1/96 inç olan CİHAZDAN bağımsız birimler) herhangi birini değiştirin **kenar boşluğu** özellikleri (**üst**, **Sol**, **sağ**, veya **alt**).

#### <a name="to-change-an-elements-margins-in-the-artboard"></a>Çalışma yüzeyi bir öğenin kenar boşluklarını değiştirmek için

-   Bir öğenin yerleşim kapsayıcısı göre kenar boşluklarını değiştirmek için tıklatın. *marjı Donatıcılar* görünen çalışma yüzeyi öğesinde geçici öğe seçildiğinde ve bir düzen kapsayıcı içinde. Kenar boşluğu Donatıcılar gösteren çizim için bkz: [XAML Tasarımcısını kullanarak bir kullanıcı Arabirimi oluşturma](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md).

     Kenar boşluğu donatıcı dikey veya yatay olarak açıksa, bu kenar boşluğu ayarlanmamış. Kenar boşluğu donatıcı kapattıysanız, o kenar boşluğu ayarlanır.

     Kenar boşluğu donatıcı açıp ters kenar boşluğu ayarlanmamış ters kenar boşluğu çalışma yüzeyi öğesinde konumuna göre doğru değerine ayarlanır. Ters kenar boşlukları için gibi **sol** ve **sağ** kenar boşlukları, en az bir özellik her zaman olarak ayarlanmış.

    > [!IMPORTANT]
    >  Öğelerin yerleştirilmesi bazı düzeni kapsayıcılarda gibi bir <xref:Windows.UI.Xaml.Controls.Canvas>, kenar boşluğu Donatıcılar yok. Öğelerin yerleştirilmesi içinde bir <xref:Windows.UI.Xaml.Controls.StackPanel> sol ve sağ kenar boşluklarının veya yönünü bağlı olarak üst ve alt kenar boşluğu Donatıcılar ya da sahip `StackPanel`.

## <a name="grouping-and-ungrouping-elements"></a>Gruplandırma ve öğeleri grubu çözme
 XAML Tasarımcısı'nda iki veya daha fazla öğe gruplandırma, yeni bir düzen kapsayıcı oluşturur ve bu kapsayıcıdaki bu öğeleri yerleştirir. İki veya daha fazla öğe birlikte bir düzen kapsayıcıya yerleştirilerek kolayca seçin, taşıma ve o gruptaki öğeler tek bir öğede değilmiş gibi Grup Dönüştürme sağlar. Gruplandırma, birbirlerine bir gezinti öğesi yapmak düğmeleri gibi bazı şekilde ilişkili öğeleri tanımlamak için kullanışlıdır. Öğeleri çözerseniz öğeler yer düzen kapsayıcı yalnızca siliyorsunuz.

#### <a name="to-group-elements-into-a-new-layout-container"></a>Yeni bir düzen kapsayıcı % Grup elemanlara

1.  Gruplandırmak için kullanmak istediğiniz öğeleri seçin. (Birden çok öğe seçmek için tuşuna basın ve bunları tıklarken Ctrl tuşunu basılı tutun.)

2.  Seçilen öğeleri sağ tıklayın, fareyle **grubu içine**ve ardından grubun bulunmasını istediğiniz düzen kapsayıcı türüne tıklayın.

    > [!TIP]
    >  Seçerseniz <xref:Windows.UI.Xaml.Controls.Viewbox>, <xref:Windows.UI.Xaml.Controls.Border>, veya <xref:Windows.UI.Xaml.Controls.ScrollViewer> öğelerinizi gruplandırmak için öğeleri yeni bir yerleştirilir <xref:Windows.UI.Xaml.Controls.Grid> içinde panel <xref:Windows.UI.Xaml.Controls.Viewbox>, <xref:Windows.UI.Xaml.Controls.Border>, veya <xref:Windows.UI.Xaml.Controls.ScrollViewer>. Yalnızca bu düzen kapsayıcıları birinde öğeleri grubunu varsa <xref:Windows.UI.Xaml.Controls.Viewbox>, <xref:Windows.UI.Xaml.Controls.Border>, veya <xref:Windows.UI.Xaml.Controls.ScrollViewer> silinir ve <xref:Windows.UI.Xaml.Controls.Grid> panel kalır. Silinecek `Grid` paneli, öğeleri yeniden Çöz.

#### <a name="to-ungroup-elements-and-delete-the-layout"></a>Öğeleri grubunu ve düzeni silmek için

-   Çöz aktarmak istediğiniz gruba sağ tıklayın **Grubu Çöz**.

 Ayrıca Grup veya Çöz öğeleri Belge Anahattı penceresinde seçili öğeleri sağ tıklatıp yapabilecekleriniz **grubu içine** veya **Grubu Çöz**.

## <a name="resetting-the-element-layout"></a>Öğe düzeni sıfırlama
 Düzeni sıfırlama komutlarını kullanarak, bir öğenin belirli düzen özelliklerinin varsayılan değerlerini geri yükleyebilirsiniz. Bu komutu kullanarak, tek tek veya toplu olarak kenar boşluğu, hizalama, genişlik, yükseklik ve bir öğenin boyutunu sıfırlayabilirsiniz.

#### <a name="to-reset-the-element-layout"></a>Öğe düzeni sıfırlamak için

-   Belge Anahattı penceresi veya çalışma yüzeyi öğeye sağ tıklayın, seçin **düzeni**, **sıfırlama** *PropertyName*, burada *PropertyName*sıfırlamak istediğiniz özelliği (veya tercih **düzeni**, **Tümünü Sıfırla** öğesinin tüm yerleşim özellikleri sıfırlamak için).

## <a name="see-also"></a>Ayrıca bkz.

- [XAML Tasarımcısı kullanarak bir kullanıcı Arabirimi oluşturma](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md)