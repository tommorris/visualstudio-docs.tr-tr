---
title: 'Hata ayıklama hazırlığı: Visual C++ proje türleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- project templates, debugging
- Visual C++ projects, debugging
- debug builds, project settings
- debugging [C++]
ms.assetid: 912b4ba2-7719-43d5-b087-db33e3f9329a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: e02be24447d5383388be0a7208bf84e36333732f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="debugging-preparation-visual-c-project-types"></a>Hata Ayıklama Hazırlığı: Visual C++ Proje Türleri
Bu bölümde temel proje türleri tarafından oluşturulan hata ayıklama açıklar [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] proje şablonları.  
  
 DLL'leri çıktılarını oluşturma bu proje türleri halinde gruplandırılır Not [DLL projelerinde hata ayıklama](../debugger/debugging-dll-projects.md) paylaştıkları genel özellikleri nedeniyle.  
  
##  <a name="BKMK_In_this_topic"></a> Bu konudaki  
 [Önerilen özellik ayarları](#BKMK_Recommended_Property_Settings)  
  
 [Win32 projeleri](#BKMK_Win32_Projects)  
  
-   [C veya C++ Win32 uygulama hata ayıklamak için](#BKMK_To_debug_a_C_or_C___Win32_application)  
  
-   [Hata ayıklama yapılandırmasını el ile ayarlamak için](#BKMK_To_manually_set_a_Debug_configuration)  
  
 [Windows Forms uygulamaları (.NET)](#BKMK_Windows_Forms_Applications___NET_)  
  
##  <a name="BKMK_Recommended_Property_Settings"></a> Önerilen özellik ayarları  
 Bazı özellikler tüm yönetilmeyen hata ayıklama senaryoları için aynı şekilde ayarlamanız gerekir. Aşağıdaki tablolarda, önerilen özellik ayarları görüntüleyin. Burada listelenmeyen ayarları farklı yönetilmeyen proje türleri arasında farklılık gösterebilir. Daha fazla bilgi için bkz: [bir C++ hata ayıklama yapılandırması proje ayarları](../debugger/project-settings-for-a-cpp-debug-configuration.md)  
  
### <a name="configuration-properties-124-cc-124-optimization-node"></a>Yapılandırma özellikleri &#124; C/C++ &#124; en iyi duruma getirme düğümü  
  
|Özellik adı|Ayar|  
|-------------------|-------------|  
|**En iyi duruma getirme**|Kümesine **devre dışı (/ 0 d).** Oluşturulan yönergeleri doğrudan kaynak koduna karşılık gelmediğinden en iyi duruma getirilmiş daha zor hata ayıklamak için kodudur. Programınızı sahip yalnızca iyileştirilmiş kodda görüntülenen hata fark ederseniz, bu ayarı etkinleştirmek, ancak gösterilen kodu unutmayın **ayrıştırılmış** penceresi kaynak gördükleri eşleşmeyebilir en iyi duruma getirilmiş kaynağından oluşturulur Windows. Atlama gibi diğer özellikleri, beklendiği gibi çalışmayabilir.|  
  
### <a name="configuration-properties-124-linker-124-debugging-node"></a>Yapılandırma özellikleri &#124; bağlayıcı &#124; hata ayıklama düğümü  
  
|Özellik adı|Ayar|  
|-------------------|-------------|  
|**Hata ayıklama bilgisi oluştur**|Her zaman bu seçeneği ayarlamalısınız **Evet (/ DEBUG)** hata ayıklama simgeleri ve hata ayıklama için gerekli dosyaları oluşturmak için. Uygulama üretime gittiğinde, off olarak ayarlayabilirsiniz.|  
  
 [Bu konudaki](../debugger/debugging-preparation-visual-cpp-project-types.md#BKMK_In_this_topic)  
  
##  <a name="BKMK_Win32_Projects"></a> Win32 projeleri  
 Win32 uygulamaları C veya C++ ile yazılmış geleneksel Windows programlardır. Bu tür bir uygulamada hata ayıklama [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] basittir.  
  
 Win32 uygulamaları MFC uygulamaları ve ATL projeleri içerir. Windows API'larını kullanın ve MFC ya da ATL kullanabilir, ancak ortak dil çalışma zamanı (CLR) kullanmayın. Ancak, CLR kullanan yönetilen kodu çağrısı olabilir.  
  
 Aşağıdaki yordam içinden bir Win32 projenin hata ayıklamasını açıklanmaktadır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Dışında uygulamayı başlatmak için bir Win32 uygulaması hata ayıklamak için başka bir yol olduğu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve ekleyebilir. Daha fazla bilgi için bkz: [eklemek için çalışan işlemler](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
###  <a name="BKMK_To_debug_a_C_or_C___Win32_application"></a> C veya C++ Win32 uygulama hata ayıklamak için  
  
1.  Projesini Visual Studio'da açın.  
  
2.  Üzerinde **hata ayıklama** menüsünde seçin **Başlat**.  
  
3.  İçinde açıklanan teknikleri kullanarak hata ayıklama [hata ayıklayıcı temel bilgileri](../debugger/debugger-basics.md).  
  
###  <a name="BKMK_To_manually_set_a_Debug_configuration"></a> Hata ayıklama yapılandırmasını el ile ayarlamak için  
  
1.  Üzerinde **Görünüm** menüsünde tıklatın **özellik sayfaları**.  
  
2.  Tıklatın **yapılandırma özellikleri** düğüm zaten değilse açmak için  
  
3.  Seçin **genel**ve değeri ayarlayın **çıkış** için satır **hata ayıklama**.  
  
4.  Açık **C/C++** düğümü ve select **genel**.  
  
     İçinde **hata ayıklama** satır hata ayıklama bilgisi derleyici tarafından üretilen türünü belirtin. Seçtiğiniz değerler **Program veritabanı (/Zi)** veya **Düzenle ve devam (/ZI) için Program veritabanı**.  
  
5.  Seçin **en iyi duruma getirme**hem de **en iyi duruma getirme** satır, select **devre dışı (/ 0d)** aşağı açılan listeden.  
  
     Oluşturulan yönergeleri doğrudan kaynak koduna karşılık gelmediğinden en iyi duruma getirilmiş daha zor hata ayıklamak için kodudur. Yalnızca en iyi duruma getirilmiş kodda görüntülenen hata programınızı sahip fark ederseniz, bu ayarı etkinleştirmek ancak kaynak Windows'da gördükleri eşleşmeyebilir en iyi duruma getirilmiş kaynak ayrıştırılmış penceresinde gösterilen kodu kaynaklandığı unutmayın. Atlama gibi özellikleri yanlış kesme noktaları ve yürütme noktası göstermek olasıdır.  
  
6.  Açık **bağlayıcı** düğümü ve select **hata ayıklama**. İlk **Generate** satır, select **Evet (/ DEBUG)** aşağı açılan listeden. Hata ayıklama yaptığınız her zaman bu ayarlanır.  
  
 Daha fazla bilgi için bkz:[bir C++ hata ayıklama yapılandırması proje ayarları](../debugger/project-settings-for-a-cpp-debug-configuration.md).  
  
 [Bu konudaki](../debugger/debugging-preparation-visual-cpp-project-types.md#BKMK_In_this_topic)  
  
##  <a name="BKMK_Windows_Forms_Applications___NET_"></a> Windows Forms uygulamaları (.NET)  
 **Windows Forms uygulaması (.NET)** şablon oluşturur bir [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] Windows Forms uygulaması. Daha fazla bilgi için bkz: [nasıl yapılır: bir Windows uygulaması projesi oluşturduğunuzda](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
 Bu tür bir uygulamada hata ayıklama [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] yönetilen Windows Forms uygulamalarında benzer.  
  
 Proje şablonu ile bir Windows Forms projesi oluşturduğunuzda [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] hata ayıklama ve yayın yapılandırmaları için gereken ayarları otomatik olarak oluşturur. Gerekirse, bu ayarları değiştirebileceğiniz varsa  **\<proje adı > özellik sayfaları** iletişim kutusu. Daha fazla bilgi için bkz: [hata ayıklama ve dağıtım yapılandırmalarını](../debugger/how-to-set-debug-and-release-configurations.md).  
  
 Daha fazla bilgi için bkz: [bir C++ hata ayıklama yapılandırması proje ayarları](../debugger/project-settings-for-a-cpp-debug-configuration.md).  
  
 Bir Windows Forms uygulaması hata ayıklamak için başka bir uygulama dışında başlatmak için yoludur [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve ekleyebilir. Daha fazla bilgi için bkz: [bir programı çalıştıran veya birden çok programlara ekleme](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
 [Bu konudaki](../debugger/debugging-preparation-visual-cpp-project-types.md#BKMK_In_this_topic)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcı temel bilgileri](../debugger/debugger-basics.md)   
 [C++ hata ayıklama yapılandırması proje ayarları](../debugger/project-settings-for-a-cpp-debug-configuration.md)   
 [Çalışan bir Program veya birden çok programlara ekleme](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [Hata ayıklama ve yayın yapılandırmaları](../debugger/how-to-set-debug-and-release-configurations.md)   
 [Nasıl yapılır: bir Windows uygulaması projesi oluşturma](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)