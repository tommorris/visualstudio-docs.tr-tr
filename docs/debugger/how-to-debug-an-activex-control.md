---
title: "Nasıl yapılır: bir ActiveX denetimi hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.controls.debug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- testing [Visual Studio], test containers
- ActiveX control container debugging [Visual Studio]
- debugging ActiveX controls
- data-bound controls, ActiveX
- test container
- containers, specifying for debug sessions
- ActiveX controls, debugging
- testing [Visual Studio], ActiveX controls
ms.assetid: bbc02cf7-a7e6-44fe-99af-87a43e1d7251
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 11d29d2d8a5ebf4774f3b71ea72a1dd9bc58cbd0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-debug-an-activex-control"></a>Nasıl Yapılır: ActiveX Denetiminde Hata Ayıklama
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için Araçlar menüsünden içeri ve dışarı aktarma ayarları seçin. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
 ActiveX denetimi hata ayıklamak için bir kapsayıcı (çalıştırmak denetimi için yürütülebilir) belirtmeniz gerekir.  
  
### <a name="to-specify-a-container-for-the-debug-session"></a>Hata ayıklama oturumu için bir kapsayıcı belirtmek için  
  
1.  Çözüm Gezgini'nde proje seçin.  
  
2.  Gelen **Görünüm** menüsünde seçin **özellik sayfaları**.  
  
3.  İçinde **proje özellik sayfalarını** açık iletişim kutusunu **yapılandırma özellikleri** klasörü ve select **hata ayıklama**.  
  
4.  Altında **hata ayıklama** kategori bulun **komutu** özelliği.  
  
5.  Kapsayıcı için yol adı belirtin. Örneğin, C:\Program Files\Internet Explorer\IEXPLORE. EXE.  
  
6.  Internet Explorer kapsayıcı olarak belirtirseniz ve etkin masaüstünün kullanıyorsanız, yazın `/new` içinde **komut bağımsız değişkenleri** kutusu.  
  
7.  **Tamam**'ı tıklatın.  
  
     Bir kapsayıcıda belirtmezseniz **proje özellik sayfalarını** iletişim kutusunda belirtebilirsiniz kapsayıcı hata ayıklama başladığınızda. Hata ayıklamayı başlatmak için bir yürütme komutu seçtiğinizde [oturumu için yürütülebilir hata ayıklama iletişim kutusu](../debugger/executable-for-debugging-session-dialog-box.md) görüntülenir. İletişim kutusunda kapsayıcı yol adını belirtin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ActiveX denetimleri](/cpp/mfc/activex-controls)   
 [Test kapsayıcısı ile özellikleri ve olayları test etme](/cpp/mfc/testing-properties-and-events-with-test-container)   
 [COM ve ActiveX hata ayıklaması](../debugger/com-and-activex-debugging.md)   
 [Visual Studio'da hata ayıklama](../debugger/index.md)  
 [Hata ayıklayıcı özelliği turu](../debugger/debugger-feature-tour.md)