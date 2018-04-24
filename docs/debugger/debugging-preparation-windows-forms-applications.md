---
title: 'Hata ayıklama hazırlığı: Windows Forms uygulamaları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging Windows applications
- Windows applications, debugging
- debugging [Visual Studio], Windows applications
- debugging [C#], Windows applications
- debugging [Visual Basic], Windows applications
ms.assetid: 7092ee7f-8378-4def-aef8-1695bd97cf14
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bde2b6d2885a83057a0211f6da4f9e4ff65ef46f
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="debugging-preparation-windows-forms-applications"></a>Hata Ayıklama Hazırlığı: Windows Forms Uygulamaları
Windows Forms proje şablonu, bir Windows Forms uygulaması oluşturur. Bu tür bir uygulamada hata ayıklama [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] basittir. Daha fazla bilgi için bkz: [Windows uygulaması projesi oluşturma](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
 Proje şablonu ile bir Windows Forms projesi oluşturduğunuzda [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] hata ayıklama ve yayın yapılandırmaları için gereken ayarları otomatik olarak oluşturur. Gerekirse, bu ayarları değiştirebilirsiniz. Bu ayarları değiştirilebilir  **\<proje adı > özellik sayfaları** iletişim kutusu (**My proje** Visual Basic'te).  
  
 Daha fazla bilgi için bkz: [önerilen özellik ayarları](../debugger/managed-debugging-recommended-property-settings.md).  
  
 Aşağıdaki tabloda bir ek önerilen özellik ayarı görüntüler.  
  
### <a name="configuration-properties-in-debug-tab"></a>Hata ayıklama sekmesi yapılandırma özellikleri  
  
|**Özellik adı**|**Ayarı**|  
|-----------------------|-----------------|  
|**Eylemi Başlat**|-Kümesine **başlangıç projesi** çoğu zaman. Kümesine **başlangıç dış program** başka bir yürütülebilir başlatmak istiyorsanız başlattığınızda hata ayıklama (genellikle DLL'lerde hata ayıklama için).|  
  
 Gelen Windows Forms uygulamalarında hata ayıklama [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], ya da zaten çalışan bir uygulamaya ekleyerek. Ekleme hakkında daha fazla bilgi için bkz: [eklemek için çalışan işlemler](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
### <a name="to-debug-a-c-f-or-visual-basic-windows-forms-application"></a>Bir C#, F # veya Visual Basic Windows Forms uygulaması hata ayıklamak için  
  
1.  Projeyi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
2.  Kesme noktaları gerektiği şekilde oluşturun.  
  
     Windows Forms uygulamaları olay kaynaklı olduğundan, kesme noktaları olay işleyici kodu veya olay işleyici koduyla adlı yöntemler gidin. Kesme noktaları yerleştirileceği tipik olaylar şunlardır:  
  
    1.  ' I tıklatın, Enter vb. gibi bir denetim ile ilişkili olaylar.  
  
    2.  Uygulama başlatma ve kapatma, yükleme, vb. etkinleştirildi ile ilişkili olaylar.  
  
    3.  Odak ve doğrulama olayları.  
  
     Daha fazla bilgi için bkz: [Windows Forms'ta olay işleyicileri oluşturma](/dotnet/framework/winforms/creating-event-handlers-in-windows-forms).  
  
3.  Üzerinde **hata ayıklama** menüsünde tıklatın **Başlat**.  
  
4.  İçinde açıklanan teknikleri kullanarak hata ayıklama [hata ayıklayıcı temel bilgileri](../debugger/debugger-basics.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen kodda hata ayıklama](../debugger/debugging-managed-code.md)   
 [C#, F # ve Visual Basic proje türleri](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [Nasıl yapılır: kümesi hata ayıklama ve yayın yapılandırmaları](../debugger/how-to-set-debug-and-release-configurations.md)   
 [Proje ayarları için C# hata ayıklama yapılandırmaları](../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Hata ayıklama yapılandırması proje ayarları bir Visual Basic](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [Çalıştırma işlemine iliştirme](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [Windows Forms](/dotnet/framework/winforms/index)