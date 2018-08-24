---
title: 'Nasıl yapılır: DLL projesinde hata ayıklama | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- DLL projects, debugging
- debugging DLLs
- DLLs, debugging projects
- debugging [Visual Studio], DLLs
ms.assetid: 40a94339-d3f7-4ab9-b8a1-b8cf82942f44
caps.latest.revision: 33
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9a3ab401c4631da22f2afc84d2e1ec763258fc42
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694863"
---
# <a name="how-to-debug-from-a-dll-project"></a>Nasıl Yapılır: DLL Projesinde Hata Ayıklama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: DLL projesinde hata ayıklama](https://docs.microsoft.com/visualstudio/debugger/how-to-debug-from-a-dll-project).  
  
DLL projesinde hata ayıklamayı başlatmak için proje özelliklerinde çağıran uygulama belirtmeniz gerekir. C++ özellik sayfaları, düzeni ve içerikleri C# ve Visual Basic özellik sayfaları farklılık gösterir.  
  
 Yönetilen bir DLL'yi yerel kod tarafından çağrılır ve her ikisi de hata ayıklamak istiyorsanız, proje özelliklerinde belirtebilirsiniz. Daha fazla bilgi için [nasıl yapılır: karışık modda hata ayıklama](../debugger/how-to-debug-in-mixed-mode.md).  
  
> [!NOTE]
>  Visual Studio'nun Express sürümlerinde, bir dış çağıran uygulama belirtemezsiniz. Bunun yerine, çözüme bir yürütülebilir proje ekleyin için başlangıç projesi olarak ayarla ve yöntemler DLL dosyanız içinde yürütülebilir projeden çağırın.  
  
### <a name="to-specify-the-calling-application-in-a-c-project"></a>Bir C++ projesinde çağıran uygulama belirtmek için  
  
1.  ' Nde proje düğümüne sağ **Çözüm Gezgini** seçip **özellikleri**. Git **hata ayıklama** sekmesi.  
  
2.  Emin olun **yapılandırma** pencerenin üst kısmındaki alanı **hata ayıklama**.  
  
3.  Git **yapılandırma özellikleri / hata ayıklama**.  
  
4.  İçinde **başlatmak için hata ayıklayıcı** listesinde **yerel Windows hata ayıklayıcı** veya **uzaktan Windows hata ayıklayıcı**.  
  
5.  İçinde **komut** veya **uzaktan komut** kutusunda, uygulama tam yol adını ekleyin.  
  
6.  Tüm gerekli program bağımsız değişkenleri eklemek **komut satırı bağımsız değişkenlerini** kutusu.  
  
### <a name="to-specify-the-calling-application-in-a-c-or-visual-basic-project"></a>Bir C# veya Visual Basic projesinde çağıran uygulama belirtmek için  
  
1.  ' Nde proje düğümüne sağ **Çözüm Gezgini** seçip **özellikleri**. Git **hata ayıklama** sekmesi.  
  
     Seçin **harici program Başlat**, programın çalışması için tam yol adını ekleyin.  
  
     Dış programın komut satırı bağımsız değişkenleri eklemeniz gerekiyorsa, bunları eklemek **komut satırı bağımsız değişkenleri** alan.  
  
2.  Ayrıca, bir uygulamanın bir URL olarak çağırabilirsiniz. (Yerel bir ASP.NET uygulaması tarafından kullanılan yönetilen bir DLL'yi hata ayıklaması yapıyorsanız, bunu yapmak isteyebilirsiniz.)  
  
     Altında **başlatma eylemi**seçin **Başlat tarayıcı URL:** radyo düğmesini ve URL'sini girin.  
  
### <a name="to-start-debugging-from-the-dll-project"></a>DLL projesinde hata ayıklamayı başlatmak için  
  
1.  Kesme noktalarını gerektiği gibi ayarlayın.  
  
2.  Hata Ayıklamayı Başlat (F5 tuşuna basın, yeşil oka tıklayın veya tıklayın **hata ayıklama / hata ayıklamayı Başlat**).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DLL projelerinde hata ayıklama](../debugger/debugging-dll-projects.md)   
 [Hata ayıklama yapılandırması proje ayarları C#](../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Hata ayıklama yapılandırması proje ayarları bir Visual Basic](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [C++ hata ayıklama yapılandırması proje ayarları](../debugger/project-settings-for-a-cpp-debug-configuration.md)


