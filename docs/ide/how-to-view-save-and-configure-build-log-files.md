---
title: 'Nasıl yapılır: görünümü, kaydetme ve derleme günlüğü dosyalarını yapılandırma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
ms.assetid: 75d38b76-26d6-4f43-bbe7-cbacd7cc81e7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: aa0a4f458f264bdbdd1f96b414d0cc689bcfeb06
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-view-save-and-configure-build-log-files"></a>Nasıl yapılır: görünümü, kaydetme ve derleme günlüğü dosyalarını yapılandırma
Visual Studio IDE içinde olan bir projeyi derleme sonra bu yapıyı hakkındaki bilgileri görüntüleyebilirsiniz **çıkış** penceresi. Bu bilgileri kullanarak, örneğin, bir derleme hatasını gidermek olabilir. C++ projeleri için aynı bilgileri de görüntüleyebilirsiniz bir *.txt* oluşturulan ve otomatik olarak kaydettiğiniz dosya. Yönetilen kod projelerde kopyalayın ve bilgileri yapıştırın **çıkış** penceresine bir *.txt* dosya ve dosyayı kaydedin. IDE, hangi türde bilgilerin her derleme hakkında görüntülemek istediğinizi belirtmek için de kullanabilirsiniz.  
  
 MSBuild kullanarak proje her türlü derleme, oluşturabileceğiniz bir *.txt* yapı hakkındaki bilgileri kaydetmek için dosya. Daha fazla bilgi için bkz: [elde yapı günlükleri](../msbuild/obtaining-build-logs-with-msbuild.md).  
  
### <a name="to-view-the-build-log-file-for-a-c-project"></a>C++ projesi için yapılandırma günlük dosyasını görüntülemek için  
  
1.  İçinde **Windows Explorer** veya **dosya Gezgini**, aşağıdaki dosyayı açın:  *\\...\Visual Studio \<sürüm\>\Projects\\ < ProjectName\>\\< ProjectName\>\Debug\\< ProjectName\>.txt*  
  
### <a name="to-create-a-build-log-file-for-a-managed-code-project"></a>Yönetilen kod projesi için bir yapı günlük dosyası oluşturmak için  
  
1.  Menü çubuğunda seçin **yapı** > **yapı çözümü**.  
  
2.  İçinde **çıkış** penceresinde, yapı bilgileri vurgulayın ve ardından kopyalayın **Pano**.  
  
3.  Gibi bir metin düzenleyicisinde açıp **not defteri**bilgileri dosyaya yapıştırın ve dosyayı kaydedin.  
  
### <a name="to-change-the-amount-of-information-included-in-the-build-log"></a>Yapı günlüğüne dahil bilgi miktarını değiştirmek için  
  
1.  Menü çubuğunda seçin **Araçları** > **seçenekleri**.  
  
2.  Üzerinde **projeler ve çözümler** sayfasında, **derleme ve çalıştırma** sayfası.  
  
3.  İçinde **MSBuild Proje yapı çıktı ayrıntı** listesinde, aşağıdaki değerlerden birini seçin ve ardından **Tamam** düğmesi.  
  
    |Ayrıntı düzeyi|Açıklama|  
    |---------------------|-----------------|  
    |**Sessiz**|Yalnızca derleme özetini görüntüler.|  
    |**en az**|Derleme ve hataları, uyarıları ve ayrılır iletileri özetini yüksek oranda önemli olarak görüntüler.|  
    |**Normal**|Yapı özetini görüntüler; hataları, uyarıları ve yüksek oranda önemli olarak sınıflandırılır iletileri; ve yapı ana adımlar. Bu düzeyde ayrıntı en sık kullanacaksınız.|  
    |**Ayrıntılı**|Yapı özetini görüntüler; hataları, uyarıları ve yüksek oranda önemli olarak sınıflandırılır iletileri; tüm adımlar yapının; ve normal önem itibariyle kategorilere iletileri.|  
    |**Tanılama**|Derleme için kullanılabilir tüm verileri görüntüler. Özel derleme kodlarıyla ve diğer yapı sorunlarını hata ayıklama yardımcı olmak için bu düzeyde ayrıntı kullanabilirsiniz.|  
  
     Daha fazla bilgi için bkz: [Seçenekler iletişim kutusu, projeler ve çözümler, derleme ve çalıştırma](../ide/reference/options-dialog-box-projects-and-solutions-build-and-run.md) ve <xref:Microsoft.Build.Framework.LoggerVerbosity>.  
  
    > [!IMPORTANT]
    >  Proje, değişikliklerin etkili olması yeniden oluşturmalısınız **çıkış** penceresi (tüm projeleri) ve  *<ProjectName>.txt* dosyası (yalnızca C++ projeleri).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Yapı günlükleri alın](../msbuild/obtaining-build-logs-with-msbuild.md)   
 [Derleme ve projeler ve çözümler Visual Studio'da Temizle](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)   
 [Derleme ve oluşturma](../ide/compiling-and-building-in-visual-studio.md)