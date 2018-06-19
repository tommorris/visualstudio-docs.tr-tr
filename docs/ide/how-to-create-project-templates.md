---
title: Visual Studio Proje şablonları oluşturma
ms.date: 01/02/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- VS.ExportTemplateWizard
helpviewer_keywords:
- project templates [Visual Studio], creating
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 8e35833f9f8facf0639a87243d46794408167914
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31944628"
---
# <a name="how-to-create-project-templates"></a>Nasıl yapılır: Proje şablonları oluşturma

Bu konuda kullanarak bir şablon oluşturmak nasıl gösterilmektedir **şablonu Dışarı Aktarma Sihirbazı**, şablonunuzda paketleri bir *.zip* dosyası.

## <a name="to-create-a-user-project-template-by-using-the-export-template-wizard"></a>Şablonu Dışarı Aktarma Sihirbazı'nı kullanarak bir kullanıcı proje şablonu oluşturmak için

1. Bir proje oluşturun.

    > [!NOTE]
    > Bir proje adlandırma bir şablon kaynağı olacaktır, yalnızca geçerli bir tanımlayıcı karakterlerini kullanın. Aksi takdirde şablondan oluşturulmuş projelerde derleme hataları oluşabilir. Geçerli bir tanımlayıcı karakterler hakkında daha fazla bilgi için bkz: [bildirilen öğe adları (Visual Basic)](/dotnet/visual-basic/programming-guide/language-features/declared-elements/declared-element-names) veya [tanımlayıcıları (C++)](/cpp/cpp/identifiers-cpp). Alternatif olarak, kullanabileceğiniz [şablon parametreleri](../ide/template-parameters.md) "safe" adları sınıfları ve ad alanları için kullanılacak.

1. Bir şablon olarak dışarı hazır olana kadar proje düzenleyin. Örneğin, burada parametre değiştirme gerçekleşmesi belirtmek için kod dosyaları düzenleme isteyebilirsiniz. Bkz: [nasıl yapılır: şablonda parametreleri ikame etme](../ide/how-to-substitute-parameters-in-a-template.md).

1. Üzerinde **proje** menüsünde seçin **şablonu dışarı aktar**.

   **Şablonu Dışarı Aktarma Sihirbazı** açar.

1. Üzerinde **şablon türünü seç** sayfasında, **proje şablonu**. Bir şablonu dışarı aktarmak ve ardından istediğiniz projesini seçin **sonraki**.

1. Üzerinde **şablon seçenekleri** sayfasında bir ad ve isteğe bağlı bir açıklama girin ve önizleme şablonunuz için resim. Bu öğe görünür **yeni proje** iletişim kutusu. Seçin **son**.

  Proje içine aktarılır bir *.zip* dosya belirtilen çıkış konumda ve, seçili olduğunda, Visual Studio'ya içeri aktarıldı.

>[!NOTE]
> Şablonunuzda bulmak için **yeni proje** iletişim kutusunda, genişletin **yüklü** genişletin ve ardından karşılık gelen kategori `ProjectType` öğesinde *.vstemplate*dosya. Örneğin, bir *.vstemplate* içeren dosya `<ProjectType>CSharp</ProjectType>` altında görünür **yüklü** > **Visual C#**, varsayılan olarak. Yalnızca bu dizinde bir klasör oluşturma ve, şablonun yerleştirme proje türü bir alt şablonunuzu düzenleyebilirsiniz *.zip* içindeki dosya. Daha fazla bilgi için bkz: [nasıl yapılır: şablonları bulma ve düzenleme](../ide/how-to-locate-and-organize-project-and-item-templates.md).

## <a name="other-ways-to-create-project-templates"></a>Proje şablonları oluşturmak için diğer yolları

Proje şablonları el ile bir klasöre proje oluşturan dosyaları toplama ve ardından oluşturma oluşturabileceğiniz bir *.vstemplate* uygun meta verileri olan XML dosyası. Daha fazla bilgi için bkz: [nasıl yapılır: web şablonlarını elle oluşturma](../ide/how-to-manually-create-web-templates.md).

Yüklü Visual Studio SDK varsa, tamamlanmış şablon dağıtımı için VSIX dosyasında kullanarak kayabilir **VSIX proje** şablonu. Daha fazla bilgi için bkz: [VSIX proje şablonu ile çalışmaya başlama](../extensibility/getting-started-with-the-vsix-project-template.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)
- [Nasıl yapılır: öğe şablonları oluşturma](../ide/how-to-create-item-templates.md)
- [VSIX proje şablonu ile çalışmaya başlama](../extensibility/getting-started-with-the-vsix-project-template.md)