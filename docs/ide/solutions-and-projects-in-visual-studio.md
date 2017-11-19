---
title: "Çözüm ve Visual Studio projeleri | Microsoft Docs"
ms.custom: 
ms.date: 10/5/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.addnewsolutionitem
- vs.environment.projects
- vs.openproject
- vs.addnewitem
- vs.addexistingitem
- VS.SolutionExplorer
- vs.newproject
- vs.addexistingsolutionitem
- vs.environment.solutions
- VS.SolutionExplorer.Solutions
helpviewer_keywords:
- solution items, folder in Solution Explorer
- solution items, shared
- solutions [Visual Studio]
- project items [Visual Studio], about project items
- solutions [Visual Studio], designing
- projects [Visual Studio]
- solutions [Visual Studio], projects and
- projects [Visual Studio], setting up
ms.assetid: aeaf56cb-c2dd-47f6-b012-23b84b7a7254
caps.latest.revision: "35"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ca3094b3bfe35381236798164fa18e58304bae3f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="solutions-and-projects-in-visual-studio"></a>Visual Studio’da Çözümler ve Projeler
Bir uygulama, Web sitesi, eklenti, vs. oluşturduğunuzda ile başlamanız Visual Studio'da bir *proje*. Bir mantıksal anlamda tüm kaynak kodu dosyaları, simgeler, görüntüler, veri dosyaları ve başka bir şey bir yürütülebilir program veya web sitesi derlenecek, aksi takdirde derleme gerçekleştirmek için gereken bir proje içerir. Bir proje ayrıca tüm derleyici ayarları ve çeşitli hizmetler veya programınız iletişim kuracağı bileşenleri tarafından gerekebilecek diğer yapılandırma dosyalarını içerir.  

> [!NOTE]
>  Çözümleri veya projeler için istemiyorsanız kullanmanız gerekmez. Yalnızca, Visual Studio'ya dosyaları açmak ve kodunuzu düzenlemeye başlayın. Bkz: [projeleri veya çözümler olmadan kod Visual Studio geliştirme](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md) daha fazla bilgi için.  

Bir proje dosyası (.vbproj .csproj, .vcxproj) projedeki tüm öğelerine sanal klasör hiyerarşisi yolları birlikte tanımlayan bir XML dosyasıdır. Ayrıca, yapılandırma ayarlarını içerir. Proje dosyası içeriğini görmek için Çözüm Gezgini'nde proje adına seçin sonra kullanabilirsiniz seçin **projeyi** (sağ tıklatma) bağlam menüsünden. Ardından bağlam menüsünden yeniden açın ve seçin **Düzenle \<projectname\>**.  

Visual Studio Proje dosyası proje içeriği ve ayarları görüntülemek için Çözüm Gezgini tarafından kullanılır. Projenizi derleme yaparken MSBuild altyapısı yürütülebilir dosyayı oluşturmak için proje dosyasını kullanır. Çıkış diğer tür üretmek için projeleri özelleştirebilirsiniz.  

Proje, mantıksal bir fikir ve dosya sistemi içinde bulunan bir *çözüm*, hangi içerebilir veya projeleri, yapı bilgileri, Visual Studio penceresi ayarlarını ve olmayan çeşitli dosyaları ile birlikte ilgili daha fazla belirli bir projeyle ilişkili. Bir çözümü kendi benzersiz biçiminde bir metin dosyasını (.sln) tarafından açıklanan; Bu genellikle el ile düzenlenmesi için tasarlanmamıştır.  

Bir çözüm ilişkili bir sahip *.suo* ayarları, tercihleri ve projede çalıştığı her bir kullanıcı için yapılandırma bilgilerini depolayan dosya.  

 Aşağıdaki diyagramda, projeler ve çözümler ve mantıksal olarak içerdikleri öğeler arasındaki ilişkiyi gösterir.  

 ![Visual Studio projeler ve çözümler](../ide/media/vside-project-diagram.png)  

## <a name="creating-new-projects"></a>Yeni proje oluşturma  
 Önceden oluşturulan kod dosyaları, yapılandırma dosyaları, varlıkları ve belirli bir uygulama veya Web sitesi belirli bir tür oluşturma başlamanıza yardımcı ayarları birtakım temel oluşan bir proje şablonu başlamak için yeni bir proje oluşturmak için en kolay yolu olan programlama dili. Uygulamasında gördüğünüz bu şablonlarıdır **yeni proje** veya **yeni Web sitesi** seçtiğinizde iletişim kutusu **dosya**, **yeni**,  **Proje** veya **dosya**, **yeni**, **Web sitesi**. Daha fazla bilgi için bkz: [oluşturma çözümler ve projeler](../ide/creating-solutions-and-projects.md).  

Özel proje ve öğe şablonları oluşturabilirsiniz. Daha fazla bilgi için bkz: [oluşturma proje ve öğe şablonlarını](../ide/creating-project-and-item-templates.md).  

## <a name="managing-projects-in-solution-explorer"></a>Çözüm Gezgini'nde projeleri yönetme  
 Yeni bir proje oluşturduğunuzda, kullandığınız **Çözüm Gezgini** projeler ve çözümler ve bunların ilişkili öğeleri görüntülemek ve yönetmek için. Aşağıdaki çizimde Solution Explorer iki proje içeren bir C# çözümü ile gösterilir.  

 ![Çözüm Gezgini](../ide/media/vs2015_solution_explorer.png "vs2015_solution_explorer")  

## <a name="in-this-section"></a>Bu Bölümde  

-   [Çözümler ve projeler oluşturma](../ide/creating-solutions-and-projects.md)  

-   [Proje öğeler ekleme ve kaldırma](../ide/adding-and-removing-project-items.md)  

-   [Proje ve çözüm özelliklerini yönetme](../ide/managing-project-and-solution-properties.md)  

-   [Bir projedeki başvuruları yönetme](../ide/managing-references-in-a-project.md)  

-   [Uygulama özellikleri](../ide/application-properties.md)  

-   [Yönetme derleme ve bildirim imzalamayı](../ide/managing-assembly-and-manifest-signing.md)  

-   [Nasıl yapılır: bir uygulama Iicon (Visual Basic, C#) belirtin](../ide/how-to-specify-an-application-icon-visual-basic-csharp.md)  

-   [Belirli bir .NET Framework sürümünü hedefleme](../ide/targeting-a-specific-dotnet-framework-version.md)  

-   [Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio IDE](../ide/visual-studio-ide.md)
