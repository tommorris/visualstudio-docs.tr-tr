---
title: 'Nasıl yapılır: bir SharePoint özelliğini özelleştirme | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.RAD.FeatureDesigner.SwitchView
- VS.SharePointTools.RAD.featureDesigner.Manifest
- VS.SharePointTools.RAD.FeatureDesignerProperties
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, features
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f22ec947e9aa3cae15427915bd5aff4122a67797
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-customize-a-sharepoint-feature"></a>Nasıl yapılır: Bir SharePoint Özelliğini Özelleştirme
  Oluşturun ve Visual Studio'da özelliği Tasarımcı kullanarak SharePoint özelliklerini özelleştirin. Örneğin, özellik kapsamı ayarlayın ve diğer özellikleri bağımlılıkları olarak ekleyin. Çözüm Gezgini veya SharePoint paketi Gezgini içinde yeni bir özellik eklediğinizde, varsayılan olarak, özellik Tasarımcısı açılır.  
  
## <a name="opening-the-feature-designer"></a>Özellik Tasarımcısı'nı açma  
 Ekleyin veya özellik Tasarımcısı'nı kullanarak bir özellik için SharePoint Proje öğeleri kaldırın.  
  
#### <a name="to-open-the-feature-designer"></a>Özellik Tasarımcısı'nı açmak için  
  
1.  İçinde **Çözüm Gezgini**, genişletin **özellikleri**.  
  
2.  Çift *Feature1* öğesini veya kısayol menüsünü açın *Feature1* öğesini ve ardından **Görünüm Tasarımcısı**.  
  
## <a name="viewing-the-packaged-manifest-file"></a>Paket bildirim dosyasının görüntüleme  
 Paket bildirim dosyası (Feature.xml dosyasına) özelliği için oluşturmak ve değiştirmek için Özellik Tasarımcısı'nı kullanabilirsiniz. Ardından, Visual Studio'da bu dosya için XML kodunu görüntüleyebilirsiniz.  
  
#### <a name="to-view-the-packaged-manifest-file"></a>Paket bildirim dosyasının görüntülemek için  
  
1.  İçinde **özelliği Designer**, seçin **bildirim** sekmesi.  
  
#### <a name="to-view-the-packaged-manifest-file-by-using-solution-explorer"></a>Çözüm Gezgini kullanarak paket bildirim dosyasının görüntülemek için  
  
1.  İçinde **Çözüm Gezgini**, seçin **tüm dosyaları göster** simgesi.  
  
2.  Özellikleri'ni genişletin, FeatureName genişletin, FeatureName.feature genişletin ve ardından açın *FeatureName*. Template.xml dosyası.  
  
    > [!NOTE]  
    >  Özellik şablon bildirim XML dosyası açtığınızda, dosyaları otomatik olarak doğrulanır ve Hata Listesi penceresinde görünen uyarıları göz ardı edilebilir.  
  
## <a name="changing-the-manifest-template"></a>Bildirim şablonu değiştirme  
 Visual Studio XML Düzenleyicisi'ni veya bildirim şablonu bölmesindeki özellik bildirim dosyası için XML kodunu değiştirebilirsiniz. XML kodunu değişiklikleri birleştirilir paket bildirim dosyasının özelliği. Örneğin, bir özellik özelleştirmek için bildirim şablonu değiştirmek isteyebilirsiniz.  
  
#### <a name="to-change-the-manifest-template-by-using-the-xml-editor"></a>XML Düzenleyicisi'ni kullanarak bildirim şablonu değiştirmek için  
  
1.  İçinde **özelliği Designer**, seçin **bildirim** sekmesinde, genişletin **seçeneklerini Düzenle** düğümünü ve ardından **XML düzenleyicisinde açın** bağlantı.  
  
     XML değişiklikler paket bildirim dosyasının birleştirilir.  
  
#### <a name="to-change-the-manifest-template-by-using-the-manifest-template-pane"></a>Bildirim şablonu bölmesini kullanarak bildirim şablonu değiştirmek için  
  
1.  İçinde **özelliği Designer**, seçin **bildirim** sekmesinde, genişletin **seçeneklerini Düzenle** düğümü ve bildirim şablonu bölmesinde görüntülenen XML değiştirin.  
  
     XML değişiklikler görünür **paketlenmiş, Önizleme bildirim** bölmesi.  
  
## <a name="overwriting-the-packaged-manifest-file"></a>Paket bildirim dosyasının üzerine  
 Özellik Tasarımcısı'nı devre dışı bırakabilir ve Feature.xml dosyasına dosyayı el ile oluşturun. Bu yordamı gerçekleştirmek ilk kez özellik Tasarımcısı'nda geçerli ayarları özellik şablonu XML dosyasına kaydedilir. Ardından, değiştirmek veya XML kodunu üzerine yazabilirsiniz.  
  
> [!NOTE]  
>  Bu proje öğeleri ekleme veya özellik Tasarımcısı'nı devre dışı durumdayken SharePoint Proje öğeleri XML dosyasında kaldırırsanız, paket yok.  
  
#### <a name="to-overwrite-packaged-manifest-file-by-disabling-the-designer"></a>Tasarımcı devre dışı bırakarak paket bildirim dosyasının üzerine yazmak için  
  
1.  İçinde **özelliği Designer**, seçin **bildirim** sekmesi.  
  
2.  Genişletin **seçeneklerini Düzenle** düğümü seçin **üzerine yaz oluşturulan XML ve düzenleme bildiriminde XML Düzenleyicisi'ni** bağlamak ve ardından **Evet** düğmesi.  
  
     Şablonu geçerli paket bildirim dosyası güncelleştirilir.  
  
## <a name="enabling-the-feature-designer"></a>Özellik Tasarımcısı'nı etkinleştirme  
 Feature.xml dosyasına dosyasını özelleştirmek için bu özelliği Designer yeniden etkinleştirebilirsiniz.  
  
#### <a name="to-re-enable-the-designer"></a>Tasarımcı yeniden etkinleştirmek için  
  
1.  İçinde **özelliği Designer**, seçin **atma bildirim düzenleme ve yeniden Tasarımcısı'nı etkinleştirmeniz** bağlamak ve ardından **Evet** düğmesi.  
  
2.  Şablon özgün metinle yenilenir ve XML değişiklikler kaybolur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint Çözümlerini Paketleme ve Dağıtma](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  