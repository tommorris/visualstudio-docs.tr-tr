---
title: Visual Studio Kabuğu | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- shell, Visual Studio
- Visual Studio, shell
ms.assetid: cb124ef4-1a6b-4bfe-bfbf-295ef9c07f36
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2d96d4204e105324a9c209f74f9aee160c3eddde
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42634263"
---
# <a name="visual-studio-shell"></a>Visual Studio Kabuğu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Visual Studio Shell](https://docs.microsoft.com/visualstudio/extensibility/internals/visual-studio-shell).  
  
[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Kabuktur tümleştirmesi, birincil aracı [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Ortak Hizmetleri paylaşan VSPackage'ı etkinleştirmek için gerekli işlevselliği sağlar. Çünkü mimari amacı, [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] birincil işlevselliği Vspackage'larda vest kullanmaktır Kabuğu'nu temel işlevleri sağlar ve kendi bileşeni Vspackage'lar arasında arası iletişimi desteklemek için bir çerçevedir.  
  
## <a name="shell-responsibilities"></a>Kabuk sorumlulukları  
 Kabuk aşağıdaki anahtar sorumluluklara sahiptir:  
  
-   Temel kullanıcı arabirimini (UI) öğeleri (COM arabirimleri) destek. Bunlar, varsayılan menüleri ve araç çubukları, belge pencere çerçeveleri veya çok Belgeli Arabirim (MDI) alt pencereler ve aracı pencere çerçeveleri ve yerleştirme desteği içerir.  
  
-   Tüm açık belgelerde çalıştırılan Belge tablosu (RDT) çalışan bir listesini, belgelerin Kalıcılık koordine ve birden fazla yolla ya da uyumsuz şekilde bir belge açılamıyor güvence altına almak için koruma.  
  
-   Komut Yönlendirme ve komut işleme arabirimini destekleyen `IOleCommandTarget`.  
  
-   VSPackage uygun zamanlarda yükleniyor. VSPackage gecikme yükleme Kabuk performansını geliştirmek için gereklidir.  
  
-   Belirli yönetme paylaşılan hizmetler gibi <xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>, temel Kabuk işlevleri sağlayan ve <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>, temel Pencereleme işlevleri sağlar.  
  
-   Çözüm (.sln) dosyaları yönetme. Çözümler, ilgili projelerin, Visual C++ 6.0 (.dsw) çalışma alanı dosyaları benzer grupları içerir.  
  
-   İzleme Kabuk genelinde seçimi, bağlam ve para birimi. Kabuk öğeleri aşağıdaki türde izler:  
  
    -   Geçerli proje  
  
    -   Geçerli proje öğe veya öğe kimliği geçerli <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>  
  
    -   Geçerli seçim için **özellikleri** penceresi veya `SelectionContainer`  
  
    -   Kimlikleri veya komutlar, menüler ve araç çubukları görünürlüğünü denetleme CmdUIGuids UI bağlamı  
  
    -   Etkin pencereyi, belge ve geri alma yöneticisi gibi şu anda etkin öğeleri  
  
    -   Dinamik Yardım sürücü kullanıcı bağlamı öznitelikleri  
  
 Kabuk yüklü VSPackages ve geçerli Hizmetleri arasındaki iletişim de aracılık. Kabuk temel özellikleri destekler ve bunları tüm VSPackages tümleşik kullandırır [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Bu temel özellikleri, aşağıdaki öğeleri ekleyin:  
  
-   **Hakkında** iletişim kutusu ve karşılama ekranı  
  
-   **Yeni ve varolan öğeyi ekle ekleme** iletişim kutuları  
  
-   **Sınıf Görünümü** penceresi ve **Nesne Tarayıcısı**  
  
-   **Başvuruları** iletişim kutusu  
  
-   **Belge Anahattı** penceresi  
  
-   **Dinamik Yardım** penceresi  
  
-   **Bulma** ve **değiştirin**  
  
-   **Projeyi açın** ve **açık dosya** iletişim kutuları üzerinde **yeni** menüsü  
  
-   **Seçenekleri** iletişim kutusunda **Araçları** menüsü  
  
-   **Özellikleri** penceresi  
  
-   **Çözüm Gezgini**  
  
-   **Görev listesi** penceresi  
  
-   **Araç Kutusu**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>   
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>   
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>   
 [VSPackage’lar](../../extensibility/internals/vspackages.md)

