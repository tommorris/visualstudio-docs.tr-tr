---
title: "Nasıl yapılır: başlangıç paketleri oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Starter Kits, creating
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d5a779c1c8779c6d7126b67da9e60326284221a6
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2018
---
# <a name="how-to-create-starter-kits"></a>Nasıl Yapılır: Başlangıç Paketleri Oluşturma

Starter Kit tam bir uygulama ve belgeleri değiştirmek veya uygulama genişletmek nasıl kodunu içerir. Starter Kit oluşturma temelde normal proje şablonu oluşturma ile aynıdır, tek farkı Starter Kit Starter Kit temel alan bir proje zaman açmak için ayarlanmış olan belgeleri dosyaları içeren olmasına, oluşturulur.

## <a name="designing-and-developing-a-starter-kit"></a>Tasarlama ve Starter Kit geliştirme

İlk olarak, geliştirmek ve hedef kitlenizi tanımlamak istediğiniz Starter Kit türünü belirlemeniz gerekir. Ardından, proje ve belgeler hedeflerinizi karşılayacak şekilde tasarlayın.

Bir örnek, bir uygulama veya eklenti oluşturuyorsanız:

- Hatasız derlemeler bir proje oluşturun.

- Ek görevler (isteğe bağlı) uygulamak için şablon kodu ekleyin.

- Belge hazırlayın.

Bir öğrenme aracı oluşturuyorsanız:

- Hatasız derlemeler bir proje oluşturun.

- Kod parçacıkları ve öğe şablonları gibi kaynakları düzenleyin.

- Belge hazırlayın.

## <a name="creating-a-template"></a>Şablon oluşturma

Proje ve belgeler tamamladıktan sonra proje şablonu için başlangıç paketi oluşturmak hazır olursunuz. Bu işlem, tam olarak bir proje şablonu oluşturma ile aynı değil.

Aşağıdaki konular, şablonları oluşturma hakkında bilgi içerir:

- [Nasıl yapılır: Proje şablonları oluşturma](../ide/how-to-create-project-templates.md) &ndash; nasıl kullanılacağı açıklanmaktadır **şablonu Dışarı Aktarma Sihirbazı** bir şablon oluşturmak için.
- [Nasıl yapılır: var olan şablonları güncelleştirme](../ide/how-to-update-existing-templates.md) &ndash; var olan bir şablonu düzenlemeyi açıklar. Starter Kit özelleştirmek için .vstemplate dosyasını değiştirmek için bu yordamı kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Proje ve Öğe Şablonları Oluşturma](../ide/creating-project-and-item-templates.md)  
[Şablonlarını özelleştirme](../ide/customizing-project-and-item-templates.md)  
[Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)