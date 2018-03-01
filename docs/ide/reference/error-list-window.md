---
title: Hata Listesi penceresi | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ErrorList
helpviewer_keywords:
- Task List
- build errors
- Error List window
- errors [Visual Studio], Error List window
ms.assetid: b7f6d45a-733b-4ad8-bc2f-737a37509e56
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 227c23714231c87ba2ecac5fa7f50a632a73b123
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="error-list-window"></a>Hata Listesi Penceresi
> [!NOTE]
>  Hata Listesi belirli bir hata iletisi hakkında bilgi görüntüler. Çıktı penceresinden hata numarası veya hata dizesi metni kopyalayabilirsiniz. Çıktı penceresini görüntülemek için Ctrl + Alt + O tuşlarına basın. Bkz: [çıktı penceresi](../../ide/reference/output-window.md).  
  
 Kullanarak daha hızlı uygulamalar geliştirebilir **hata listesi** penceresi. Örneğin, aşağıdaki görevleri gerçekleştirebilirsiniz:  
  
-   Hataları, uyarıları ve kod yazarken üretilen iletileri görüntüler.  
  
-   IntelliSense tarafından belirtildiği sözdizimi hataları bulun.  
  
-   Dağıtım hataları, statik belirli çözümleme Bul hataları ve hataları Kurumsal şablon ilkeleri uygulanırken algılandı.  
  
-   Burada sorunu oluşur ve hata konuma taşı dosyayı açmak için herhangi bir hata iletisi giriş çift tıklayın.  
  
-   Hangi girişleri görüntülenir ve her giriş için hangi sütunların bilgilerin görünür filtreleyin.  
  
-   Belirli terimleri için arayın ve yalnızca geçerli proje veya belge aramayı kapsam.  
  
Görüntülenecek **hata listesi**, tıklatın **görünüm / hata listesinde**, veya **CTRL +\\+ E**.  
  
Seçebileceğiniz **hataları**, **uyarıları**, ve **iletileri** farklı düzeylerde bilgileri görmek için sekmeler.  
  
Sıralamak için herhangi bir sütun başlığını tıklatın. Yeniden başka bir sütuna göre sıralamak için SHIFT tuşunu basılı tutun ve başka bir sütun başlığını tıklatın. Hangi sütunlar görüntülenir ve hangi gizlenir seçmek istediğinizde **sütunları göster** kısayol menüsünden. Sütunların görüntüleneceği sırayı değiştirmek için herhangi bir sütun başlığını sola veya sağa sürükleyin.  
  
> [!NOTE]
>  İletişim kutuları ve menü komutlarını gördüğünüz açıklanana burada etkin ayarlarınıza veya sürümünüze bağlı olarak farklı olabilir. Ayarlarınızı değiştirmek için tıklatın. **araçları / içeri ve dışarı aktarma ayarları**. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="error-list-filters"></a>Hata listesi filtreleri  
 Araç çubuğunun sağ tarafında biri diğeri araç solundaki iki açılan kutusu filtrede iki tür vardır. Araç çubuğunun sol tarafında açılır listede kullanmak üzere kod dosyaları kümesini belirtir (**çözümün tamamında**, **açık belgeleri**, **geçerli projenin**,  **Geçerli belge**).  
  
 Çözümleme ve hataları grupları üzerinde hareket için arama kapsamını sınırlayabilirsiniz. Örneğin, bir projeyi derleme gelen engelliyor Çekirdek hataları odaklanmak isteyebilirsiniz. Kapsam seçenekleri şunlardır:  
  
1.  **Belgeleri açma**: hatalar, uyarılar ve açık belgeler için iletileri göster.  
  
2.  **Geçerli projenin**: hatalar, uyarılar ve şu anda seçili belgedeki projeden iletileri göster **Düzenleyicisi** veya seçilen projede **Çözüm Gezgini**.  
  
    > [!NOTE]
    >  Şu anda seçili belgenin seçili projeden farklı projesiyse hataları, uyarıları ve iletileri filtrelenmiş listesi değişir **Çözüm Gezgini**.  
  
3.  **Geçerli belge**: hatalar, uyarılar ve şu anda seçili belgedeki iletileri göster **Düzenleyicisi** veya **Çözüm Gezgini**.  
  
Arama sonucu için bir filtre uygulanmış durumda, filtrenin adını görünür **hata listesi** başlık çubuğu. **Hataları**, **uyarıları**, ve **iletileri** düğmeleri sonra toplam öğe sayısını birlikte gösterildikten filtrelenmiş öğe sayısını görüntüleyin; örneğin, düğme Göster x, y hataları. Hiçbir filtre uyguladıysanız, başlık çubuğu "Hata listesi" yalnızca söyler.  
  
Araç çubuğunun sağ tarafında listede (derleme işleminden kaynaklanan hatalar) derleme hataları gösterilip gösterilmeyeceğini belirtir veya IntelliSense (derleme çalıştırmadan önce algılanan hatalar) veya her ikisi de.  
  
## <a name="search"></a>Ara  
 Kullanım **arama hata listesi** metin kutusunun sağ tarafında **hata listesi** hata listesinde belirli hataları bulmak için araç. Arama sonuçları her zaman sorgu veya uygulanan filtre yerine sıralama önceliğe sahip sütun göre sıralanır ve hata listesinde görünür sütununun arayabilir. Seçerseniz **Esc** odağı olarak kullanılırken anahtar **hata listesi**, arama sonuçları filtrelenmiş ve arama terimi temizleyebilirsiniz. Tıklatarak **X** temizleyin metin kutusunun sağ tarafındaki.  
  
## <a name="save"></a>Kaydet  
 Hata listesi kopyalayın ve bir dosyaya kaydedin. Kopyalayın ve seçime sağ tıklayın ve ardından bağlam menüsünde istediğiniz hatalarını seçin **kopya**. Daha sonra bir dosyaya hataları yapıştırabilirsiniz. Bir Excel elektronik tablosuna hataları yapıştırırsanız, alanlar farklı sütun olarak görünür.  
  
## <a name="ui-element-list"></a>UI öğe listesi  
 Önem Derecesi  
 Farklı türde görüntüler **hata listesi** giriş (**hata**, **ileti**, **uyarı**, **uyarı (etkin)**, **(Etkin) uyarı**.  
  
 Kod  
 Hata kodu görüntüler.  
  
 Açıklama  
 Giriş metni görüntüler.  
  
 Proje  
 Geçerli projenin adını görüntüler.  
  
 Dosya  
 Dosya adını görüntüler.  
  
 Çizgi  
 Sorunun nerede oluştuğunu satır görüntüler.