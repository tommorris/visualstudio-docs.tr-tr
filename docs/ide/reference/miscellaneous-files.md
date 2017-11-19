---
title: "Çeşitli dosyalar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.newfile
- VS.OpenWith
- MiscellaneousFilesProject
helpviewer_keywords:
- solutions, miscellaneous files
- builds [Visual Studio], miscellaneous files
- standalone files
- Solution Explorer, miscellaneous files
- Miscellaneous Files folder
- files [Visual Studio], outside of containers
- files [Visual Studio], Miscellaneous Files folder
ms.assetid: 5b96640b-8efe-48a4-8d0a-1ae3f9587e44
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 831d0f60c992324c81cb1366ac28b3e3f1b066ad
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="miscellaneous-files"></a>Çeşitli Dosyalar
Kullanmak istediğiniz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] bağımsız olarak bir projeden veya bir çözüm dosyalarda çalışmak için düzenleyiciler. Açık bir çözüm sahip olsa da, açın ve bir çözüm ya da bir proje eklemeden dosyaları değiştirin. Çeşitli dosyalar bağımsız olarak kapsayıcılardan çalışmak istediğiniz dosya adı verilir. Çeşitli dosyalar çözümler ve projeler için dış, derlemelerde eklenmez ve kaynak denetimi altında bir çözümüyle eklenemez.  
  
 Dosyaları bağımsız olarak bir kapsayıcı açma çeşitli nedenlerden dolayı kullanışlıdır. Proje tabanlı bir çözümdür ancak geliştirmek için çözümün geliştirme tam sayı olmamasına karşın görüntülemek istediğiniz bir dosyanız olabilir. Yaygın örnek geliştirme notları veya yönergeleri, veritabanı şeması ve kod klipleri verilebilir. Ayrıca, tek başına bir dosya oluşturmak isteyebilirsiniz.  
  
 ![Çözüm projeleri](../../ide/reference/media/projects_solutions_misc.gif "Projects_Solutions_Misc")  
  
 Klasör seçenekleri etkinleştirilirse Çözüm Gezgini dosyaları için çeşitli dosyalar klasörü görüntüleyebilirsiniz. Seçenekler arasında ayarlanabilir [belgeler, ortam, Seçenekler iletişim kutusu](../../ide/reference/documents-environment-options-dialog-box.md). Çeşitli dosya kapattıktan sonra bir seçenek için de etkinleştirilmediği sürece herhangi bir belirli çözüm veya proje ile ilişkili değil.  
  
 Çeşitli dosyalar klasörü dosyaları bağlantılar olarak temsil eder. Bir çözümü açtığınızda, bu klasör bir çözümün bir parçası olmasa da, bazı veya tüm çözüm son kapatıldığında açıldı çeşitli dosyalar, klasör ayarlarını bağlı olarak yeniden açılır.  
  
> [!NOTE]
>  Çeşitli dosyalar klasörü görünmez dosyaların bazıları şunlardır: .zip dosyaları gibi IDE içinden değiştirilemiyor dosyaları ve .doc dosyaları. IDE harici bir düzenleyici yalnızca değiştirilebilir dosyaları izlemek değil.  
  
## <a name="commands-available-in-the-ide"></a>IDE içinde kullanılabilen komutları  
 Menüleri, araç çubukları ve dosya biçimine bağlı değişiklik içerdikleri komutları, açın. Örneğin, bir metin dosyası açtığınızda, metin düzenleyici araç çubuğu görüntülenir ve kendi komutları kullanılabilir. Ardından bir XML Şeması dosyası açarsanız, XML Şeması araç çubuğu görüntülenir. XML Şeması düzenlerken, metin düzenleyici araç çubuğunun komutları (veya araç) kullanılamaz. XML Şeması etkin pencereyi ve bu nedenle, geçerli seçim bağlamı vardır. Proje dosyası ile çeşitli dosya arasında geçiş yaptığınızda, tüm proje ile ilgili komutları kaybolur ve yalnızca o çeşitli dosyaya doğrudan ilgili görünür.  
  
## <a name="folder-display-options"></a>Klasör görünen seçenekleri  
 Çeşitli dosyaları açmadıysanız olsa bile klasör görünür çeşitli klasörü için görüntüleme seçeneklerini ayarlayabilirsiniz. Çözüm dosyası çeşitli dosyaların listesini kalıcı olarak yönetmez. Dosyaların en son kullanılan kullanıcı başına (MRU) listesini unutmayın imkan tanıyan isteğe bağlı bir özellik kullanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çözümler ve projeler](../../ide/solutions-and-projects-in-visual-studio.md)   
 [Belgeler, ortam, Seçenekler iletişim kutusu](../../ide/reference/documents-environment-options-dialog-box.md)