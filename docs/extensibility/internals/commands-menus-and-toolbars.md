---
title: Komutları, menüleri ve araç çubuklarını | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- menus [Visual Studio SDK], commands
- commands [Visual Studio]
- toolbars [Visual Studio], commands
ms.assetid: 07b4ed90-dbbd-40df-b6c9-8395fd6f2ab6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6f27bfc7d679d972482e6b910f40a0ecf74d9d6a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31131982"
---
# <a name="commands-menus-and-toolbars"></a>Komutları, menüleri ve araç çubukları
Menüleri ve araç çubuklarını şekilde, kullanıcılar, VSPackage komutlarda erişimi var. Belge yazdırma, bir görünümü yenileme veya yeni bir dosya oluşturmak gibi görevleri gerçekleştirmek işlevleri komutlardır. Menüleri ve araç çubuklarını komutlarınızı sunmak için uygun grafik yollarıdır. Genellikle, ilgili komutları birlikte aynı menü veya araç çubuğunda kümelenir.  
  
-   Menüleri, genellikle bir satırda tümleşik geliştirme ortamı (IDE) veya bir araç penceresi üstündeki kümelenmiş Tek sözcüklü dizeleri olarak görüntülenir. Menüler da sağ tıklatma olay sonucu olarak görüntülenebilir ve bu bağlamda kısayol menüleri olarak adlandırılır. Tıklatıldığında, bir veya daha fazla komut görüntülenecek menüleri genişletin. Tıklatıldığında, komutları, görevleri gerçekleştirmek ya da ek komutlar içeren alt menüler Başlat. Bazı iyi bilinen menü dosya, düzenleme, Görünüm ve pencere adlardır. Daha fazla bilgi için bkz: [genişletme menüleri ve komutları](../../extensibility/extending-menus-and-commands.md).  
  
-   Araç çubukları genellikle satırları düğmeleri ve birleşik giriş kutuları, liste kutuları, metin kutuları ve menü denetleyicileri gibi diğer denetimlerin edilir. Tüm araç çubuğu denetimleri komutları ile ilişkilendirilir. Araç çubuğu düğmesini tıklattığınızda, ilişkili komutu etkinleştirilir. Araç çubuğu düğmeleri genellikle bir yazdırma komutu için bir yazıcı gibi temel komutları önermek simgeler sahiptir. Aşağı açılan liste denetiminde listedeki her öğeye farklı komutu ile ilişkilidir. Menü denetimi bir tarafında bir araç çubuğu düğmesi bulunur ve diğer taraftaki tıklatıldığında ek komutları görüntüleyen bir aşağı ok olan bir karma denetleyicisidir. Daha fazla bilgi için bkz: [menü denetleyicisi araç çubuğuna ekleme](../../extensibility/adding-a-menu-controller-to-a-toolbar.md).  
  
-   Bir komut oluşturduğunuzda, aynı zamanda bir olay işleyicisi için oluşturmanız gerekir. Olay işleyicisi belirler komutu görünür ya da etkin olduğunda, metin değiştirme olanak tanır ve komut uygun şekilde yanıt verdiğini sağlar ("etkinleştirildiğinde rotaları"). Çoğu durumda, IDE kullanarak komutları işler <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> arabirimi. İçindeki komutlar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] rota yerel seçimine göre ve genel seçimine göre en dıştaki bağlamı için devam en içteki komut bağlamı başlayarak hiyerarşik bir biçimde. Ana menüsüne eklenen komutlar komut dosyası için hemen kullanılabilir. Daha fazla bilgi için bkz: [MenuCommands Vs. OleMenuCommands](../../extensibility/menucommands-vs-olemenucommands.md) ve [seçimi bağlam nesneleri](../../extensibility/internals/selection-context-objects.md).  
  
 Yeni menüleri ve araç çubuklarını tanımlamak için bir Visual Studio komut tablosu (.vsct) dosyasında açıklamak gerekir. Visual Studio Paketi şablonu hangi komutların, araç çubukları ve şablonda seçili düzenleyicileri desteklemek için gerekli öğeler yanı sıra, bu dosyaya oluşturur. Burada açıklanan xml şeması kullanarak kendi .vsct dosyanızı alternatif olarak, yazabilirsiniz: [VSCT XML Şeması Başvurusu](../../extensibility/vsct-xml-schema-reference.md).  
  
 .Vsct dosyaları ile çalışma hakkında daha fazla bilgi için bkz: [Visual Studio komut tablosu (. Vsct) dosyaları](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md).  
  
 Bu bölümdeki konular, komutları, menüleri ve araç çubuklarını VSPackages içinde nasıl çalıştığını açıklanır.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [VSPackage’ların Kullanıcı Arabirimi Öğeleri Eklemesi](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)  
 Komut tablo biçiminde belirtimi ayrıntılı bir açıklaması.  
  
 [Visual Studio Komut Tablosu (.Vsct) Dosyaları](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)  
 Bir XML tabanlı sözdizimi ve derleyici komut tablolar için açıklar.  
  
 [Varsayılan Komut, Grup ve Araç Çubuğu Yerleşimi](../../extensibility/internals/default-command-group-and-toolbar-placement.md)  
 Önceden tanımlanmış komutları, gruplar, menüleri ve araç çubuklarını açıklar.  
  
 [IDE Tanımlı Komutlar, Menüler ve Gruplar](../../extensibility/internals/ide-defined-commands-menus-and-groups.md)  
 Önceden tanımlanmış menüleri, komutları ve komut grupları tarafından kullanılmak üzere kullanılabilir belirtir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  
  
 [Komut Tasarımı](../../extensibility/internals/command-design.md)  
 Komutları tasarım açıklanmaktadır.  
  
 [Menü ve Araç Çubuğu Komutlarını En İyi Duruma Getirme](../../extensibility/internals/optimizing-menu-and-toolbar-commands.md)  
 Yönergeler için komutları sağlar.  
  
 [Komutları Kullanılabilir Yapma](../../extensibility/internals/making-commands-available.md)  
 Visual Studio komutları kullanılabilir hale getirmek açıklanmaktadır.  
  
 [Birlikte Çalışma Bütünleştirilmiş Kodları Kullanan Komutlar ve Menüler](../../extensibility/internals/commands-and-menus-that-use-interop-assemblies.md)  
 Birlikte çalışma derlemeleri kullanma komutları uygulamak açıklanmaktadır.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [VSPackage’larda Komut Yönlendirme](../../extensibility/internals/command-routing-in-vspackages.md)  
 Komut içinde VSPackages yönlendirme açıklanmaktadır.