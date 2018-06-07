---
title: Mevcut proje ve öğe şablonları Visual Studio güncelleştirme
ms.date: 01/02/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- item templates, updating
- Visual Studio templates, updating
- project templates, updating
- updating templates [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: ddc360e6146678730d1844e4762ac3f6112a97d3
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34572572"
---
# <a name="how-to-update-existing-templates"></a>Nasıl yapılır: varolan şablonları güncelleme

Bir şablon oluşturun ve içine dosyaları sıkıştırın sonra bir *.zip* dosyası şablonu değiştirmek isteyebilirsiniz. Şablon dosyaları el ile değiştirerek veya şablonu temel alan bir projeye ait yeni bir şablon vererek bunu yapabilirsiniz.

## <a name="using-the-export-template-wizard-to-update-an-existing-project-template"></a>Var olan bir proje şablonu güncelleştirmek için şablonu Dışarı Aktarma Sihirbazı'nı kullanarak

Visual Studio sağlayan bir **şablonu Dışarı Aktarma Sihirbazı** mevcut bir şablonu güncellemek için kullanılabilir:

1. Açık **yeni proje** seçerek iletişim kutusu **dosya** > **yeni** > **proje**.

1. Güncelleştirme, bir ad ve projenizin konumunu girin veya seçmek için istediğiniz şablonu seçin **Tamam**.

1. Visual Studio Proje değiştirin.

1. Üzerinde **proje** menüsünde seçin **şablonu dışarı aktar**.

    **Şablonu Dışarı Aktarma Sihirbazı** açar.

1. Şablon olarak dışarı aktarmak için sihirbazdaki yönergeleri izleyerek bir *.zip* dosyası.

1. (İsteğe bağlı) Şablona eklemek için **yeni proje** iletişim kutusunda, yerine *.zip* aşağıdaki dizinde dosya: *%USERPROFILE%\Documents\Visual Studio \<sürüm\>\Templates\ProjectTemplates*. Seçeneğini seçmediyseniz, bu adımı gerçekleştirmeniz gerekir **otomatik olarak şablon Visual Studio'ya içeri** içinde **şablonu Dışarı Aktarma Sihirbazı**.

1. Eski şablonu silmek *.zip* dosyası.

## <a name="manually-update-an-existing-template"></a>Var olan bir şablonu el ile güncelleştirme

Var olan bir şablonunu kullanmadan güncelleştirebilirsiniz **şablonu Dışarı Aktarma Sihirbazı**, sıkıştırılmış dosyalarda değiştirerek *.zip* dosyası.

### <a name="to-manually-update-an-existing-template"></a>Var olan bir şablonu el ile güncelleştirmek için

1. Bulun *.zip* şablonu içeren dosya. Kullanıcı proje şablonları adresindedir *%USERPROFILE%\Documents\Visual Studio \<sürüm\>\Templates\ProjectTemplates*.

1. Extract *.zip* dosyası.

1. Değiştirin veya geçerli şablon dosyaları silin veya yeni dosyalar şablonuna ekleyin.

1. Açma, değiştirme ve kaydetme *.vstemplate* güncelleştirilmiş davranışı ya da yeni dosyaları işlemek için XML dosyası.

    Hakkında daha fazla bilgi için *.vstemplate* şeması, bkz: [Visual Studio Şablon Şeması Başvurusu (genişletilebilirlik)](../extensibility/visual-studio-template-schema-reference.md). Kaynak dosyalarda Parametreleştirme hakkında daha fazla bilgi için bkz: [şablon parametreleri](../ide/template-parameters.md).

1. Şablonunuzda ve sağ tıklatın veya bağlam menüsünde dosyaları seçin ve **göndermek** > **sıkıştırılmış (daraltılmış) klasör**.

    Seçtiğiniz dosyalar halinde sıkıştırılmış bir *.zip* dosyası.

1. Yeni put *.zip* eski ile aynı dizinde dosya *.zip* dosyası.

1. Ayıklanan şablon dosyalarını ve eski şablonu silmek *.zip* dosyası.

## <a name="see-also"></a>Ayrıca bkz.

- [Şablonları özelleştirme](../ide/customizing-project-and-item-templates.md)
- [Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)
- [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)
- [Şablon parametreleri](../ide/template-parameters.md)