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
ms.openlocfilehash: 5a34111ed357e38693b3cdb74c490b07cc8386b7
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/20/2018
ms.locfileid: "39178858"
---
# <a name="debugging-preparation-windows-forms-applications"></a>Hata Ayıklama Hazırlığı: Windows Forms Uygulamaları
Windows Forms proje şablonu, bir Windows Forms uygulaması oluşturur. Bu tür bir uygulamada hata ayıklama [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] oldukça basittir. Daha fazla bilgi için [bir Windows uygulaması projesi oluşturma](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
 Proje şablonuyla bir Windows Forms projesi oluşturduğunuzda [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] hata ayıklama ve yayın yapılandırmaları için gereken ayarları otomatik olarak oluşturur. Gerekirse, bu ayarları değiştirebilirsiniz. Bu ayarlar değiştirilebilir  **\<proje adı > özellik sayfaları** iletişim kutusu (**Projem** Visual Basic'te).  
  
 Daha fazla bilgi için [önerilen özellik ayarları](../debugger/managed-debugging-recommended-property-settings.md).  
  
 Aşağıdaki tabloda bir ek önerilen özellik ayarı görüntüler.  
  
### <a name="configuration-properties-in-debug-tab"></a>Hata ayıklama sekmesindeki yapılandırma özellikleri  
  
|**Özellik adı**|**Ayarı**|  
|-----------------------|-----------------|  
|**Başlatma eylemi**|-Kümesine **başlangıç projesi** çoğu zaman. Kümesine **harici program Başlat** başka bir yürütülebilir başlatmak istiyorsanız başlattığınızda hata ayıklama (genellikle DLL'lerinde hata ayıklama için).|  
  
 Windows Forms uygulamaları içinde hata ayıklama [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], veya zaten çalışan bir uygulamaya ekleme. Ekleme hakkında daha fazla bilgi için bkz. [çalışan işlemlere ekleme](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
### <a name="to-debug-a-c-f-or-visual-basic-windows-forms-application"></a>Bir C#, F # veya Visual Basic Windows Forms uygulamasında hata ayıklamak için  
  
1.  Projeyi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
2.  Kesme noktaları, gerektiği şekilde oluşturun.  
  
     Windows Forms uygulamaları, olay temelli olduğundan, kesme noktalarınız olay işleyici kodu veya olay işleyici kodu tarafından çağrılan yöntemler geçer. Kesme noktaları yerleştirmek için tipik olaylar şunlardır:  
  
    1.  ' A tıklayın, Enter vb. gibi bir denetim ile ilişkili olayları.  
  
    2.  Uygulama başlatma ve kapatma, yük, etkin, vb. gibi ilişkili olaylar.  
  
    3.  Odak ve doğrulama olayları.  
  
     Daha fazla bilgi için [Windows Forms'ta olay işleyicileri oluşturma](/dotnet/framework/winforms/creating-event-handlers-in-windows-forms).  
  
3.  Üzerinde **hata ayıklama** menüsünde tıklatın **Başlat**.  
  
4.  İçinde açıklanan teknikleri kullanarak hata ayıklama [hata ayıklayıcı temel bilgileri](../debugger/getting-started-with-the-debugger.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen kodda hata ayıklama](../debugger/debugging-managed-code.md)   
 [C#, F # ve Visual Basic proje türleri](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [Nasıl yapılır: kümesi hata ayıklama ve yayın yapılandırmaları](../debugger/how-to-set-debug-and-release-configurations.md)   
 [Hata ayıklama yapılandırması proje ayarları C#](../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Hata ayıklama yapılandırması proje ayarları bir Visual Basic](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [Çalıştırma işlemleri iliştirme](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [Windows Forms](/dotnet/framework/winforms/index)