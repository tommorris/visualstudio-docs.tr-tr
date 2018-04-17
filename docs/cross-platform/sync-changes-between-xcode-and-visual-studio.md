---
title: Eşitleme XCode ve Visual Studio arasındaki değişiklikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c71a4d7c-120e-4559-a114-3a99c4b860a9
ms.technology: vs-ide-mobile
author: corob-msft
ms.author: corob
manager: douge
ms.workload:
- xamarin
ms.openlocfilehash: 09067c881e717f5e3e2ed6295e0f550adf29f511
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="sync-changes-between-xcode-and-visual-studio"></a>XCode ve Visual Studio arasındaki eşitleme değişiklikleri
Mobil Geliştirme bileşen için Microsoft Visual C++ çalışmanızı PC ve Mac arasında eşitlenmesi uzak yetenekleri içerir Visual Studio ve Mac makinelerinizi eşleştirilmiş, iOS, Xcode'da projenize açmak için kullanabileceğiniz Visual Studio'da Uygulama projeleri için yeni seçenekler kullanılabilir taşıma kodunuzu XCode ve Visual Studio arasında ve geçici XCode projesi dizin temizleme.  
  
 Uzak makine seçeneklerini kullanmak için projenizin bir iOS uygulaması projesini olmalıdır ve Visual Studio ile Mac eşleştirilmelidir Önkoşullar ve çiftine Mac hakkında yönergeler için bkz: [yükleme ve yapılandırma araçları iOS kullanılarak derleme](../cross-platform/install-and-configure-tools-to-build-using-ios.md).  
  
## <a name="the-remote-machine-menu"></a>Uzak makine menüsü  
 İçinde **Çözüm Gezgini**, bağlam menüsü göstermek için bir iOS uygulaması projeye sağ tıklayın. Seçin **uzak makine** Uzak seçenekleri gösterilecek öğe.  
  
 ![Çözüm Gezgini'nde uzak makine menü öğesi](../cross-platform/media/cppmdd_u2_remotemachine_menu.jpg "CPPMDD_U2_RemoteMachine_Menu")  
  
 Bu komutlar, Xcode'da, projenizi açın yerel değişiklikler veya taşımak tüm projeyi Visual Studio ve XCode arasında ve geçici dosyalar uzak makinede temiz olanak tanır.  
  
### <a name="open-in-xcode"></a>Xcode'da Aç  
 Visual Studio'dan XCode projesinde açmak için **uzak makine** alt seçin **Xcode'da Aç** eşleştirilmiş uzak makinede seçilen projeyi açın. Vcremote sunucunun Mac XCode açın ve projeyi bir kopyasını içeren Mac üzerinde oluşturulan geçici bir dizine gidin için kullanılır. Visual Studio projesi için kullanılan geçici dizini gösteren bir iletişim kutusu görüntüler. Uzak makinede gerçekleştirilen eylemleri de gösterilir **çıkış** Visual Studio'daki. Bunları görmek için seçmeniz gerekebilir **Visual C++ uzak makine** içinde **Göster çıktı** en üstündeki açılır **çıkış** penceresi.  
  
 ![Çıktı penceresi uzak makine eylemleri gösterir. ] (../cross-platform/media/cppmdd_u2_remotemachine_output.png "CPPMDD_U2_RemoteMachine_Output")  
  
 Mac'inizde kod ve kaynakları, film şeritleri ve eylemleri düzenlemek için tüm XCode araçlarını kullanabilirsiniz. Visual Studio'da "Açılan içinde uzak makinede değişiklik yaptığınız olduğunu göstermek için XCode" ile iOS uygulaması projenize işaretiyle gösterilir. Düzenlemeleriniz tamamlandıktan sonra değişiklikleri geri Visual Studio projenize kopyalamak için uzaktan gelen çekme veya artımlı çekme uzak komutlarındaki kullanabilirsiniz.  
  
### <a name="push-to-remote-and-incremental-push-to-remote"></a>Uzaktan için Uzak ve artımlı gönderim iletin  
 İOS uygulaması projeniz Visual Studio'da değişiklik yaptıysanız eşleştirilmiş uzak makineye değiştirilen proje dosyalarını taşımak için anında iletme uzak ve artımlı gönderme uzak komutları için kullanılabilir. Uzak komuta itme uzak makineye tüm proje dosyalarını kopyalar. Artımlı anında uzak komutu yalnızca değiştirilen dosyaların uzak makineye kopyalar. Küçük değişikliklerle büyük projeler için artımlı komutu süresi ve bant genişliği kaydedebilirsiniz.  
  
 Visual Studio'da Mac bilgisayarınızı proje dosyalarını kopyalamak için **Çözüm Gezgini** penceresinde, bağlam menüsünü açmak için iOS uygulama projesine sağ tıklayın. Seçin **uzak makine** ve seçin **anında uzaktan** veya **artımlı itme uzaktan** Mac için Visual Studio proje dosyalarını kopyalamak için  
  
### <a name="pull-from-remote-and-incremental-pull-from-remote"></a>Uzaktan gelen uzak ve artımlı çekme isteneceğini  
 Xcode'da projenize herhangi bir değişiklik yaptıktan sonra değişiklikler projeleri eşitlenmiş tutmak için Visual Studio için geri dönün.  
  
 Visual Studio'da Mac bilgisayarınızı proje dosyalarını kopyalamak için **Çözüm Gezgini** penceresinde, bağlam menüsünü açmak için iOS uygulama projesine sağ tıklayın. Seçin **uzak makine** ve seçin **çekme uzaktan** veya **artımlı çekme uzaktan gelen** , Mac için Visual Studio proje dosyalarını kopyalanacak.  
  
### <a name="clean-remote"></a>Uzaktan temizleme  
 Uzak makinedeki geçici proje dizininde dosyaları silmek için temiz uzak komutunu kullanabilirsiniz. Herhangi bir kaynak dosya veya derleme ürünler dahil olmak üzere bu dizinin içindekilerin Mac üzerindeki kaldırılır Temiz uzak komutunu kullanmadan önce uzak gelen çekme veya artımlı çekme uzak gelen kullanarak Visual Studio'ya geri tutmak istediğiniz değişiklikleri eşitlendiğinden emin olun.  
  
 Geçici proje directory uzak makinede Visual Studio'da temizlemek için **Çözüm Gezgini** penceresinde, bağlam menüsünü açmak için iOS uygulama projesine sağ tıklayın. Seçin **uzak makine** ve **temiz uzak** Mac proje dizin dosyalarını kaldırmak için