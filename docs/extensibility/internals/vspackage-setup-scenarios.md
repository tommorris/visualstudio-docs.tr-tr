---
title: VSPackage Kurulum senaryoları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, deployment considerations
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b58400330bb2032354d28a7b76729a5d7f85fd3c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="vspackage-setup-scenarios"></a>VSPackage Kurulum senaryoları

VSPackage Yükleyicinizle esneklik için tasarlamanız önemlidir. Örneğin, bir güvenlik düzeltme eki gelecekte serbest bırakmanız gerekebilir veya kapsamlı yan yana sürüm oluşturma desteği gerektiren bir iş stratejisi değişebilir.

İçinde [Visual Studio, birden çok sürümleri destekleyen](../../extensibility/supporting-multiple-versions-of-visual-studio.md), avantajları ve yan yana yüklemesini destekleme sorunlar hakkında bilgi edinebilirsiniz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] , VSPackage paylaşılan veya yan yana yüklemesini ile. Kısacası, yan yana VSPackages, yeni özellikleri desteklemek için en çok esneklik [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

Bu konuda tartışılan senaryoların yalnızca seçimlerinizi değildir, ancak önerilen en iyi yöntemler olarak sunulur.

## <a name="components-privacy-and-sharing"></a>Bileşenleri, gizlilik ve paylaşma

### <a name="make-your-components-independent"></a>Bileşenlerinizi bağımsız olun

Tanımlamak ve bir bileşen doldurmak sonra Ata bir `GUID`ve bileşen dağıtmak için kendi birleşim değiştiremezsiniz. Bir bileşenin birleşim değiştirirseniz, sonuçta elde edilen bileşeni yeni bir ile yeni bir bileşen olmalıdır `GUID`. Bu bilgiler verildiğinde, her bileşen bağımsız, kendi birimi yaparak en büyük sürüm oluşturma esnekliği karşılanan. Bileşenleri yöneten kuralları hakkında daha fazla bilgi için bkz: [bileşen kodunu değiştirme](http://msdn.microsoft.com/library/aa367849\(VS.85\).aspx) ve [ne olur bileşen kuralları bozuk olduğu?](http://msdn.microsoft.com/library/aa372795\(VS.85\).aspx).

### <a name="do-not-mix-shared-and-private-resources-in-a-component"></a>Bir bileşenin paylaşılan ve özel kaynakları karıştırmamanızı

Başvuru sayım bileşen düzeyinde gerçekleşir. Sonuç olarak, bir bileşen paylaşılan ve özel kaynaklarında karıştırma paylaşılan kaynakları da geçersiz kılmadan bir yürütülebilir dosya gibi özel kaynakları güncelleştirmek mümkün kılar. Bu senaryo, geriye dönük uyumluluk sorunları oluşturur ve yan yana özellik oluşturma kısıtlar.

Örneğin, kullanılan kayıt defteri değerleri, VSPackage ile kaydetmek için [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] bir bileşeni, VSPackage Visual Studio ile kaydetmek için kullanılan birinden ayrı tutulmalıdır. Paylaşılan dosyaları veya kayıt defteri değerlerini henüz başka bir bileşeni gidin.

## <a name="scenario-1-shared-vspackage"></a>Senaryo 1: Paylaşılan VSPackage

Bu senaryoda, bir Paylaşılan VSPackage (Visual Studio birden fazla sürümünü destekleyen tek bir ikili bir Windows Installer paketinde geliyordu. Visual Studio her sürümü kaydetme, kullanıcı tarafından seçilebilen özellikleri tarafından denetlenir. Özellikler ayırmak için atandığında, her bileşenin tek tek yükleme veya kaldırma işlemi, farklı sürümlerini VSPackage tümleştirme denetiminde kullanıcıya veren seçilebilir olduğunu de anlamına [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. (Bkz [Windows Yükleyici'nin özellikleri](http://msdn.microsoft.com/library/aa372840\(VS.85\).aspx) Windows Installer paketinde özelliklerini kullanma hakkında daha fazla bilgi için.)

![VS Paylaşılan VSPackage yükleyici](../../extensibility/internals/media/vs_sharedpackage.gif "VS_SharedPackage")

Çizimde gösterildiği gibi paylaşılan bileşenler her zaman yüklü Feat_Common özelliğinin bir parçası yapılır. Feat_VS2002 ve Feat_VS2003 özellikleri görünür hale getirerek kullanıcıların tümleştirmek için VSPackage istedikleri hangi sürümlerinin Visual Studio yükleme zamanında seçebilirsiniz. Kullanıcılar, Windows Installer Bakım modu eklemek veya özellikleri, bu durumda ekler veya Visual Studio farklı sürümlerinden VSPackage kayıt bilgileri kaldırır kaldırmak için de kullanabilirsiniz.

> [!NOTE]
> Bir özelliğin görüntü sütunu 0 olarak ayarlanması gizler. 1 gibi bir düşük düzey sütun değeri her zaman yüklenecek sağlar. Daha fazla bilgi için bkz: [INSTALLLEVEL özelliği](http://msdn.microsoft.com/library/aa369536\(VS.85\).aspx) ve [özellik tablosu](http://msdn.microsoft.com/library/aa368585.aspx).

## <a name="scenario-2-shared-vspackage-update"></a>Senaryo 2: Paylaşılan VSPackage güncelleştirme

Bu senaryoda, Senaryo 1 VSPackage yükleyicisinde güncelleştirilmiş bir sürümünü geliyordu. Tartışma amacıyla güncelleştirme Visual Studio için destek ekler, ancak de daha basit bir güvenlik düzeltme eki olabilir veya hata düzeltme hizmet paketi. Yeni bileşenleri yüklemek için Windows Installer'ın kuralları, zaten sistemde değişmeden bileşenleri değil kopyalanması gerektirir. Bu durumda, sürüm 1.0 zaten mevcut olan bir sistemi güncelleştirilen bileşenin Comp_MyVSPackage.dll üzerine ve onun bileşeniyle Comp_VS2005_Reg Feat_VS2005 yeni özellik eklemek için kullanıcıların izin.

> [!CAUTION]
> Her bir VSPackage paylaşılır arasında birden fazla sürümünü [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], VSPackage sonraki sürümleri, Visual Studio'nun önceki sürümleri ile geriye dönük uyumluluğu korumak önemlidir. Geriye dönük uyumluluk korunamaz burada yan yana, özel VSPackages kullanmanız gerekir. Daha fazla bilgi için bkz: [Visual Studio, birden çok sürümleri destekleyen](../../extensibility/supporting-multiple-versions-of-visual-studio.md).

![VS Paylaşılan VS Paketi güncelleştirme yükleyicisi](../../extensibility/internals/media/vs_sharedpackageupdate.gif "VS_SharedPackageUpdate")

Bu senaryo, küçük yükseltmeler için Windows Installer'ın destek yararlanarak bir yeni VSPackage yükleyicisi gösterir. Kullanıcılar yalnızca sürüm 1.1 yükleyin ve sürüm 1.0 yükseltir. Ancak, sistemdeki sürüm 1.0 gerekli değildir. Aynı yükleyicisi, sürüm 1.0 olmadan bir sistemde sürüm 1.1 yükler. Bir yükseltme yükleyici ve bir tam ürün yükleyicisi geliştirme iş gitmek gerekli değildir, bu şekilde Küçük yükseltmeler sağlamak için avantajı sağlamasıdır. Bir yükleyici hem işlerini yapar. Bir güvenlik düzeltme veya hizmet paketi kaybolabileceğini bunun yerine Windows Installer düzeltme eklerinin faydalanın. Daha fazla bilgi için bkz: [düzeltme eki ve yükseltme](http://msdn.microsoft.com/library/aa370579\(VS.85\).aspx).

## <a name="scenario-3-side-by-side-vspackage"></a>Senaryo 3: Yan yana VSPackage

Bu senaryo iki VSPackage yükleyicileri sunar — bir her Visual Studio .NET 2003 ve Visual Studio sürümü. Her yükleyici yan yana veya özel, VSPackage (özellikle oluşturulur ve belirli bir sürümü için Visual Studio yüklü bir) yükler. Her VSPackage kendi bileşenidir. Sonuç olarak, her tek tek düzeltme ekleri veya bakım hizmet verilebilir serbest bırakır. VSPackage DLL artık sürüme özgü olduğundan, aynı bileşeni DLL olarak kayıt bilgileri dahil güvenlidir.

![VS Yan Yana VS paketi yükleyicisi](../../extensibility/internals/media/vs_sbys_package.gif "VS_SbyS_Package")

Her yükleyici de iki yükleyicileri arasında paylaşılan kodu içerir. Her iki .msi dosyası yüklendiğinde paylaşılan kod bir ortak konuma yüklüyse, paylaşılan kod yalnızca bir kez yüklenir. İkinci yükleyici yalnızca bileşen üzerindeki bir başvuru sayısını artırır. Başvuru sayısı VSPackages birini kaldırılırsa, paylaşılan kod için diğer VSPackage kalmasını sağlar. İkinci VSPackage de kaldırılırsa, paylaşılan kodu kaldırılacak.

## <a name="scenario-4-side-by-side-vspackage-update"></a>Senaryo 4: Yan yana VSPackage güncelleştirme

Bu senaryoda, VSPackage Visual Studio için bir güvenlik açığını başlayamıyorsa ve bir güncelleştirme vermek gerekiyor. Senaryo 2 olduğu gibi güncelleştirmeleri yanı sıra güvenlik düzeltme ekini dahil güvenlik düzeltme ekini zaten yerinde ile yeni yüklemeler dağıtmak için mevcut bir yüklemesi yeni bir .msi dosyası oluşturabilirsiniz.

Bu durumda genel derleme önbelleğinde (GAC) yüklü bir yönetilen VSPackage VSPackage olur. Güvenlik düzeltme ekini içerecek şekilde yeniden yapılandırdığınızda, derleme sürüm numarasını düzeltme numarası kısmıyla değiştirmeniz gerekir. Kayıt bilgileri yeni derleme sürüm numarası önceki sürümü üzerine yazar için neden [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] sabit derlemesi yüklenemedi.

![VS Yan Yana VS Paketi güncelleştirme yükleyicisi](../../extensibility/internals/media/vs_sbys_packageupdate.gif "VS_SbyS_PackageUpdate")

Yan yana derlemeler dağıtımı hakkında daha fazla bilgi için bkz: [basitleştirme dağıtım ve çözme DLL cehennemi .NET Framework ile](http://msdn.microsoft.com/library/ms973843.aspx).

## <a name="see-also"></a>Ayrıca Bkz.

[Windows Installer](http://msdn.microsoft.com/library/cc185688\(VS.85\).aspx)  
[Visual Studio'nun Birden Çok Sürümünü Destekleme](../../extensibility/supporting-multiple-versions-of-visual-studio.md)