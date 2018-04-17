---
title: Çözüm ve Visual Studio projeleri | Microsoft Docs
ms.custom: ''
ms.date: 10/5/2017
ms.technology: vs-ide-general
ms.topic: conceptual
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
- solution items [Visual Studio]
- solutions [Visual Studio]
- project items [Visual Studio]
- solutions [Visual Studio], designing
- projects [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 11441c826a316d995e75f2b6c79232f19985c17b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="solutions-and-projects-in-visual-studio"></a>Çözümler ve projeler Visual Studio'da

## <a name="projects"></a>Projeler

Bir uygulama, Web sitesi, eklenti, vs. oluşturduğunuzda ile başlamanız Visual Studio'da bir *proje*. Bir mantıksal anlamda bir proje tüm kaynak kodu dosyaları, simgeler, görüntüler, veri dosyalarını, yürütülebilir dosya, kitaplığı veya Web sitesi derlenmiş vb. içerir. Bir proje ayrıca derleyici ayarları ve çeşitli hizmetler veya programınız kurduğu bileşenleri tarafından gerekebilecek diğer yapılandırma dosyalarını içerir.

> [!NOTE]
> Çözümleri veya projeleri düzenlemek, yapı ve kodda hata ayıklama için Visual Studio'da kullanmak zorunda değilsiniz. Yalnızca Visual Studio, kaynak dosyalarını içeren klasörü açın ve düzenlemeye başlayın. Bkz: [projeleri veya çözümler olmadan kod Visual Studio geliştirme](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md) daha fazla bilgi için.

Bir proje .vbproj, .csproj veya .vcxproj gibi uzantılı bir XML dosyasında tanımlanır. Bu dosya, bir sanal klasör hiyerarşisini ve projedeki tüm öğeleri yollara içerir. Ayrıca, yapılandırma ayarlarını içerir.

> [!TIP]
> Visual Studio Proje dosyasında içeriğini bakmak için ilk proje Çözüm Gezgini'nde proje adına ve seçerek unload **Unload proje** bağlam ya da sağ tıklatma menüsünden. Ardından bağlam menüsünden yeniden açın ve seçin **Düzenle \<projectname\>**.

Visual Studio Proje dosyası proje içeriği ve ayarları görüntülemek için Çözüm Gezgini tarafından kullanılır. Projenizi derleme yaparken MSBuild altyapısı yürütülebilir dosyayı oluşturmak için proje dosyasını kullanır. Çıkış diğer tür üretmek için projeleri özelleştirebilirsiniz.

## <a name="solutions"></a>Çözümleri

Bir proje kapsamında yer alan bir *çözüm*. Bir veya daha fazla ilgili projeleri, yapı bilgileri, Visual Studio penceresi ayarlarını ve belirli bir projeyle ilişkili olmayan tüm çeşitli dosyalar ile birlikte bir çözüm içerir. Bir çözümü kendi benzersiz biçimde metin dosyasını (.sln uzantılı) tarafından açıklanan; Bu genellikle el ile düzenlenmesi için tasarlanmamıştır.

Bir çözüm ilişkili bir sahip *.suo* ayarları, tercihleri ve projede çalıştığı her bir kullanıcı için yapılandırma bilgilerini depolayan dosya.

## <a name="creating-new-projects"></a>Yeni proje oluşturma

Belirli bir tür uygulama veya Web sitesi için bir proje şablondan yeni bir proje oluşturmak için en kolay yolu başlatmaktır. Bir proje şablonu, önceden oluşturulan kod dosyaları, yapılandırma dosyaları, varlıkları ve ayarları temel kümesinden oluşur. Uygulamasında gördüğünüz bu şablonlarıdır **yeni proje** veya **yeni Web sitesi** seçtiğinizde iletişim kutusu **dosya**, **yeni**,  **Proje** veya **dosya**, **yeni**, **Web sitesi**. Daha fazla bilgi için bkz: [oluşturma çözümler ve projeler](../ide/creating-solutions-and-projects.md).

Özel proje ve öğe şablonları oluşturabilirsiniz. Daha fazla bilgi için bkz: [oluşturma proje ve öğe şablonlarını](../ide/creating-project-and-item-templates.md).

## <a name="managing-projects-in-solution-explorer"></a>Çözüm Gezgini'nde projeleri yönetme

Yeni bir proje oluşturduğunuzda, kullanabileceğiniz **Çözüm Gezgini** proje ve çözüm ve bunların ilişkili öğeleri görüntülemek ve yönetmek için. Aşağıdaki çizimde Solution Explorer iki proje içeren bir C# çözümü ile gösterilir.

![Çözüm Gezgini](../ide/media/vs2015_solution_explorer.png "vs2015_solution_explorer")

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio IDE](../ide/visual-studio-ide.md)
