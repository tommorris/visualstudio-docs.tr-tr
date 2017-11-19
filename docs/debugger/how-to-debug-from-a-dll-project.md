---
title: "Nasıl yapılır: DLL projesinde hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 05/24/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- DLL projects, debugging
- debugging DLLs
- DLLs, debugging projects
- debugging [Visual Studio], DLLs
ms.assetid: 40a94339-d3f7-4ab9-b8a1-b8cf82942f44
caps.latest.revision: "30"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 371c48282b2f775833287046ed9810f0cbc8f69e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-debug-from-a-dll-project-in-visual-studio"></a>Nasıl yapılır: Visual Studio'da bir DLL projeden hata ayıklama
DLL projesinde hata ayıklamak için bir çağrı yapan uygulamanın DLL projesi Proje özelliklerini belirtmek için yoludur ve ardından DLL projesi kendisini hata ayıklama başlayabilirsiniz. Bu yöntem çalışmak uygulama DLL çağırmanız gerekir ve DLL burada uygulama bekler bulmak için konumda olması gerekir (Aksi takdirde uygulama DLL farklı bir sürümünü bulun ve bunun yerine, yükleme ve noktalarınıza isabet olmaz). DLL'lerde hata ayıklama diğer yöntemleri için bkz: [DLL projelerinde hata ayıklama](../debugger/debugging-dll-projects.md).
  
Yönetilen DLL yerel kod tarafından çağrılır ve her ikisi de hata ayıklama istiyorsanız, bu proje özellikleri'nde belirtebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: karışık modda hata ayıklama](../debugger/how-to-debug-in-mixed-mode.md).   

C++ özellik sayfaları, Düzen ve C# ve Visual Basic özellik sayfaları içerikten farklılık gösterir. 
  
### <a name="to-specify-the-calling-application-in-a-c-project"></a>Çağrı yapan uygulamanın C++ projesinde belirtmek için  
  
1.  Proje düğümüne sağ tıklayın **Çözüm Gezgini** seçip **özellikleri**.  
  
2.  Olduğundan emin olun **yapılandırma** alan pencerenin üstündeki ayarlanmış **hata ayıklama**. 

    A **hata ayıklama** yapılandırma bu yöntem için gereklidir. 
  
3.  Git **yapılandırma özellikleri > hata ayıklama**.  
  
4.  İçinde **başlatmak için hata ayıklayıcı** listesinde, seçin **yerel Windows hata ayıklayıcı** veya **uzak Windows hata ayıklayıcı**.  
  
5.  İçinde **komutu** veya **uzak komut** kutusunda, çağıran uygulama (örneğin, bir .exe dosyası) tam yol adını ekleyin.

    ![Özellikler penceresini hata ayıklama](../debugger/media/dbg-debugging-properties-dll.png "DebuggingPropertiesWindow")  
  
6.  Tüm gerekli bir programı bağımsız değişkenleri eklemek **komut bağımsız değişkenleri** kutusu.  
  
### <a name="to-specify-the-calling-application-in-a-c-or-visual-basic-project"></a>Bir C# veya Visual Basic projesinde çağrı yapan uygulamanın belirtmek için  
  
1.  Proje düğümüne sağ tıklayın **Çözüm Gezgini** seçip **özellikleri**ve ardından **hata ayıklama** sekmesi.

2.  Olduğundan emin olun **yapılandırma** alan pencerenin üstündeki ayarlanmış **hata ayıklama**.

3.  (.NET framework) Seçin **başlangıç dış program**, çağıran uygulama tam yol adını ekleyin.

4.  (.NET çekirdek) Seçin **yürütülebilir** gelen **başlatma** listesinde ve çağıran uygulamada tam yol adını eklemek **yürütülebilir** alan. 
  
     Dış programın komut satırı bağımsız değişkenleri eklemek gerekiyorsa, bunları ekleyin **komut satırı bağımsız değişkenleri** (veya **uygulama bağımsız değişkenleri**) alan.

    ![Özellikler penceresini hata ayıklama](../debugger/media/dbg-debugging-properties-dll-csharp.png "DebuggingPropertiesWindow") 

5.  Gerekiyorsa, ayrıca uygulamanın URL olarak çağırabilirsiniz. (Yerel bir ASP.NET uygulaması tarafından kullanılan yönetilen DLL hata ayıklama, bunu yapmak isteyebilirsiniz.)  
  
     Altında **eylemi Başlat**seçin **başlangıç tarayıcı URL ile:** radyo düğmesinin ve URL'yi girin.
  
### <a name="to-start-debugging-from-the-dll-project"></a>DLL projesinde hata ayıklamayı başlatmak için  
  
1.  DLL projesinde kesme noktalarını ayarlayın. 

2.  DLL projesine sağ tıklayın ve seçin **başlangıç projesi olarak ayarla**. 

    (Ayrıca olduğundan emin olun **çözümleri yapılandırma** alan ayarlanmış hala **hata ayıklama**.)   
  
3.  Hata Ayıklamayı Başlat (F5 tuşuna basın, yeşil ok simgesine tıklayın veya tıklatın **hata ayıklama > hata ayıklamayı Başlat**).

    Kesme noktaları DLL dosyanızda karşılaşır. Kesme noktası isabet mümkün değilse, DLL çıkış yaptığınızdan emin olun (varsayılan olarak, **project\Debug** klasör) çağıran uygulama bulmak bekler bir konumda bulunuyor.
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DLL projelerinde hata ayıklama](../debugger/debugging-dll-projects.md)   
 [Proje ayarları için C# hata ayıklama yapılandırmaları](../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Hata ayıklama yapılandırması proje ayarları bir Visual Basic](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [C++ hata ayıklama yapılandırması proje ayarları](../debugger/project-settings-for-a-cpp-debug-configuration.md)