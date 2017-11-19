---
title: "Nasıl yapılır: varolan şablonları güncelleme | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- item templates, updating existing templates
- Visual Studio templates, updating existing templates
- project templates, updating existing templates
ms.assetid: d585e45b-7fe2-45fa-9cf3-7f2bc060f3c4
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0fffcc55953e394c5efd00b86949f04474a66111
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-update-existing-templates"></a>Nasıl yapılır: varolan şablonları güncelleme
Bir şablon oluşturmak ve bir .zip dosyasına dosyaları sıkıştırın sonra şablonu değiştirmek isteyebilirsiniz. Şablon dosyaları el ile değiştirerek veya şablonu temel alan bir projeye ait yeni bir şablon vererek bunu yapabilirsiniz.  
  
## <a name="using-the-export-template-wizard-to-update-an-existing-template"></a>Mevcut bir şablonu güncellemek için şablonu Dışarı Aktarma Sihirbazı'nı kullanma  
Visual Studio sağlayan bir **şablonu dışarı aktar** var olan bir şablonu güncelleştirmek için kullanılan sihirbaz.  
  
#### <a name="to-use-export-template-to-update-an-existing-template"></a>Var olan bir şablonu güncelleştirmek için şablonu Dışarı Aktar kullanma  
  
1.  Açık **yeni proje** seçerek iletişim kutusu **dosya**, **yeni**, **proje**.  
  
2.  Güncelleştirme, bir ad ve projenizin konumunu girin veya seçmek için istediğiniz şablonu seçin **Tamam**.  
  
3.  Visual Studio Proje değiştirin.  
  
4.  Üzerinde **proje** menüsünde seçin **şablonu dışarı aktar**.  

    **Şablonu Dışarı Aktarma Sihirbazı** açar.  

5.  Şablonu bir .zip dosyası olarak dışarı aktarmak için sihirbazdaki yönergeleri izleyin.  

6.  Eski şablon .zip dosyasını silin.  
  
## <a name="manually-updating-an-existing-template"></a>Var olan bir şablonu el ile güncelleştirme  
Dosyaları sıkıştırılmış .zip dosyasını değiştirerek, var olan bir şablonu Visual Studio'nun dışında güncelleştirebilirsiniz.  
  
#### <a name="to-manually-update-an-existing-template"></a>Var olan bir şablonu el ile güncelleştirmek için  
  
1.  Şablonu içeren .zip dosyasını bulun. Varsayılan olarak, bu dosya %USERPROFILE%\Documents\Visual Studio bulunur \<sürüm\>\My dışa aktarılan şablonları\.  
  
2.  .Zip dosyasını ayıklayın.  
  
3.  Değiştirin veya geçerli şablon dosyaları silin veya yeni dosyalar şablonuna ekleyin.  
  
4.  Açın, değiştirmek ve güncelleştirilmiş davranışı işlemek için .vstemplate XML dosyasını veya yeni dosyalar kaydedin.  

    .Vstemplate şeması hakkında daha fazla bilgi için bkz: [Visual Studio şablon şeması başvurusu](../extensibility/visual-studio-template-schema-reference.md). Kaynak dosyalarda Parametreleştirme hakkında daha fazla bilgi için bkz: [şablon parametreleri](../ide/template-parameters.md).  
  
5.  Şablonunuzda dosyaları seçin, sağ tıklatın, **göndermek için**ve ardından **sıkıştırılmış (daraltılmış) klasör**.  

    Seçtiğiniz dosyaların bir .zip dosyasına sıkıştırılır.  
  
6.  Yeni .zip dosyasını eski .zip dosyası ile aynı dizine koyun.  
  
7.  Ayıklanan şablon dosyalarını ve eski şablonu .zip dosyasını silin.  
  
8.  Yükseltilmiş bir örneği, geliştirici komut istemi başlatın:  

  1. Başlat menüsünde gidin **Visual Studio \<sürüm\>**, **Geliştirici komut istemi**.  

  2. (Sağ tıklatma) bağlam menüsünden **daha fazla**, **yönetici olarak çalıştır**.  
  
9. Aşağıdaki komutu çalıştırın: `devenv /installvstemplates`.  
  
## <a name="see-also"></a>Ayrıca bkz.  
[Şablonlarını özelleştirme](../ide/customizing-project-and-item-templates.md)   
[Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)   
[Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)   
[Şablon parametreleri](../ide/template-parameters.md)   
[Nasıl yapılır: başlangıç paketleri oluşturma](../ide/how-to-create-starter-kits.md)