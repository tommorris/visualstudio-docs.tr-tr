---
title: "Office çözümlerinin işbirlikçi geliştirme | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office applications [Office development in Visual Studio], collaborative development
- Office development in Visual Studio, collaboration
- source control [Office development in Visual Studio]
- collaborative development [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 3b69eccc3f6c140c44bff3b2d3d24e33914cae84
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="collaborative-development-of-office-solutions"></a>Office Çözümlerinin İşbirlikçi Geliştirmesi
  Birden çok geliştiricilerin Office projesinde, diğer Visual Studio projelerinde birlikte aynı şekilde çalışabilir. Office farklı konumlarda yüklü olsa bile visual Studio Microsoft Office yüklemesini her bilgisayarda doğru bulur. Ancak, farkında olmanız gereken bazı önemli noktalar vardır.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="debug-properties-are-not-shared"></a>Hata ayıklama özellikleri paylaşılmayan  
 Hata ayıklama özellikleri paylaşılamaz kaynak denetimi altında birden çok kullanıcı. Visual Basic ve Visual C# projeleri, kullanıcıya özel dosyada hata ayıklama özelliklerini depolar (*ProjectName*. vbproj.user veya *ProjectName*. csproj.user), ve bu dosya kaynak denetimi altında değil. Birden çok kişi hata ayıklama, her kişi hata ayıklama özelliklerini el ile girmeniz gerekir.  
  
 Proje kaynak denetiminde yerine ağ paylaşımında barındırılıyorsa çözümü açın ve derleme sınamak birlikte çalışan geliştiricilerin etkinleştirmek için bazı ek adımlar izlenmelidir.  
  
## <a name="source-control-requires-checking-out-all-files"></a>Kaynak Denetimi tüm dosyaları kullanıma alma gerektirir  
 Projeler için kaynak denetimi kullanırsanız, bir kod dosyasında altındaki tüm dosyaların kullanıma **Çözüm Gezgini** (ThisDocument, ThisWorkbook veya ThisAddIn kod dosyaları gibi) kod dosyası her değiştirdiğinizde bile Varsayılan olarak gizli dosyalar. Yalnızca üst düzey kod dosyasını kullanıma işaretlerseniz, yaptığınız değişiklikler kaybolabilir.  
  
 Yaptığınız değişiklikleri yaptıktan sonra tüm dosyalar geri denetleyin. Projelerdeki gizli kod dosyaları hakkında daha fazla bilgi için bkz: [Visual Studio ortamında Office projeleri](../vsto/office-projects-in-the-visual-studio-environment.md).  
  
## <a name="security-for-informal-collaboration-on-a-network"></a>Bir ağ üzerinde resmi olmayan işbirliği için güvenlik  
 Bir ağ konumundaki tüm belge düzeyi çözümleri (gibi \\ \\ *Servername*\\*Sharename*), tam konum eklenmelidir birlikte çalıştığınız Microsoft Office uygulamasında güvenilir klasör listesi. Ana klasörü altında alt dizinleri içerir veya özel olarak hata ayıklama ekleyin ve yapı klasörlerini güvenilir klasör listesine seçeneğini seçin. Bunun nasıl yapılacağı hakkında daha fazla bilgi için bkz: [belgelere güven verme](../vsto/granting-trust-to-documents.md).  
  
 Derleme zamanında otomatik olarak oluşturulan geçici sertifikalar parolalarla değil. Sertifikalar geliştiricinin oturum açma adı ve diğer kişisel bilgileri içerir. Geçici sertifikalar tarafından imzalanan özelleştirmeler dağıtıyorsanız, diğerlerinin bu bilgilere erişmek olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümleri güvenliğini sağlama](../vsto/securing-office-solutions.md)   
 [Tasarlama ve Office çözümleri oluşturma](../vsto/designing-and-creating-office-solutions.md)   
 [Office Çözümleri Oluşturma](../vsto/building-office-solutions.md)  
  
  