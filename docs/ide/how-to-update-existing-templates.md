---
title: "Mevcut proje ve öğe şablonları Visual Studio güncelleştirme | Microsoft Docs"
ms.custom: 
ms.date: 01/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- item templates, updating
- Visual Studio templates, updating
- project templates, updating
- updating templates [Visual Studio]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9401f8a9a07f7098575ff267825982a03024e968
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2018
---
# <a name="how-to-update-existing-templates"></a>Nasıl yapılır: varolan şablonları güncelleme

Bir şablon oluşturmak ve bir .zip dosyasına dosyaları sıkıştırın sonra şablonu değiştirmek isteyebilirsiniz. Şablon dosyaları el ile değiştirerek veya şablonu temel alan bir projeye ait yeni bir şablon vererek bunu yapabilirsiniz.

## <a name="using-the-export-template-wizard-to-update-an-existing-project-template"></a>Var olan bir proje şablonu güncelleştirmek için şablonu Dışarı Aktarma Sihirbazı'nı kullanarak

Visual Studio sağlayan bir **şablonu Dışarı Aktarma Sihirbazı** mevcut bir şablonu güncellemek için kullanılabilir:

1. Açık **yeni proje** seçerek iletişim kutusu **dosya** > **yeni** > **proje**.

1. Güncelleştirme, bir ad ve projenizin konumunu girin veya seçmek için istediğiniz şablonu seçin **Tamam**.

1. Visual Studio Proje değiştirin.

1. Üzerinde **proje** menüsünde seçin **şablonu dışarı aktar...** .

    **Şablonu Dışarı Aktarma Sihirbazı** açar.

1. Şablonu bir .zip dosyası olarak dışarı aktarmak için sihirbazdaki yönergeleri izleyin.

1. (İsteğe bağlı) Şablona eklemek için **yeni proje** iletişim kutusunda, aşağıdaki dizinde .zip dosyasını yerleştirin: %USERPROFILE%\Documents\Visual Studio \<sürüm\>\Templates\ProjectTemplates. Seçeneğini seçmediyseniz, bu adımı gerçekleştirmeniz gerekir **otomatik olarak şablon Visual Studio'ya içeri** içinde **şablonu Dışarı Aktarma Sihirbazı**.

1. Eski şablon .zip dosyasını silin.

## <a name="manually-updating-an-existing-template"></a>Var olan bir şablonu el ile güncelleştirme

Var olan bir şablonunu kullanmadan güncelleştirebilirsiniz **şablonu Dışarı Aktarma Sihirbazı**, dosyaları sıkıştırılmış .zip dosyasını değiştirerek.

### <a name="to-manually-update-an-existing-template"></a>Var olan bir şablonu el ile güncelleştirmek için

1. Şablonu içeren .zip dosyasını bulun. Kullanıcı proje şablonları konumlandırıldığını Studio %USERPROFILE%\Documents\Visual genellikle \<sürüm\>\Templates\ProjectTemplates.

1. .Zip dosyasını ayıklayın.

1. Değiştirin veya geçerli şablon dosyaları silin veya yeni dosyalar şablonuna ekleyin.

1. Açın, değiştirmek ve güncelleştirilmiş davranışı işlemek için .vstemplate XML dosyasını veya yeni dosyalar kaydedin.

    .Vstemplate şeması hakkında daha fazla bilgi için bkz: [Visual Studio Şablon Şeması Başvurusu (genişletilebilirlik)](../extensibility/visual-studio-template-schema-reference.md). Kaynak dosyalarda Parametreleştirme hakkında daha fazla bilgi için bkz: [şablon parametreleri](../ide/template-parameters.md).

1. Şablonunuzda ve sağ tıklatın veya bağlam menüsünde dosyaları seçin ve **göndermek** > **sıkıştırılmış (daraltılmış) klasör**.

    Seçtiğiniz dosyaların bir .zip dosyasına sıkıştırılır.

1. Yeni .zip dosyasını eski .zip dosyası ile aynı dizine koyun.

1. Ayıklanan şablon dosyalarını ve eski şablonu .zip dosyasını silin.

## <a name="see-also"></a>Ayrıca bkz.

[Şablonlarını özelleştirme](../ide/customizing-project-and-item-templates.md)  
[Proje ve Öğe Şablonları Oluşturma](../ide/creating-project-and-item-templates.md)  
[Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)  
[Şablon Parametreleri](../ide/template-parameters.md)  
[Nasıl Yapılır: Başlangıç Paketleri Oluşturma](../ide/how-to-create-starter-kits.md)