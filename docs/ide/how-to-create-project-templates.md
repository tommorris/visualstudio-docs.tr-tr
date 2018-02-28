---
title: "Visual Studio Proje şablonları oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 01/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ExportTemplateWizard
helpviewer_keywords:
- project templates [Visual Studio], creating
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0da7a7979b4fed6f58cdda6f1eafa55517e4df9b
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2018
---
# <a name="how-to-create-project-templates"></a>Nasıl yapılır: Proje şablonları oluşturma

Bu konuda kullanarak bir şablon oluşturmak nasıl gösterilmektedir **şablonu Dışarı Aktarma Sihirbazı**, bir .zip dosyası şablonunuzda paketler.

## <a name="to-create-a-user-project-template-by-using-the-export-template-wizard"></a>Şablonu Dışarı Aktarma Sihirbazı'nı kullanarak bir kullanıcı proje şablonu oluşturmak için

1. Bir proje oluşturun.

    > [!NOTE]
    > Bir proje adlandırma bir şablon kaynağı olacaktır, yalnızca geçerli bir tanımlayıcı karakterlerini kullanın. Aksi takdirde şablondan oluşturulmuş projelerde derleme hataları oluşabilir. Geçerli bir tanımlayıcı karakterler hakkında daha fazla bilgi için bkz: [bildirilen öğe adları (Visual Basic)](/dotnet/visual-basic/programming-guide/language-features/declared-elements/declared-element-names) veya [tanımlayıcıları (C++)](/cpp/cpp/identifiers-cpp). Alternatif olarak, kullanabileceğiniz [şablon parametreleri](../ide/template-parameters.md) "safe" adları sınıfları ve ad alanları için kullanılacak.

1. Bir şablon olarak dışarı hazır olana kadar proje düzenleyin. Örneğin, burada parametre değiştirme gerçekleşmesi belirtmek için kod dosyaları düzenleme isteyebilirsiniz. Bkz: [nasıl yapılır: şablonda parametreleri ikame etme](../ide/how-to-substitute-parameters-in-a-template.md).

1. Üzerinde **proje** menüsünde seçin **şablonu dışarı aktar...** .

   **Şablonu Dışarı Aktarma Sihirbazı** açar.

1. Üzerinde **şablon türünü seç** sayfasında, **proje şablonu**. Bir şablonu dışarı aktarmak ve ardından istediğiniz projesini seçin **sonraki**.

1. Üzerinde **şablon seçenekleri** sayfasında bir ad ve isteğe bağlı bir açıklama girin ve önizleme şablonunuz için resim. Bu öğe görünür **yeni proje** iletişim kutusu. Seçin **son**.

  Proje bir .zip dosyasına dışarı aktardığınız ve belirtilen çıkış konumda ve, seçili olduğunda, Visual Studio'ya içeri.

>[!NOTE]
> Şablonunuzda bulmak için **yeni proje** iletişim kutusunda, genişletin **yüklü** genişletin ve ardından karşılık gelen kategori `ProjectType` .vstemplate dosyasındaki öğesi. Örneğin, içeren .vstemplate dosyası `<ProjectType>CSharp</ProjectType>` altında görünür **yüklü** > **Visual C#**, varsayılan olarak. Yalnızca bu dizinde bir klasör oluşturup, şablonun .zip dosyası içinde yerleştirmek tarafından bir proje türü alt şablonunuzu düzenleyebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: şablonları bulma ve düzenleme](../ide/how-to-locate-and-organize-project-and-item-templates.md).

## <a name="other-ways-to-create-project-templates"></a>Proje şablonları oluşturmak için diğer yolları

Proje bir klasöre oluşturan dosyaları toplama ve ardından uygun meta verileriyle .vstemplate XML dosyası oluşturarak proje şablonları el ile oluşturabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: web şablonlarını elle oluşturma](../ide/how-to-manually-create-web-templates.md).

Yüklü Visual Studio SDK varsa, tamamlanmış şablon dağıtımı için VSIX dosyasında kullanarak kayabilir **VSIX proje** şablonu. Daha fazla bilgi için bkz: [VSIX proje şablonu ile çalışmaya başlama](../extensibility/getting-started-with-the-vsix-project-template.md).

## <a name="see-also"></a>Ayrıca bkz.

[Proje ve Öğe Şablonları Oluşturma](../ide/creating-project-and-item-templates.md)  
[Nasıl Yapılır: Öğe Şablonları Oluşturma](../ide/how-to-create-item-templates.md)  
[VSIX proje şablonu ile çalışmaya başlama](../extensibility/getting-started-with-the-vsix-project-template.md)
