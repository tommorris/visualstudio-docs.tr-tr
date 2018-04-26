---
title: 'Nasıl yapılır: Bir Hizmetteki Verilere Bağlanma'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- data [Visual Studio], connecting to Web services
- data sources, creating from Web services
- data [Visual Studio], reading from Web services
- reading data, from Web services
- Web services, reading data
- Web services, as data sources
- Web services, connecting
ms.assetid: a6b54353-05fe-4e5c-8631-90231fc95504
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 3975d7f0bcfc9b80c944c892cde52f2b625e0bbf
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-connect-to-data-in-a-service"></a>Nasıl yapılır: Bir Hizmetteki Verilere Bağlanma

Uygulamanızı çalıştırarak bir hizmetten döndürülen verileri bağlanmak [veri kaynağı Yapılandırma Sihirbazı](../data-tools/media/data-source-configuration-wizard.png) ve seçerek **hizmet** üzerinde **bir veri kaynağı türüSeç**sayfası.

Tamamlandıktan sonra Sihirbazı, bir hizmet başvurusu projenize eklenir ve hemen kullanılabilir [veri kaynakları penceresi](add-new-data-sources.md).

> [!NOTE]
> İçinde görüntülenen öğeleri **veri kaynakları** penceresi hizmet döndüren bilgi bağımlı. Bazı hizmetler için yeterli bilgi sağlamayabilir **veri kaynağı Yapılandırma Sihirbazı** bağlanabilirse nesneleri oluşturmak için. Hizmet türü belirsiz bir veri kümesini döndürürse, örneğin, daha sonra hiç öğe görünür **veri kaynakları penceresi** Sihirbazı tamamladıktan sonra. Yazılmayan veri kümeleri şema sağlamaz, bu sihirbazın veri kaynağı oluşturmak için yeterli bilgi yok şekilde olmasıdır.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="to-connect-your-application-to-a-service"></a>Uygulamanızı bir hizmete bağlanmak için

1.  Üzerinde **veri** menüsünde tıklatın **yeni veri kaynağı Ekle**.

2.  Seçin **hizmet** üzerinde **bir veri kaynağı türü seç** sayfasında ve ardından **sonraki**.

3.  Tıklayın veya kullanmak istediğiniz hizmeti adresini girin **bulma** geçerli çözümde Hizmetleri bulun ve ardından **Git**.

4.  İsteğe bağlı olarak, yeni **Namespace** yerine varsayılan değeri belirtilmiş olmalıdır.

    > [!NOTE]
    > Tıklatın **Gelişmiş** açmak için [Yapılandırma hizmeti başvuru iletişim kutusu](../data-tools/configure-service-reference-dialog-box.md).

5.  Tıklatın **Tamam** hizmet başvurusu projenize eklemek için.

6.  **Son**'a tıklayın.

     Veri kaynağına eklenen **veri kaynakları** penceresi.

## <a name="next-steps"></a>Sonraki Adımlar

Uygulamanıza işlevsellik eklemek için bir öğe seçin **veri kaynakları** penceresi ve ilişkili denetimler oluşturmak için bir form üzerine sürükleyin. Daha fazla bilgi için bkz: [Visual Studio'da verilere denetimler bağlama](../data-tools/bind-controls-to-data-in-visual-studio.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Bir WCF veri hizmetine WPF denetimleri bağlama](../data-tools/bind-wpf-controls-to-a-wcf-data-service.md)
- [Windows Communication Foundation Hizmetleri ve Visual Studio'da WCF Veri Hizmetleri](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)