---
title: 'Nasıl Yapılır: WCF Veri Hizmeti Başvurusunu Güncelleme veya Kaldırma'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- service references [Visual Studio]
- WCF Data Service reference
- WCF data service references
- ADO.NET service references
- ADO.NET Data Service reference
ms.assetid: 892ebf37-3af4-472e-8744-92837677d611
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: b6726b2c859143f5dbc9b264e67bb9bb91757de5
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37089318"
---
# <a name="how-to-add-update-or-remove-a-wcf-data-service-reference"></a>Nasıl yapılır: ekleme, güncelleştirme veya bir WCF veri hizmeti başvurusunu kaldırma
A *hizmet başvurusu* bir proje için bir veya daha fazla erişim sağlayan [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)]. Kullanım **hizmet Başvurusu Ekle** aramak için iletişim kutusu [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] geçerli çözümde, yerel ağ üzerinde yerel olarak ya da Internet üzerindeki.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="add-a-service-reference"></a>Hizmet Başvurusu Ekle

### <a name="to-add-a-reference-to-an-external-service"></a>Bir dış hizmetine başvuru eklemek için

1.  İçinde **Çözüm Gezgini**, hizmeti eklemek ve ardından istediğiniz proje adına sağ tıklayın **hizmet Başvurusu Ekle**.

     **Hizmet Başvurusu Ekle** iletişim kutusu görüntülenir.

2.  İçinde **adresi** kutusuna hizmeti URL'sini girin ve ardından **Git** hizmetinde aramak için. Hizmetin kullanıcı adı ve parola güvenlik uygularsa, bir kullanıcı adı ve parolası istenebilir.

    > [!NOTE]
    >  Yalnızca güvenilir bir kaynaktan Hizmetleri başvuruda bulunmalıdır. Güvenilmeyen bir kaynaktan başvuruları ekleme, güvenliği tehlikeye atabilir.

     URL'den öğesini de seçebilirsiniz **adresi** geçerli hizmet meta verisi bulunamadı önceki 15 URL'leri depolar listesi.

     Arama gerçekleştirildiğinde bir ilerleme çubuğu görüntüler. Tıklayarak istediğiniz zaman arama durdurabilirsiniz **durdurmak**.

3.  İçinde **Hizmetleri** listesinde, kullanma ve bir varlık kümesi seçme istediğiniz hizmeti düğümünü genişletin.

4.  İçinde **Namespace** kutusuna, başvuru için kullanmak istediğiniz ad alanı girin.

5.  Tıklatın **Tamam** projesine başvuru eklemek için.

     Bir hizmeti istemcisi (proxy) oluşturulur ve hizmet açıklayan meta veriler eklenen *app.config* dosya.

### <a name="to-add-a-reference-to-a-service-in-the-current-solution"></a>Geçerli çözümde bir hizmet için bir başvuru eklemek için

1.  İçinde **Çözüm Gezgini**, hizmeti eklemek ve ardından istediğiniz proje adına sağ tıklayın **hizmet Başvurusu Ekle**.

     **Hizmet Başvurusu Ekle** iletişim kutusu görüntülenir.

2.  Tıklatın **Bul**.

     Tüm hizmetler (her ikisi de [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] ve WCF hizmetleri) geçerli çözümde eklenir **Hizmetleri** listesi.

3.  İçinde **Hizmetleri** listesinde, kullanma ve bir varlık kümesi seçme istediğiniz hizmeti düğümünü genişletin.

4.  İçinde **Namespace** kutusuna, başvuru için kullanmak istediğiniz ad alanı girin.

5.  Tıklatın **Tamam** projesine başvuru eklemek için.

     Bir hizmeti istemcisi (proxy) oluşturur ve hizmet açıklayan meta veriler eklenen *app.config* dosya.

## <a name="update-a-service-reference"></a>Güncelleştirme hizmeti başvurusu
 Varlık veri modeli için bir [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] bazen değiştirir. Bu gerçekleştiğinde, hizmet başvurusu güncelleştirmeniz gerekir.

### <a name="to-update-a-service-reference"></a>Hizmet başvurusu güncelleştirmek için

-   İçinde **Çözüm Gezgini**, hizmet başvurusu sağ tıklayın ve ardından **güncelleştirme hizmet başvurusu**.

     Başvuru özgün konumundan güncelleştirilir ve hizmeti istemcisi meta verilerindeki değişiklikleri yansıtacak şekilde yeniden ilerleme durumu iletişim kutusu görüntüler.

## <a name="remove-a-service-reference"></a>Bir hizmet başvurusunu kaldırın
 Hizmet başvurusu artık kullanılıp kullanılmadığını çözümünüzden kaldırabilirsiniz.

### <a name="to-remove-a-service-reference"></a>Hizmet başvurusunu kaldırmak için

-   İçinde **Çözüm Gezgini**, hizmet başvurusu sağ tıklayın ve ardından **silmek**.

     Hizmeti istemcisi çözümden kaldırılacak ve hizmet açıklayan meta veriler kaldırılır *app.config* dosya.

    > [!NOTE]
    >  Hizmet başvurusu başvuran herhangi bir kod el ile kaldırılması gerekir.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da Windows Communication Foundation Hizmetleri ve WCF Veri Hizmetleri](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)