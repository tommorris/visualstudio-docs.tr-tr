---
title: "Denetim listesi: Yeni proje türleri oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio SDK], creating new types
- project types, checklist for creating
ms.assetid: 29eb9c3b-1933-4741-aa85-65a33f0825ba
caps.latest.revision: "23"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 06b6dc2fab4158f36126b6509909dd0db6fd7125
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="checklist-creating-new-project-types"></a>Denetim listesi: Yeni proje türleri oluşturma
Yeni bir proje türü oluşturmak için çeşitli görevleri tamamlamanız gerekir. Aşağıdaki denetim listesinde, bu görevleri için bir kılavuz sağlar.  
  
1.  Yeni proje türü için işlevsellik tasarlayın. Daha fazla bilgi için bkz: [proje türü tasarım kararları](../../extensibility/internals/project-type-design-decisions.md).  
  
2.  Hangi düzenleyicileri kod ve diğer proje öğeleri için kullanılan belirler. Temel veya standart düzenleyicileri kullanabilirsiniz veya oluşturup projeye özgü düzenleyicilerini kullanın. Daha fazla bilgi için bkz: [özel düzenleyici oluşturma ve tasarımcıları](../../extensibility/creating-custom-editors-and-designers.md) ve [nasıl yapılır: açık projeye özgü düzenleyicileri](../../extensibility/how-to-open-project-specific-editors.md).  
  
3.  Proje öğeleri olacaktır katılım düzeyini belirlemek **sınıf görünümü** ve **Nesne Tarayıcısı**. Daha fazla bilgi için bkz: [destekleyen simgenin tarama araçları](../../extensibility/internals/supporting-symbol-browsing-tools.md).  
  
4.  Proje ve proje öğeleri için daha önce yaptığınız tasarım kararlarına göre yeni sınıflar türetilir.  
  
5.  Aşağıdaki proje türü bileşenleri için kodu yazın:  
  
    -   Yeni proje oluşturma ve mevcut projeleri açma yönetmek için proje üreteci. Daha fazla bilgi için bkz: [oluşturma proje örnekleri tarafından kullanarak proje Fabrikalarını](../../extensibility/internals/creating-project-instances-by-using-project-factories.md).  
  
    -   Proje hiyerarşisi ve komut işleme. Daha fazla bilgi için bkz: [yapı içinde değil: Proje türü (C++) uygulamak için HierUtil7 proje sınıflarını kullanarak](http://msdn.microsoft.com/en-us/a5c16a09-94a2-46ef-87b5-35b815e2f346), [proje modeli öğeleri](../../extensibility/internals/elements-of-a-project-model.md), [proje modeli çekirdek bileşenleri](../../extensibility/internals/project-model-core-components.md)ve [MenuCommands Vs. OleMenuCommands](../../extensibility/menucommands-vs-olemenucommands.md).  
  
    -   Proje öğeleri Yönetimi projenize ekleme de dahil olmak üzere, **yeni proje** iletişim kutusu. Daha fazla bilgi için bkz: [ekleme proje ve proje öğesi şablonları](../../extensibility/internals/adding-project-and-project-item-templates.md) ve [kaydetme proje ve öğe şablonlarını](../../extensibility/internals/registering-project-and-item-templates.md).  
  
    -   Proje durumu ve bireysel öğeleri kalıcılığı. Daha fazla bilgi için bkz: [açma ve kaydetme proje öğeleri](../../extensibility/internals/opening-and-saving-project-items.md). Çözüm bilgileri kalıcılığını bkz [çözümleri](../../extensibility/internals/solutions.md).  
  
    -   Özellikler penceresini görüntülemek için yapılandırma bağımsız özellikleri. Daha fazla bilgi için bkz: [genişletme özellikleri](../../extensibility/internals/extending-properties.md).  
  
    -   Yapılandırmaya bağlı özellikleri göstermek için özellik sayfalarında uygulandığı gibi yapılandırma özellikleri proje. Daha fazla bilgi için bkz: [yönetme yapılandırma seçenekleri](../../extensibility/internals/managing-configuration-options.md).  
  
    -   Dağıtım çıktıların numaralandırma. Daha fazla bilgi için bkz: [çıktı için proje yapılandırması](../../extensibility/internals/project-configuration-for-output.md).  
  
    -   Proje başlangıç Hizmetleri. Daha fazla bilgi için bkz: [proje modeli öğeleri](../../extensibility/internals/elements-of-a-project-model.md) ve [proje modeli çekirdek bileşenleri](../../extensibility/internals/project-model-core-components.md).  
  
    -   Nesneleri veya türetilmiş sınıfları `IDispatch`, otomasyon için kullanılabilir.  
  
    -   XML komutu tablosu (.vsct) dosyaları. Daha fazla bilgi için bkz: [Visual Studio komut tablosu (. Vsct) dosyaları](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md).  
  
6.  Test, hata ayıklama ve başlatma proje türü.  
  
7.  Projenizde görüntülemek **proje** sekmesinde **Başvuru Ekle** ayarlayarak iletişim kutusu `VARIANT_TRUE` değeri olarak `VSHPROPID_ShowProjInSolutionPage`. Daha fazla bilgi için bkz. <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A>.  
  
8.  VSPackages yüklemek için Microsoft Installer (.msi) dosyası oluşturun. Daha fazla bilgi için bkz: [yükleme VSPackages ile Windows Installer](../../extensibility/internals/installing-vspackages-with-windows-installer.md), [proje türü kaydetme](../../extensibility/internals/registering-a-project-type.md), ve [VSPackages](../../extensibility/internals/vspackages.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da hiyerarşileri](../../extensibility/internals/hierarchies-in-visual-studio.md)   
 [Proje türleri oluşturma zamanı](../../extensibility/internals/when-to-create-project-types.md)   
 [Proje türleri oluşturma](../../extensibility/internals/creating-project-types.md)