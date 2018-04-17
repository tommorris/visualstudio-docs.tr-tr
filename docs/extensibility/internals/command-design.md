---
title: Komut tasarım | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- commands
- commands, implementation
ms.assetid: 097108c3-f758-4b87-89d6-b32d12d9041a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 43b83e5a02fb84ad09531f87b3120168bad0b2e0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="command-design"></a>Komut tasarım
Bir komut bir VSPackage eklediğinizde, görünmesi olduğu, kullanılabilir olduğunda ve nasıl işleneceğini olduğunu belirtmeniz gerekir.  
  
## <a name="defining-commands"></a>Komutları tanımlama  
 Yeni komutları tanımlamak için bir Visual Studio komut tablosu (.vsct) dosya VSPackage projenize ekleyin. Visual Studio Paketi şablonu kullanarak bir VSPackage oluşturduysanız, projenin bu dosyalardan birini içerir. Daha fazla bilgi için bkz: [Visual Studio komut tablosu (. Vsct) dosyaları](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md).  
  
 Visual Studio komutları görüntüleyebilmesi bulduğu tüm .vsct dosyaları birleştirir. Bu dosyalar ikili VSPackage birbirinden farklı olduğundan, Visual Studio komutları bulmak için paketi yüklemek sahip değil. Daha fazla bilgi için bkz: [nasıl VSPackages ekleme kullanıcı arabirimi öğeleri](../../extensibility/internals/how-vspackages-add-user-interface-elements.md).  
  
 Visual Studio kullanan <xref:Microsoft.VisualStudio.Shell.ProvideMenuResourceAttribute> menüsü kaynaklarını ve komutları tanımlayan için kayıt özniteliği. Daha fazla bilgi için bkz: [uygulama](../../extensibility/internals/command-implementation.md).  
  
 Komutları çalışma zamanında bir birkaç farklı yolla değiştirilebilir. Bunlar görüntülenen veya gizli, etkin veya devre dışı. Bunlar farklı bir metin veya simgelerini görüntülemek veya farklı değerler içeriyor. Visual Studio, VSPackage yüklenmeden önce özelleştirme büyük bir bölümünü gerçekleştirilebilir. Daha fazla bilgi için bkz: [nasıl VSPackages ekleme kullanıcı arabirimi öğeleri](../../extensibility/internals/how-vspackages-add-user-interface-elements.md).  
  
## <a name="command-handlers"></a>Komut işleyicileri  
 Bir komut oluşturduğunuzda komutu çalıştırmak için bir olay işleyicisi sağlamanız gerekir. Kullanıcı komut seçerse, uygun şekilde yönlendirilmelidir. Bir komut yönlendirme etkinleştirmek veya devre dışı bırakın, gizleme veya görüntüleme ve kullanıcı bunu yapmak seçerse yürütmek için doğru VSPackage gönderme anlamına gelir. Daha fazla bilgi için bkz: [yönlendirme algoritması](../../extensibility/internals/command-routing-algorithm.md).  
  
## <a name="the-visual-studio-command-environment"></a>Visual Studio komut ortamı  
 Visual Studio VSPackages herhangi bir sayıda barındırabilir ve her biri kendi komut kümesini katkıda bulunabilir. Ortam geçerli görev için uygun olan komutları görüntüler. Daha fazla bilgi için bkz: [kullanılabilirlik](../../extensibility/internals/command-availability.md) ve [seçimi bağlam nesneleri](../../extensibility/internals/selection-context-objects.md).  
  
 Yeni komutlar, menüler, araç çubukları veya kısayol menüleri tanımlayan bir VSPackage yerel veya yönetilen derlemelerde kaynaklara başvuran kayıt defteri girdileri aracılığıyla yükleme zamanında Visual Studio komut bilgilerini sağlar. Her kaynak sonra Visual Studio komut tablosu (.vsct) dosyası derlediğinizde üretilen bir ikili veri kaynağı (.cto) dosyası başvurur. Bu, her yüklü VSPackage yüklemek zorunda kalmadan birleştirilmiş komut kümelerini, menüleri ve araç çubuklarını sağlamak Visual Studio sağlar.  
  
### <a name="command-organization"></a>Komut kuruluş  
 Ortam grup, öncelik ve menü komutlarını yerleştirir.  
  
-   Gruplardır mantıksal koleksiyonları, ilgili komutlar, örneğin, **Kes**, **kopya**, ve **Yapıştır** komut grubu. Menülerde görünen komutları gruplarıdır.  
  
-   Öncelik tek tek bir grup komutlarda menüsünde görünme sırasını belirler.  
  
-   Menü grupları için kapsayıcı görevi görür.  
  
 Ortam bazı komutlar, grupları ve menüleri önceden belirler. Daha fazla bilgi için bkz: [varsayılan komutu, Grup ve araç çubuğu yerleştirme](../../extensibility/internals/default-command-group-and-toolbar-placement.md).  
  
 Bir komut birincil bir gruba atanabilir. Ana menü yapısı hem de komut konumunu birincil grup denetimleri **Özelleştir** iletişim kutusu. Bir komutu, birden çok gruba görüntülenebilir; Örneğin, bir komut ana menü, bir kısayol menüsü ve bir araç olabilir. Daha fazla bilgi için bkz: [nasıl VSPackages ekleme kullanıcı arabirimi öğeleri](../../extensibility/internals/how-vspackages-add-user-interface-elements.md).  
  
### <a name="command-routing"></a>Komut Yönlendirme  
 Çağırma ve komutlar için VSPackages yönlendirme işlemi nesne örneklerine yöntemleri çağırma işlemi farklıdır.  
  
 Ortam komutları sırayla geçerli seçimi temel alan, en içteki (yerel) komutu içeriğinden en dıştaki (Genel) bağlam yönlendirir. Komutu yürütmek için ilk içeriği, işleme adrestir. Daha fazla bilgi için bkz: [yönlendirme algoritması](../../extensibility/internals/command-routing-algorithm.md).  
  
 Çoğu durumda, ortam kullanarak komutları işleyen <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> arabirimi. Komut yönlendirme düzeni komutları işlemek birçok farklı nesneleri sağladığından <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> herhangi bir sayıda nesneleri uygulanması olabilir; bu dahil Microsoft ActiveX denetimleri, pencere görünüm uygulamaları, belge nesneleri, proje hiyerarşileri ve VSPackage nesneleri kendilerini (genel komutları). Bazı özel durumlarda, örneğin, komutları bir hiyerarşide yönlendirme <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> arabirimi uygulanan.  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Uygulama](../../extensibility/internals/command-implementation.md)|Bir VSPackage komutları uygulamak açıklar.|  
|[Kullanılabilirlik](../../extensibility/internals/command-availability.md)|Visual Studio bağlam hangi komutlar kullanılabilir nasıl belirlediğini açıklar.|  
|[Yönlendirme algoritması](../../extensibility/internals/command-routing-algorithm.md)|Visual Studio komut yönlendirme mimarisi farklı VSPackages tarafından işlenecek komutları nasıl sağladığını açıklar.|  
|[Yerleştirme yönergeleri](../../extensibility/internals/command-placement-guidelines.md)|Visual Studio ortamında komutları konumlandırmak nasıl önerir.|  
|[VSPackage’ların Kullanıcı Arabirimi Öğeleri Eklemesi](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)|Nasıl VSPackages Visual Studio komut mimarisi en iyi kullanabilir açıklar.|  
|[Varsayılan Komut, Grup ve Araç Çubuğu Yerleşimi](../../extensibility/internals/default-command-group-and-toolbar-placement.md)|Nasıl VSPackages Visual Studio'ya dahil olan komutları en iyi şekilde kullanabileceğinizi açıklar.|  
|[VSPackage’ları Yönetme](../../extensibility/managing-vspackages.md)|Visual Studio VSPackages nasıl yükler açıklar.|  
|[Visual Studio Komut Tablosu (.Vsct) Dosyaları](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)|Düzen ve VSPackages komutlarda görünümünü tanımlamak için kullanılan XML tabanlı .vsct dosyaları hakkında bilgi sağlar.|