---
title: Visual Studio Kabuğu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- shell, Visual Studio
- Visual Studio, shell
ms.assetid: cb124ef4-1a6b-4bfe-bfbf-295ef9c07f36
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 71b624cee0e55f95f90a86eac943828bbc26ac97
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31144362"
---
# <a name="visual-studio-shell"></a>Visual Studio Kabuğu
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Kabuğu tümleştirmesine birincil aracı olan [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Kabuk ortak Hizmetleri paylaşmak VSPackages etkinleştirmek için gerekli işlevselliği sağlar. Çünkü mimari amacı [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] VSPackages içinde birincil işlevleri vest için kabuk temel işlevleri sağlamak ve kendi bileşen VSPackages arasında arası iletişimi desteklemek için bir çerçevedir.  
  
## <a name="shell-responsibilities"></a>Kabuk sorumlulukları  
 Kabuk aşağıdaki anahtar sorumlulukları vardır:  
  
-   (COM arabirimleri) destekleyen temel öğeleri kullanıcı arabirimi (UI). Bunlar, varsayılan menüleri ve araç çubukları, belge pencere çerçeveleri veya birden çok belge arabirimi (MDI) alt öğe pencerelerini ve aracı pencere çerçeveleri ve yerleşik destek içerir.  
  
-   Çalışan tüm açık belgelerde çalışan bir belge tablosu (RDT) listesini belgeleri kalıcılığı koordine etmek için ve bir belgede birden fazla şekilde ya da uyumsuz şekilde açılamıyor güvence altına almak için koruma.  
  
-   Komut Yönlendirme ve komut işleme arabirimi destekleyen `IOleCommandTarget`.  
  
-   VSPackages uygun zamanlarda yükleniyor. Gecikmeli yükleme bir VSPackage Kabuk performansını geliştirmek için gereklidir.  
  
-   Belirli paylaşılan yönetme hizmetleri gibi <xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>, temel Kabuğu işlevselliği sağlar ve <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>, temel Pencereleme işlevselliği sağlar.  
  
-   Çözüm (.sln) dosyalarını yönetme. Çözümleri ilgili projeleri, Visual C++ 6.0 çalışma (.dsw) dosyalarında benzer gruplarını içerir.  
  
-   İzleme Kabuk genelinde seçimi, içerik ve para birimi. Kabuk aşağıdaki türlerde öğeleri izler:  
  
    -   Geçerli projenin  
  
    -   Öğe kimliği geçerli ve geçerli proje öğesi <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>  
  
    -   Geçerli seçim için **özellikleri** penceresi veya `SelectionContainer`  
  
    -   UI bağlamında kimlikleri ya da komutları, menüleri ve araç çubuklarını görünürlüğünü kontrol CmdUIGuids  
  
    -   Etkin pencereyi, belge ve geri alma yöneticisi gibi şu anda etkin öğeleri  
  
    -   Dynamic Help sürücü kullanıcı bağlamı öznitelikleri  
  
 Kabuk yüklü VSPackages ve geçerli Hizmetleri arasındaki iletişim de aracılık. Kabuk çekirdek özelliklerini destekler ve tümleşik tüm VSPackages için kullanılabilir duruma getirir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Bu çekirdek özellikler aşağıdaki öğeleri içerir:  
  
-   **Hakkında** iletişim kutusu ve giriş ekranı  
  
-   **Yeni ve varolan öğeyi ekle ekleme** iletişim kutuları  
  
-   **Sınıf Görünümü** penceresi ve **Nesne Tarayıcısı**  
  
-   **Başvuruları** iletişim kutusu  
  
-   **Belge Anahattı** penceresi  
  
-   **Dinamik Yardım** penceresi  
  
-   **Bul** ve **Değiştir**  
  
-   **Projeyi açın** ve **açık dosya** iletişim kutuları **yeni** menüsü  
  
-   **Seçenekler** iletişim kutusundaki **Araçları** menüsü  
  
-   **Özellikler** penceresi  
  
-   **Çözüm Gezgini**  
  
-   **Görev listesi** penceresi  
  
-   **Araç Kutusu**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>   
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>   
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>   
 [VSPackage’lar](../../extensibility/internals/vspackages.md)