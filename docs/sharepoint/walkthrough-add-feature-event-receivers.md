---
title: 'İzlenecek yol: Özellik Olay alıcıları ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, advanced packaging tools
- SharePoint development in Visual Studio, event receivers
- SharePoint development in Visual Studio, feature event receivers
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: cda3967d0fc95fdd8f28503f209a5f2208d07031
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-add-feature-event-receivers"></a>İzlenecek yol: Özellik Olay Alıcıları Ekleme
  Özellik Olay alıcıları özelliği ile ilgili aşağıdaki olaylardan biri SharePoint'te oluştuğunda, yürütme yöntemler şunlardır:  
  
-   Bir özelliğin yüklenme biçimini.  
  
-   Bir özelliği etkinleştirilir.  
  
-   Bir özelliği devre dışı bırakılır.  
  
-   Bir özellik kaldırılır.  
  
 Bu kılavuz, bir SharePoint Proje özelliğinde olay alıcı eklemek gösterilmiştir. Aşağıdaki görevleri gösterir:  
  
-   Boş bir proje ile özellik olay alıcısı oluşturma.  
  
-   İşleme **FeatureDeactivating** yöntemi.  
  
-   Duyuruyu Duyurular listesine eklemek için SharePoint Proje nesne modelini kullanarak.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   Microsoft Windows ve SharePoint sürümleri desteklenir. Daha fazla bilgi için bkz: [SharePoint çözümleri geliştirmek için gereksinimleri](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio.  
  
## <a name="creating-a-feature-event-receiver-project"></a>Özellik olay alıcı proje oluşturma  
 İlk olarak, özellik olay alıcısı içerecek şekilde bir proje oluşturun.  
  
#### <a name="to-create-a-project-with-a-feature-event-receiver"></a>Özellik olay alıcısı ile bir proje oluşturmak için  
  
1.  Menü çubuğunda seçin **dosya**, **yeni**, **proje** görüntülemek için **yeni proje** iletişim kutusu.  
  
2.  Genişletme **SharePoint** ya da düğümünde **Visual C#** veya **Visual Basic**ve ardından **2010** düğümü.  
  
3.  İçinde **şablonları** bölmesinde seçin **SharePoint 2010 proje** şablonu.  
  
     Proje şablonu sahip oldukları için bu proje türü için özellik Olay alıcıları kullanın.  
  
4.  İçinde **adı** kutusuna **FeatureEvtTest**ve ardından **Tamam** görüntülemek için düğmesini **SharePoint Özelleştirme Sihirbazı'nı**.  
  
5.  Üzerinde **hata ayıklama için site ve güvenlik düzeyini belirtmek** sayfasında, yeni özel alan öğesi eklemek istediğiniz SharePoint server site için URL'yi girin veya varsayılan konumu kullanın (http://\<*sistem ad*> /).  
  
6.  İçinde **bu SharePoint çözüm için güven düzeyini nedir?** bölümünde, seçin **Grup çözümü olarak dağıtma** seçenek düğmesi.  
  
     Küme çözümleri karşı korumalı çözümler hakkında daha fazla bilgi için bkz: [Korumalı çözüm değerlendirmeleri](../sharepoint/sandboxed-solution-considerations.md).  
  
7.  Seçin **son** düğmesine tıklayın ve ardından Feature1 adlı bir özellik altında göründüğünü fark **özellikleri** düğümü.  
  
## <a name="adding-an-event-receiver-to-the-feature"></a>Olay alıcısı için özellik ekleme  
 Ardından, olay alıcı özelliğini ekleyin ve özellik devre dışı bırakıldığında yürütülen kodu ekleyin.  
  
#### <a name="to-add-an-event-receiver-to-the-feature"></a>Özelliği için olay alıcı eklemek için  
  
1.  Özellikler düğümü için kısayol menüsünü açın ve ardından **Özellik Ekle** bir özellik oluşturmak için.  
  
2.  Altında **özellikleri** düğümü için kısayol menüsünü açın **Feature1**ve ardından **olay alıcısı Ekle** özelliği için olay alıcı eklemek için.  
  
     Bu kod dosyası Feature1 altında ekler. Bu durumda, onu Feature1.EventReceiver.cs veya Feature1.EventReceiver.vb, projenizin geliştirme dilini bağlı olarak adlandırılır.  
  
3.  Projenizi yazılmışsa [!INCLUDE[csprcs](../sharepoint/includes/csprcs-md.md)], zaten yoksa olay alıcısı en üstte aşağıdaki kodu ekleyin:  
  
     [!code-csharp[SP_FeatureEvt#1](../sharepoint/codesnippet/CSharp/featureevttest2/features/feature1/feature1.eventreceiver.cs#1)]  
  
4.  Olay alıcısı sınıf olayları olarak hareket birkaç kılınan yöntemler içerir. Değiştir **FeatureDeactivating** aşağıdaki yöntemiyle:  
  
     [!code-vb[SP_FeatureEvt#2](../sharepoint/codesnippet/VisualBasic/featureevt2vb/features/feature1/feature1.eventreceiver.vb#2)]
     [!code-csharp[SP_FeatureEvt#2](../sharepoint/codesnippet/CSharp/featureevttest2/features/feature1/feature1.eventreceiver.cs#2)]  
  
## <a name="testing-the-feature-event-receiver"></a>Özellik olay alıcısı test etme  
 Ardından, test etmek için özellik devre dışı olup olmadığını **FeatureDeactivating** yöntemi duyuru SharePoint Duyurular listesine çıkarır.  
  
#### <a name="to-test-the-feature-event-receiver"></a>Özellik olay alıcısı sınamak için  
  
1.  Projenin değerini **etkin Dağıtım Yapılandırması** özelliğine **Hayır etkinleştirme**.  
  
     Bu özelliği ayarlamak, SharePoint'te etkinleştirme özelliği engeller ve özellik Olay alıcıları hata ayıklama olanak tanır. Daha fazla bilgi için bkz: [hata ayıklama SharePoint çözümlerini](../sharepoint/debugging-sharepoint-solutions.md).  
  
2.  Seçin **F5** projeyi çalıştırın ve SharePoint'e dağıtmak için anahtar.  
  
3.  SharePoint Web sayfanın en üstünde açık **Site eylemleri** menüsünde ve ardından **Site Ayarları**.  
  
4.  Altında **Site eylemleri** bölümünü **Site Ayarları** sayfasında, **site özelliklerini Yönet** bağlantı.  
  
5.  Üzerinde **özellikleri** sayfasında, **etkinleştirme** düğmesine **FeatureEvtTest Feature1** özelliği.  
  
6.  Üzerinde **özellikleri** sayfasında, **etkinliğini** düğmesine **FeatureEvtTest Feature1** özelliği ve ardından **bu özelliği devre dışı bırak**  özelliği devre dışı bırakmak için onay bağlantısı.  
  
7.  Seçin **giriş** düğmesi.  
  
     Duyuru görünür bildirimi **duyuruları** özelliği devre dışı bırakıldıktan sonra listeleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: olay alıcısı oluşturma](../sharepoint/how-to-create-an-event-receiver.md)   
 [SharePoint Çözümleri Geliştirme](../sharepoint/developing-sharepoint-solutions.md)  
  
  