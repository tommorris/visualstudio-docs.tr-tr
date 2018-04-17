---
title: DPI Issues2 adresleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 359184aa-f5b6-4b6c-99fe-104655b3a494
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: dc0801d3fb43188ac3371ed7e5e7394b0e3aad72
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="addressing-dpi-issues"></a>DPI sorunlarını çözdükten
Cihazlar artan sayıda "yüksek çözünürlüklü" ekranlar yayımlayan. Bu ekranlar genellikle 200 inç başına piksel (ppi) vardır. Bir uygulama bu bilgisayarlarda çalışmaya aygıtın normal görüntüleme uzaklıkta içeriği görüntüleme gereksinimlerini karşılamak üzere ölçeği için içerik gerektirir. 2014 sürümünden itibaren birincil yüksek yoğunluklu görüntüler mobil cihazlar (tabletler, clamshell dizüstü bilgisayarları ve telefonları) bilgi işlem hedefidir.  
  
 Windows 8.1 ve üzeri görüntüler ve burada makine hem de yüksek yoğunluklu bağlı olduğu ve aynı anda standart yoğunluklu görüntüler ortamları çalışmak bu makineleri etkinleştirmek için çeşitli özellikler içerir.  
  
-   Windows izin verebilir, Ölçek içerik "Make metin ve diğer öğelerin daha büyük veya küçük" kullanarak cihazı için (Windows XP itibaren kullanılabilir) ayarlama.  
  
-   Windows 8.1 ve üzeri otomatik olarak farklı piksel densities görüntüler arasında taşındıklarında tutarlı olacak şekilde çoğu uygulama için içerik ölçeklendirir. Birincil görüntü yüksek yoğunluklu (% 200 Ölçeklendirmesi) ve ikincil görüntü standart yoğunluğu (% 100) olduğunda, Windows otomatik olarak uygulama penceresi içeriği ikincil ekranda ölçeklenir (tarafından işlenen her 4 piksel için görüntülenen 1 piksel Uygulama).  
  
-   Windows için piksel yoğunluğu ölçekleme ve görüntüleme (Windows 7 ve üzeri, OEM yapılandırılabilir) için uzaklık görüntüleme hakkı varsayılan olur.  
  
-   Otomatik olarak Windows (itibariyle Windows 8.1 S14) 280 ppi aşan yeni cihazlarda % 250 içerik yukarı ölçeklendirebilirsiniz.  
  
 Windows artan piksel sayıları yararlanmak için bir yol UI'yi ölçeklendirme postalarla sahiptir. Bir uygulama bu sisteme kendisini "sistemi DPI farkında." bildirerek kabul eder Bunu yapmazsanız uygulamalar, sistem tarafından ölçeklenir. Bu, tüm uygulama hep piksel uzatılmış olduğu bir "benzer öğe" kullanıcı deneyimi neden olabilir. Örneğin:  
  
 ![DPI benzer sorunlar](../extensibility/media/dpi-issues-fuzzy.png "DPI benzer sorunlar")  
  
 Visual Studio DPI ölçeklendirme uyumlu olarak kabul eder ve bu nedenle değil "sanallaştırılır."  
  
 Windows (ve Visual Studio) sistemi tarafından belirlenen Etkenler ölçeklendirme postalarla farklı yolu vardır birkaç kullanıcı Arabirimi teknolojileri yararlanın. Örneğin:  
  
-   WPF denetimleri bir CİHAZDAN bağımsız şekilde (birimler, değil piksel) ölçer. WPF kullanıcı Arabirimi için geçerli DPI otomatik olarak ölçeklendirir.  
  
-   UI çerçevesi bağımsız olarak tüm metin boyutları nokta olarak ifade edilir ve bu nedenle sisteminde DPI bağımsız olarak kabul edilir. Win32, WinForms ve WPF metin zaten ölçeği doğru görüntüleme cihazı için çizildiğinde.  
  
-   Win32/WinForms iletişim kutuları ve windows metinle - Örneğin, kılavuz, akış ve tablo düzen panelleri yeniden boyutlandırır düzeni etkinleştirme için yöntemler vardır. Bu yazı tipi boyutlarını artan yükleyen ölçeklenmez sabit kodlanmış piksel konumlarına kaçınma etkinleştirin.  
  
-   Sistem tarafından sağlanan simgeler veya sistem ölçümleri (örneğin, SM_CXICON ve SM_CXSMICON) temel kaynaklar zaten ölçeklenir.  
  
## <a name="older-win32-gdi-gdi-and-winforms-based-ui"></a>Eski Win32 (GDI, GDI +) ve WinForms tabanlı kullanıcı Arabirimi  
 WPF zaten yüksek DPI olsa da, Win32/GDI tabanlı kodumuza çoğunu başlangıçta aklınızda DPI farkındalıkta yazılmadı. Windows API'ları DPI ölçeklendirme sağlamıştır. Win32 sorunları düzeltmelere bu ürün genelinde tutarlı bir şekilde kullanmanız gerekir. Visual Studio yardımcıyı sağlanan işlevselliği çoğaltma ve ürün arasında tutarlılık sağlamaya önlemek için sınıf kitaplığı.  
  
## <a name="high-resolution-images"></a>Yüksek çözünürlüklü görüntüler  
 Bu bölüm, öncelikle Visual Studio 2013 genişletme geliştiriciler için değildir. Visual Studio 2015, Visual Studio'ya yerleşik Görüntü hizmeti kullanın. Visual Studio birçok sürümü desteği/hedef gerek ve önceki sürümlerde yok olduğundan bu nedenle 2015'te görüntü hizmetini kullanarak bir seçenek değil de bulabilirsiniz. Bu bölümde ayrıca sizin için ise.  
  
## <a name="scaling-up-images-that-are-too-small"></a>Çok küçük resimleri ölçeklendirme  
 Çok küçük resimler "yukarı ölçeklendirilemez" ve GDI ve bazı yaygın yöntemleri kullanarak WPF çizilir. Yönetilen DPI yardımcı sınıfları iç ve dış Visual Studio tümleştiricileri simgeler, bit eşlemler, imagestrips ve imagelists ölçeklendirme adresine kullanılabilir. Win32 tabanlı yerel C / C ++ Yardımcıları HICON, HBITMAP, HIMAGELIST ve VsUI::GdiplusImage ölçekleme için kullanılabilir. Bir bit eşlem genellikle ölçeklendirme yalnızca Yardımcısı kitaplığına bir başvuru dahil olmak üzere sonra tek satır değişiklik gerektirir. Örneğin:  
  
```cpp  
(Unmanaged)  VsUI::DpiHelper::LogicalToDeviceUnits(&hBitmap);  
```  
  
```csharp  
(WinForms) DpiHelper.LogicalToDeviceUnits(ref image);  
```  
  
 Bir ImageList ölçeklendirme olup ImageList yükleme zamanında tamamlandıktan ve çalışma zamanında eklenir bağlıdır. Bir bit eşlem gibi tam yükleme zamanında LogicalToDeviceUnits() ile ImageList çağırır. Kod ImageList oluşturma önce tek bir bit eşlem yük gerektiğinde ImageList görüntü boyutunu ölçeklendirmek emin olun:  
  
```csharp  
imagelist.ImageSize = DpiHelper.LogicalToDeviceUnits(imagelist.ImageSize);  
```  
  
 Yerel kodda boyutları ImageList gibi oluştururken Genişletilebilir:  
  
```cpp  
ImageList_Create(VsUI::DpiHelper::LogicalToDeviceUnitsX(16),VsUI::DpiHelper::LogicalToDeviceUnitsY(16), ILC_COLOR32|ILC_MASK, nCount, 1);  
```  
  
 İşlevler Kitaplığı'nda yeniden boyutlandırma algoritması belirtme izin verir. Ne zaman imagelists içinde yerleştirilecek ölçeklendirme görüntüleri için saydamlığı kullanılan arka plan rengini belirttiğinizden emin olun veya NearestNeighbor (hangi %125 ve % 150 deformasyonları neden olur) ölçeklendirme kullanın.  
  
 Başvurun <xref:Microsoft.VisualStudio.PlatformUI.DpiHelper> MSDN'de belgelerin.  
  
 Aşağıdaki tabloda, Etkenler ölçeklendirme görüntüleri karşılık gelen DPİ'de nasıl ölçeklendirilmesi gerektiğini örnekleri gösterilmektedir. Yeşil görüntülerinde bizim en iyi uygulama (% 100-% 200 DPI ölçeklendirme) Visual Studio 2013'ten itibaren gösterin:  
  
 ![Ölçeklendirme DPI sorunları](../extensibility/media/dpi-issues-scaling.png "ölçeklendirme DPI sorunları")  
  
## <a name="layout-issues"></a>Düzen sorunları  
 Ortak yerleşim sorunları öncelikle keserek noktaları ölçeklendirilmiş kullanıcı arabiriminde ve birbiriyle göreli yerine Mutlak Konumlar (özellikle, piksel birimleri) kullanılarak önlenebilir. Örneğin:  
  
-   Düzen/metin konumlar ölçeği artırılmış görüntüleri için hesabı ayarlamanız gerekir.  
  
-   Kılavuzları sütun genişliklerini ölçeği artırılmış metin için ayarlanmış olması gerekir.  
  
-   Sabit kodlanmış boyutları veya öğeler arasındaki boşluğu ayrıca ölçeklendirilmiş gerekir. Yalnızca metin boyutlara dayanan boyutları genellikle ince olduklarından yazı tipleri otomatik olarak ölçeklendirilir.  
  
 Yardımcı işlevleri kullanılabilir <xref:Microsoft.VisualStudio.PlatformUI.DpiHelper> X ve Y Ekseninde ölçekleme izin veren sınıfı:  
  
-   LogicalToDeviceUnitsX/LogicalToDeviceUnitsY (izin işlevler X ölçeklendirme / Y ekseni)  
  
-   int alanı (10); DpiHelper.LogicalToDeviceUnitsX =  
  
-   int yüksekliği = VsUI::DpiHelper::LogicalToDeviceUnitsY(5);  
  
 Rect, nokta ve boyutu gibi nesneleri ölçekleme izin vermek için LogicalToDeviceUnits aşırı vardır.  
  
## <a name="using-the-dpihelper-libraryclass-to-scale-images-and-layout"></a>Ölçek görüntüler ve düzeni DPIHelper kitaplığı/sınıfını kullanma  
 Visual Studio DPI yardımcı kitaplık yerel ve yönetilen formlarında kullanılabilir ve Visual Studio Kabuğu dışında başka uygulamalar tarafından kullanılabilir.  
  
 Kitaplık kullanmak için Git [Visual Studio VSSDK genişletilebilirliği örnekleri](https://github.com/Microsoft/VSSDK-Extensibility-Samples) ve yüksek DPI_Images_Icons örnek kopyalama  
  
 Kaynak dosyalarında VsUI::DpiHelper sınıfının statik işlevleri çağırmak ve VsUIDpiHelper.h içerir:  
  
```cpp  
#include "VsUIDpiHelper.h"  
  
int cxScaled = VsUI::DpiHelper::LogicalToDeviceUnitsX(cx);  
VsUI::DpiHelper::LogicalToDeviceUnits(&hBitmap);  
  
```  
  
> [!NOTE]
>  Yardımcı işlevleri modül düzeyi veya sınıf düzeyi statik değişkenler kullanmayın. Kitaplık için iş parçacığı eşitleme istatistikleri de kullanır. ve sipariş başlatma sorunlarla karşılaşırsanız. Statik olmayan üye değişkenleri için bu istatistikleri Dönüştür ya da (bunlar ilk erişimde oluşturulan için) bunları işlevi sarmalayın.  
  
 Visual Studio ortamın içinde çalışacak yönetilen koddan DPI yardımcı işlevleri erişmek için:  
  
-   Süren proje Kabuk MPF en son sürümünü başvurmalıdır. Örneğin:  
  
    ```csharp  
    <Reference Include="Microsoft.VisualStudio.Shell.14.0.dll" />  
    ```  
  
-   Proje başvurularını sahip olduğundan emin olun **System.Windows.Forms**, **PresentationCore**, ve **PresentationUI**.  
  
-   Kod içinde kullanma **Microsoft.VisualStudio.PlatformUI** DpiHelper sınıfının ad alanı ve çağrı statik işlevler. Desteklenen türler için (noktaları, boyutları, dikdörtgenler vb.), yeni döndüren uzantısı işlevler nesneleri ölçeklendirilmiş sağlanan vardır. Örneğin:  
  
    ```csharp  
    using Microsoft.VisualStudio.PlatformUI;  
    double x = DpiHelper.LogicalToDeviceUnitsX(posX);  
    Point ptScaled = ptOriginal.LogicalToDeviceUnits();  
    DpiHelper.LogicalToDeviceUnits(ref bitmap);  
  
    ```  
  
## <a name="dealing-with-wpf-image-fuzziness-in-zoomable-ui"></a>WPF görüntü belirsizlik yakınlaştırılabilir arabiriminde postalarla  
 WPF'de, bit eşlemler otomatik olarak tarafından WPF Resim veya büyük ekran görüntüleri için iyi çalışır, ancak algılanan belirsizlik oluşturduğundan menü öğesi simgelerinin için uygun değil yüksek kaliteli çift kübik algoritmasını (varsayılan) kullanarak geçerli DPI yakınlaştırma düzeyini yeniden boyutlandırılıyor .  
  
 Öneriler:  
  
-   Logo görüntüsü ve başlıkları resim, varsayılan için <xref:System.Windows.Media.BitmapScalingMode> modu yeniden boyutlandırma kullanılabilirdi.  
  
-   Menü öğeleri ve yansır görüntüleri için <xref:System.Windows.Media.BitmapScalingMode> belirsizlik (en % 200 ve %300) ortadan kaldırmak diğer bozulma yapıları neden olmaz olduğunda kullanılmalıdır.  
  
-   Büyük yakınlaştırma değil (örneğin, %250 veya % 350) % 100'ün katları düzeyleri için çift kübik yansır görüntülerle ölçeklendirme belirsiz, soluk kullanıcı Arabiriminde sonuçlanır. Daha iyi sonuç ilk NearestNeighbor görüntüsüyle % 100 oranında (örneğin, %200 veya % 300) en büyük katına ölçekleme ve buradan çift kübik ile ölçeklendirme tarafından alınır. Özel durum bkz: WPF görüntüleri için büyük DPI prescaling düzeyleri daha fazla bilgi için.  
  
 Üye DpiHelper SAX Microsoft.VisualStudio.PlatformUI ad alanında <xref:System.Windows.Media.BitmapScalingMode> bağlama için kullanılabilir. Visual Studio Kabuğu'nu modu ürün hep, DPI ölçeklendirme bağlı olarak Ölçeklendirme çarpanı bit eşlem denetlemek izin verir.  
  
 XAML'de kullanmak için ekleyin:  
  
```xaml  
xmlns:vsui="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Shell.14.0"  
  
<Setter Property="RenderOptions.BitmapScalingMode" Value="{x:Static vs:DpiHelper.BitmapScalingMode}" />  
  
```  
  
 Visual Studio Kabuğu'nu en üst düzey windows ve iletişim kutuları zaten bu özelliği ayarlar. Visual Studio'da çalışan WPF tabanlı UI zaten bu devralır. Ayarı UI belirli, parçalarını dağıtılmaz, XAML/WPF UI kök öğesinin ayarlayabilirsiniz. Blend gibi dışı çalıştırmak Tasarımcı windows işlem ve burada bu gerçekleşir yerler Win32 üst ile öğelerde açılır pencereleri içerir.  
  
 Bazı kullanıcı Arabirimi, WPF tabanlı tasarımcıların (WPF Masaüstü ve Windows mağazası) ve Visual Studio metin düzenleyici gibi sistem kümesi DPI yakınlaştırma düzeyini bağımsız olarak ölçeklendirebilirsiniz. Bu durumlarda, DpiHelper.BitmapScalingMode kullanılmamalıdır. Düzenleyici'de bu sorunu gidermek için bir özel özellik oluşturulan IDE takım RenderOptions.BitmapScalingMode başlıklı. Bu özellik değeri HighQuality veya NearestNeighbor bağlı olarak sistem, kullanıcı Arabirimi ve birleşik yakınlaştırma düzeyini ayarlayın.  
  
## <a name="special-case-prescaling-wpf-images-for-large-dpi-levels"></a>Özel durum: WPF görüntüler büyük DPI düzeyleri için prescaling  
 (Örneğin, % 250, %350 vb.) % 100'ün katları olmayan çok geniş yakınlaştırma düzeyleri için belirsiz, soluk UI çift kübik sonuçlarında yansır görüntülerle ölçeklendirme. NET metin yanı sıra bu görüntüleri izlenim, optik görünümü gibi hemen hemen aynıdır. Görüntüleri göz ve dışında odak metin ile ilgili olarak daha yakın gibi görünüyor. Bu büyütülmüş boyutta ölçekleme sonuç ilk NearestNeighbor görüntüsüyle % 100 oranında (örneğin, %200 veya % 300) en büyük katına ölçekleme ve çift kübik (bir ek % 50) kalanı için ölçeklendirme tarafından geliştirilebilir.  
  
 Aşağıdaki sonuçları, farklar burada ilk ölçeklendirilir örneğidir -> % 100 -> Gelişmiş çift ölçeklendirme algoritması ile %200 % 250 ve ikincisi yalnızca çift kübik % 100 ile -> % 250.  
  
 ![DPI sorunları çift ölçeklendirme örnek](../extensibility/media/dpi-issues-double-scaling-example.png "DPI çift ölçeklendirme örnek sorunları")  
  
 Her bir görüntü öğesi görüntülemek için bu çift ölçekleme, XAML biçimlendirme kullanmak için kullanıcı Arabirimi etkinleştirmek için değiştirilmesi gerekir. Aşağıdaki örneklerde, WPF içinde çift ölçeklendirme DpiHelper kitaplığı ve Shell.12/14 kullanarak Visual Studio'da kullanımını göstermektedir.  
  
 1. adım: görüntünün % 200, %300 Prescale vb. NearestNeighbor kullanarak.  
  
 Bağlama, ya da XAML biçimlendirme uzantısı ile uygulanan dönüştürücü ile görüntü prescale. Örneğin:  
  
```xaml  
<vsui:DpiPrescaleImageSourceConverter x:Key="DpiPrescaleImageSourceConverter" />  
  
<Image Source="{Binding Path=SelectedImage, Converter={StaticResource DpiPrescaleImageSourceConverter}}" Width="16" Height="16" />  
  
<Image Source="{vsui:DpiPrescaledImage Images/Help.png}" Width="16" Height="16" />  
  
```  
  
 Görüntü ayrıca konulu olması gerekiyorsa (en değilse, gerekir), biçimlendirme ilk tema görüntü ve ardından önceden ölçekleme yapar farklı bir dönüştürücü kullanabilirsiniz. İşaretleme kullanabilirsiniz <xref:Microsoft.VisualStudio.PlatformUI.DpiPrescaleThemedImageConverter> veya <xref:Microsoft.VisualStudio.PlatformUI.DpiPrescaleThemedImageSourceConverter>istenen dönüştürme çıktı bağlı olarak.  
  
```xaml  
<vsui:DpiPrescaleThemedImageSourceConverter x:Key="DpiPrescaleThemedImageSourceConverter" />  
  
<Image Width="16" Height="16">  
  <Image.Source>  
    <MultiBinding Converter="{StaticResource DpiPrescaleThemedImageSourceConverter}">  
      <Binding Path="Icon" />  
      <Binding Path="(vsui:ImageThemingUtilities.ImageBackgroundColor)"    
               RelativeSource="{RelativeSource Self}" />  
      <Binding Source="{x:Static vsui:Boxes.BooleanTrue}" />  
    </MultiBinding>  
  </Image.Source>  
</Image>  
```  
  
 2. adım: son boyutu için geçerli DPI doğru olduğundan emin olun.  
  
 WPF kullanıcı arabirimini üzerinde UIElement BitmapScalingMode özelliğini kullanarak geçerli DPI için ölçeklendirmek için iki veya üç kez büyük kaynağına görüneceğini prescaled görüntü kullanarak bir görüntü denetimi gerekir. Bu etkiyi sayaç için birkaç yolla verilmiştir:  
  
-   % 100 özgün resim boyutu biliyorsanız, görüntü denetimi tam boyutunu belirtebilirsiniz. Bu boyutlar ölçeklendirme önce UI boyutunu uygulanan yansıtır.  
  
    ```xaml  
    <Image Source="{Binding Path=SelectedImage, Converter={StaticResource DpiPrescaleImageSourceConverter}}" Width="16" Height="16" />  
    ```  
  
-   Özgün resim boyutu bilinmiyorsa LayoutTransform son görüntü nesneyi ölçeklemek için kullanılabilir. Örneğin:  
  
    ```xaml  
    <Image Source="{Binding Path=SelectedImage, Converter={StaticResource DpiPrescaleImageSourceConverter}}" >  
        <Image.LayoutTransform>  
         <ScaleTransform  
             ScaleX="{x:Static vsui:DpiHelper.PreScaledImageLayoutTransformScale}"  
             ScaleY="{x:Static vsui:DpiHelper.PreScaledImageLayoutTransformScale}" />  
        </Image.LayoutTransform>  
    </Image>  
    ```  
  
## <a name="enabling-hdpi-support-to-the-weboc"></a>Alma WebOC için HDPI desteğini etkinleştirme  
 Varsayılan olarak, HDPI algılama ve destek alma WebOC denetimleri (örneğin, WPF veya Iwebbrowser2 arabirimi WebBrowser denetimi) etkinleştirmeyin. Sonuç yüksek çözünürlüklü ekranda çok küçük görüntü içeriğini katıştırılmış bir denetimle olacaktır. Belirli web alma WebOC örneğinde yüksek DPI desteğini nasıl etkinleştireceğinizi açıklar.  
  
 IDocHostUIHandler arabirimini uygulayan (MSDN makalesine bakın [IDocHostUIHandler](http://msdn.microsoft.com/library/aa753260.aspx) arabirimi):  
  
```idl  
[ComImport, InterfaceType(ComInterfaceType.InterfaceIsIUnknown),  
 Guid("BD3F23C0-D43E-11CF-893B-00AA00BDCE1A")]  
public interface IDocHostUIHandler  
{  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int ShowContextMenu(  
        [In, MarshalAs(UnmanagedType.U4)] int dwID,  
        [In] POINT pt,  
        [In, MarshalAs(UnmanagedType.Interface)] object pcmdtReserved,  
        [In, MarshalAs(UnmanagedType.IDispatch)] object pdispReserved);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int GetHostInfo([In, Out] DOCHOSTUIINFO info);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int ShowUI(  
        [In, MarshalAs(UnmanagedType.I4)] int dwID,  
        [In, MarshalAs(UnmanagedType.Interface)] object activeObject,  
        [In, MarshalAs(UnmanagedType.Interface)] object commandTarget,  
        [In, MarshalAs(UnmanagedType.Interface)] object frame,  
        [In, MarshalAs(UnmanagedType.Interface)] object doc);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int HideUI();  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int UpdateUI();  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int EnableModeless([In, MarshalAs(UnmanagedType.Bool)] bool fEnable);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int OnDocWindowActivate([In, MarshalAs(UnmanagedType.Bool)] bool fActivate);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int OnFrameWindowActivate([In, MarshalAs(UnmanagedType.Bool)] bool fActivate);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int ResizeBorder(  
        [In] COMRECT rect,  
        [In, MarshalAs(UnmanagedType.Interface)] object doc,  
        bool fFrameWindow);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int TranslateAccelerator(  
        [In] ref MSG msg,  
        [In] ref Guid group,  
        [In, MarshalAs(UnmanagedType.I4)] int nCmdID);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int GetOptionKeyPath(  
        [Out, MarshalAs(UnmanagedType.LPArray)] string[] pbstrKey,  
        [In, MarshalAs(UnmanagedType.U4)] int dw);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int GetDropTarget(  
        [In, MarshalAs(UnmanagedType.Interface)] IOleDropTarget pDropTarget,  
        [MarshalAs(UnmanagedType.Interface)] out IOleDropTarget ppDropTarget);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int GetExternal([MarshalAs(UnmanagedType.IDispatch)] out object ppDispatch);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int TranslateUrl(  
        [In, MarshalAs(UnmanagedType.U4)] int dwTranslate,  
        [In, MarshalAs(UnmanagedType.LPWStr)] string strURLIn,  
        [MarshalAs(UnmanagedType.LPWStr)] out string pstrURLOut);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int FilterDataObject(  
        IDataObject pDO,  
        out IDataObject ppDORet);  
    }   
```  
  
 İsteğe bağlı olarak, ICustomDoc arabirimini uygulayan (MSDN makalesine bakın [ICustomDoc](http://msdn.microsoft.com/library/aa753272.aspx) arabirimi):  
  
```idl  
[InterfaceType(ComInterfaceType.InterfaceIsIUnknown),  
 Guid("3050F3F0-98B5-11CF-BB82-00AA00BDCE0B")]  
public interface ICustomDoc  
{  
    void SetUIHandler(IDocHostUIHandler pUIHandler);  
}   
```  
  
 Alma WebOC'ın belgeyle IDocHostUIHandler uygulayan sınıfa ilişkilendirin. Yukarıdaki ICustomDoc arabirimi uygulanırsa, ardından alma WebOC'ın belge özelliği geçerlidir hemen bir ICustomDoc cast ve IDocHostUIHandler uygulayan sınıfa geçirme SetUIHandler yöntemini çağırın.  
  
```csharp  
// "this" references that class that owns the WebOC control and in this case also implements the IDocHostUIHandler interface  
ICustomDoc customDoc = (ICustomDoc)webBrowser.Document;  
customDoc.SetUIHandler(this);  
  
```  
  
 ICustomDoc arabirimi uygulamadı, alma WebOC'ın belge özelliği geçerlidir hemen sonra bir IOLE nesnesini cast ve IDocHostUIHandler uygulayan sınıfında SetClientSite yöntemini çağırmak gerekir. GetHostInfo yöntemi çağrısına iletilen DOCHOSTUIINFO DOCHOSTUIFLAG_DPI_AWARE bayrağını ayarlayın:  
  
```csharp  
public int GetHostInfo(DOCHOSTUIINFO info)  
{  
    // This is what the default site provides.  
    info.dwFlags = (DOCHOSTUIFLAG)0x5a74012;  
    // Add the DPI flag to the defaults  
    info.dwFlags |=.DOCHOSTUIFLAG.DOCHOSTUIFLAG_DPI_AWARE;  
    return S_OK;  
}  
```  
  
 Bu alma WebOC denetim HPDI destek almak için gereken tüm olmalıdır.  
  
## <a name="tips"></a>İpuçları  
  
1.  Belge özelliği alma WebOC denetimde değişirse, belgenin IDocHostUIHandler sınıfı ile yeniden ilişkilendirmek gerekebilir.  
  
2.  Yukarıdaki çalışmazsa, değişikliği DPI bayrağı için çekme değil alma WebOC bilinen bir sorun yoktur. Bu düzeltme en güvenilir anlamı iki çağrıları yakınlaştırma yüzdesini iki farklı değerlerini alma WebOC optik yakınlaştırma geçiş yapmak için yoludur. Ayrıca, bu geçici çözüm gerekiyorsa, her kayıt Bul çağrıda gerçekleştirmek gerekli olabilir.  
  
    ```csharp  
    // browser2 is a SHDocVw.IWebBrowser2 in this case  
    // EX: Call the Exec twice with DPI%-1 and then DPI% as the zoomPercent values  
    IOleCommandTarget cmdTarget = browser2.Document as IOleCommandTarget;  
    if (cmdTarget != null)  
    {  
        object commandInput = zoomPercent;  
        cmdTarget.Exec(IntPtr.Zero,  
                       OLECMDID_OPTICAL_ZOOM,  
                       OLECMDEXECOPT_DONTPROMPTUSER,  
                       ref commandInput,  
                       ref commandOutput);  
    }  
    ```