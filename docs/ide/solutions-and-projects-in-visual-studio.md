---
title: Çözümler ve projeler Visual Studio'da
ms.date: 10/05/2017
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: 8dc94838423cea7eeab8cef6357267609394352b
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="solutions-and-projects-in-visual-studio"></a>Çözümler ve projeler Visual Studio'da

## <a name="projects"></a>Projeler

Bir uygulama, Web sitesi, eklenti, vs. oluşturduğunuzda ile başlamanız Visual Studio'da bir *proje*. Bir mantıksal anlamda bir proje tüm kaynak kodu dosyaları, simgeler, görüntüler, veri dosyalarını, yürütülebilir dosya, kitaplığı veya Web sitesi derlenmiş vb. içerir. Bir proje ayrıca derleyici ayarları ve çeşitli hizmetler veya programınız kurduğu bileşenleri tarafından gerekebilecek diğer yapılandırma dosyalarını içerir.

> [!NOTE]
> Çözümleri veya projeleri düzenlemek, yapı ve kodda hata ayıklama için Visual Studio'da kullanmak zorunda değilsiniz. Yalnızca Visual Studio, kaynak dosyalarını içeren klasörü açın ve düzenlemeye başlayın. Daha fazla bilgi için bkz: [projeleri veya çözümler olmadan kod Visual Studio geliştirme](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md).

Bir proje uzantılı bir XML dosyasında aşağıdaki gibi tanımlanır *.vbproj*, *.csproj*, veya *.vcxproj*. Bu dosya, bir sanal klasör hiyerarşisini ve projedeki tüm öğeleri yollara içerir. Ayrıca, yapılandırma ayarlarını içerir.

> [!TIP]
> Visual Studio Proje dosyasında içeriğini bakmak için önce projeyi Proje adı seçerek unload **Çözüm Gezgini** ve seçme **Unload proje** bağlam ya da sağ tıklatma menüsünden. Ardından bağlam menüsünden yeniden açın ve seçin **Düzenle \<projectname\>**.

Visual Studio Proje dosyası tarafından kullanılan **Çözüm Gezgini** proje içeriği ve ayarları görüntülemek için. Projenizi derleme yaparken MSBuild altyapısı yürütülebilir dosyayı oluşturmak için proje dosyasını kullanır. Çıkış diğer tür üretmek için projeleri özelleştirebilirsiniz.

## <a name="solutions"></a>Çözümleri

Bir proje kapsamında yer alan bir *çözüm*. Bir veya daha fazla ilgili projeleri, yapı bilgileri, Visual Studio penceresi ayarlarını ve belirli bir projeyle ilişkili olmayan tüm çeşitli dosyalar ile birlikte bir çözüm içerir. Bir çözümü bir metin dosyası tarafından tanımlanan (uzantısı *.sln*) kendi benzersiz biçimde; bu el ile düzenlenmesi kullanılmaya yönelik değildir.

Bir çözüm ilişkili bir sahip *.suo* ayarları, tercihleri ve projede çalıştığı her bir kullanıcı için yapılandırma bilgilerini depolayan dosya.

## <a name="create-new-projects"></a>Yeni projeler oluştur

Belirli bir tür uygulama veya Web sitesi için bir proje şablondan yeni bir proje oluşturmak için en kolay yolu başlatmaktır. Bir proje şablonu, önceden oluşturulan kod dosyaları, yapılandırma dosyaları, varlıkları ve ayarları temel kümesinden oluşur. Uygulamasında gördüğünüz bu şablonlarıdır **yeni proje** veya **yeni Web sitesi** seçtiğinizde iletişim kutusu **dosya** > **yeni**  >  **Proje** veya **dosya** > **yeni** > **Web sitesi**. Daha fazla bilgi için bkz: [çözümler ve projeler oluşturma](../ide/creating-solutions-and-projects.md).

Özel proje ve öğe şablonları oluşturabilirsiniz. Daha fazla bilgi için bkz: [proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md).

## <a name="manage-projects-in-solution-explorer"></a>Çözüm Gezgini'nde projeleri yönetme

Yeni bir proje oluşturduğunuzda, kullanabileceğiniz **Çözüm Gezgini** proje ve çözüm ve bunların ilişkili öğeleri görüntülemek ve yönetmek için. Aşağıdaki çizimde gösterildiği **Çözüm Gezgini** Çözümle iki proje içeren bir C#.

![Çözüm Gezgini](../ide/media/vs2015_solution_explorer.png "vs2015_solution_explorer")

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio IDE](../ide/visual-studio-ide.md)