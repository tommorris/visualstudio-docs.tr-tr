---
title: "Özel proje ve öğe şablonları oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 586da5dc-f678-402b-afd0-0332959fd7a6
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 3677dd4ad6177f4085c907d1fceaaf37978bf769
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2018
---
# <a name="creating-custom-project-and-item-templates"></a>Özel proje ve öğe şablonları oluşturma

Visual Studio SDK'sı özel Proje şablonu oluşturup özel öğesi Şablonu proje şablonları içerir. Bu şablonlar bazı ortak parametresi değiştirmeleri içerir ve ZIP dosyaları olarak oluşturun. Değil bunlar otomatik olarak dağıtılır ve deneysel örneğinde kullanılabilir değildir. Kullanıcı şablonu dizini oluşturulan zip dosyası kopyalamanız gerekir.
  
Şablon oluşturma şablonları büyük uzantılarını şablonları Ekle olanak tanır. Bu sürüm denetimi kaynak dosyalarda uygulamak ve şablon projelerini grubu bir VSIX paketi oluşturmanıza olanak sağlar.  
  
NuGet paketlerini yüklemek için bir şablon da yapılandırabilirsiniz. Daha fazla bilgi için bkz: [Visual Studio şablonları NuGet paketlerine](/nuget/visual-studio-extensibility/visual-studio-templates).

Temel şablon oluşturma senaryoları için kullanmanız gereken **şablonu dışarı aktar** Sihirbazı'nı, ama sıkıştırılmış bir dosya çıkarır. Temel şablonu oluşturma hakkında daha fazla bilgi için bkz: [oluşturma proje ve öğe şablonlarını](../ide/creating-project-and-item-templates.md).  

> [!NOTE]
> Visual Studio 2017 içinde başlayarak, özel Proje ve öğe şablonları için tarama artık gerçekleştirilir. Bunun yerine, uzantı bu şablonları yükleme konumunu tanımlayan şablon bildirim dosyası sağlamanız gerekir. Visual Studio 2017 VSIX uzantılarınızın güncelleştirmek için kullanabilirsiniz. Uzantınızı bir MSI kullanarak dağıtırsanız, şablon bildirim dosyalarını el ile oluşturmanız gerekir. Daha fazla bilgi için bkz: [yükseltme özel Proje ve öğe şablonları için Visual Studio 2017](../extensibility/upgrading-custom-project-and-item-templates-for-visual-studio-2017.md). Şablon bildirim şeması belgelenen [Visual Studio şablon bildirim şema başvurusu](../extensibility/visual-studio-template-manifest-schema-reference.md).

## <a name="creating-a-project-template"></a>Proje şablonu oluşturma  
  
1.  Bir proje şablonu projesi oluşturun. Proje şablonu bulabilirsiniz **yeni proje** iletişim kutusunda, Visual Basic veya Visual C# **genişletilebilirlik** klasör.  
  
     Bir sınıf dosyası, bir simge, .vstemplate dosyası, ProjectTemplate.vbproj veya ProjectTemplate.csproj adlı bir düzenlenebilir proje dosyası ve diğer proje türleri tarafından böyle bir resources.resx dosya, bir AssemblyInfo genellikle oluşturulan bazı dosyaları şablon oluşturur Dosya ve .settings dosya. Her kod dosyası, uygun olan yerlerde ortak parametresi değiştirmeleri içerir.  
  
2.  Ekleme ve projeniz için gereken proje öğeleri kaldırın. Düzenlenebilir proje dosyası, AssemblyInfo dosyası ya da .vstemplate dosyasına kaldırmayın.  
  
3.  .Vstemplate dosya ekleme ve silme işlemleri yansıtacak şekilde güncelleştirin. [Proje](../extensibility/project-element-visual-studio-templates.md) öğesi içermelidir bir [ProjectItem](../extensibility/projectitem-element-visual-studio-item-templates.md) şablonda eklenecek her bir dosyanın öğesi.  
  
4.  Kod dosyaları ve diğer kullanıcı dönük içeriği değiştirebilir ve uygun parametresi değiştirmeleri ekleyebilirsiniz.  
  
5.  Oluşturulan içeriği gerektiği gibi değiştirin.  
  
6.  Projeyi oluşturun.  
  
     Visual Studio şablonunuzu içeren bir .zip dosyası oluşturur. Değil dağıtılır ve deneysel örneğinde mevcut değil.  
  
## <a name="creating-an-item-template"></a>Bir öğe şablonu oluşturma  
  
1.  Bir öğe şablonu projesi oluşturun.  
  
     Şablon bir sınıf dosyası, bir simge, .vstemplate dosyası ve bir AssemblyInfo dosyası oluşturur. Sınıf dosyası bazı ortak parametresi değiştirmeleri içerir.  
  
2.  Ekleme ve projeniz için gereken proje öğeleri kaldırın.  
  
3.  .Vstemplate dosya ekleme ve silme işlemleri yansıtacak şekilde güncelleştirin. [Proje](../extensibility/project-element-visual-studio-templates.md) öğesi içermelidir bir [ProjectItem](../extensibility/projectitem-element-visual-studio-item-templates.md) şablonda eklenecek her bir dosyanın öğesi.  
  
4.  Kod dosyaları ve diğer kullanıcı dönük içeriği değiştirebilir ve uygun parametresi değiştirmeleri ekleyebilirsiniz.  
  
5.  Oluşturulan içeriği gerektiği gibi değiştirin.  
  
6.  Projeyi oluşturun.  
  
     Visual Studio, şablonu içeren sıkıştırılmış bir dosya oluşturur. Değil dağıtılır ve deneysel örneğinde mevcut değil.  
  
## <a name="deployment"></a>Dağıtım  
  
#### <a name="to-deploy-the-project-or-item-template"></a>Öğe veya proje şablonu dağıtmak için  
  
1.  VSIX projesi oluşturun. Daha fazla bilgi için bkz: [VSIX proje şablonu](../extensibility/vsix-project-template.md).  
  
2.  VSIX projesini başlangıç projesi olarak ayarlayın. İçinde **Çözüm Gezgini**, VSIX proje düğümüne sağ tıklatın ve seçin seçin **başlangıç projesi olarak ayarla**.  
  
3.  Proje şablonu proje VSIX proje bir varlık ayarlayın. .Vsixmanifest dosyasını açın. Git **varlıklar** sekmesinde **yeni**.  
  
    1.  Ayarlama **türü** alanı **Microsoft.VisualStudio.ProjectTemplate** veya **Microsoft.VisualStudio.ItemTemplate**.  
  
    2.  Kaynağı için **geçerli çözümdeki bir proje ile** seçeneğini ve ardından şablonunuzu içeren projesini seçin.  
  
4.  Çözümü derlemek ve F5 tuşuna basın. Deneysel örneği görüntülenir.  
  
5.  Bir proje şablonu projesi için listelenen, proje şablonu görmelisiniz **yeni proje** iletişim (**Dosya > Yeni > Proje**), Visual C# veya Visual Basic düğümü. Bir öğe şablonu projesi için Yeni Öğe Ekle iletişim kutusunda listelenen öğesi şablonunuzu görmeniz gerekir (içinde **Çözüm Gezgini**, proje düğümünü seçin ve tıklatın **Ekle / yeni öğe**).  
  
## <a name="see-also"></a>Ayrıca Bkz.

[Visual Studio şablon başvurusu](../ide/visual-studio-template-reference.md)  
[Visual Studio şablonları NuGet paketleri](/nuget/visual-studio-extensibility/visual-studio-templates)