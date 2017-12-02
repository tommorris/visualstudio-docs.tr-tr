---
title: "Unity için Visual Studio araçlarını kullanmaya başlama | Microsoft Docs"
ms.custom: 
ms.date: 04/07/2017
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: get-started-article
ms.assetid: 66b5b4eb-13b5-4071-98d2-87fafa4598a8
caps.latest.revision: "10"
author: conceptdev
ms.author: crdun
manager: crdun
ms.openlocfilehash: 1727330a559b5a9aed41ea9063f3394e01bc45ab
ms.sourcegitcommit: 5f5587a1bcf4aae995c80d54a67b4b461f8695f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/29/2017
---
# <a name="getting-started-with-visual-studio-tools-for-unity"></a>Unity için Visual Studio araçlarını kullanmaya başlama
Bu bölümde, Unity için Visual Studio araçlarını yükleme ve Unity projeniz Visual Studio ile çalışmak için yapılandırma hakkında bilgi edineceksiniz.  

> [!IMPORTANT]
>  Unity 5.2 proje kurulumu basitleştirir Unity 2.1 için Visual Studio Araçları için yerleşik destek ekler. Bu yararlanmak için Unity sürüm 5.2.0 gerekir ya da Windows ve sürüm 2.1 veya üzeri Unity için Visual Studio Araçları daha yüksek.  

## <a name="prerequisites"></a>Önkoşullar  
 Unity için Visual Studio Araçları kullanmak için ihtiyacınız vardır:  

-   Bir sürümünü **Visual Studio** uzantıları, Visual Studio Community, Professional, Premium veya Enterprise gibi destekler. Visual Studio Community'yi ücretsiz indirebilirsiniz.  

     [Visual Studio Community'yi indirin](http://www.visualstudio.com/downloads/download-visual-studio-vs)  

-   **Unity** sürüm 4.0.0 veya üzeri; **Unity** sürüm 5.2.0 veya Visual Studio Araçları Unity sürüm 2.1 veya üzeri için yerleşik destek yararlanmak için daha yüksek.  

     [Unity indirin](https://unity3d.com/get-unity/download)  

## <a name="install-visual-studio-tools-for-unity"></a>Unity için Visual Studio araçlarını yükleme  
 Karşıdan yükleyip Unity için Visual Studio Araçları Visual Studio Galerisi'nden. Visual Studio sürümünüz için doğru hizmet paketini yüklemeniz gerekir. VSTU Unity 5.2 veya üzeri için yerleşik destek yararlanmak sürüm 2.1 veya üzeri Unity için Visual Studio Araçları yüklediğinizden emin olun.  

-   Visual Studio 2015 topluluk, Visual Studio 2015 Professional veya Visual Studio 2015 Enterprise için:  

     [Unity için Visual Studio 2015 araçları yükle](https://visualstudiogallery.msdn.microsoft.com/8d26236e-4a64-4d64-8486-7df95156aba9)  

-   Visual Studio 2013 Community, Visual Studio 2013 Professional veya Visual Studio 2013 Premium için:  

     [Unity için Visual Studio 2013 araçları yükle](https://visualstudiogallery.msdn.microsoft.com/20b80b8c-659b-45ef-96c1-437828fe7cf2)  

-   Visual Studio 2012 Professional veya Visual Studio 2012 Premium için:  

     [Unity için Visual Studio 2012 araçları yükle](https://visualstudiogallery.msdn.microsoft.com/7ab11d2a-f413-4ed6-b3de-ff1d05157714)  

-   Visual Studio 2010 Professional veya Visual Studio 2010 Premium için:  

     [Unity için Visual Studio 2010 Araçları yükle](https://visualstudiogallery.msdn.microsoft.com/6e536faa-ce73-494a-a746-6a14753015f1)  

> [!NOTE]
>  Visual Studio Express sürümleri Unity için Visual Studio Araçları gibi uzantıları desteklemez. Visual Studio Community, Unity ve diğer uzantılar için Visual Studio Araçları destekleyen Visual Studio, boş bir sürümüdür. Çoğu kullanıcı için Visual Studio Community Express daha iyi bir seçimdir.  

> [!NOTE]
>  Visual Studio 2017 VSTU 3 Yükleyiciden seçebilirsiniz Unity iş yükü birlikte gelir.  

## <a name="your-first-unity-project-with-visual-studio-tools-for-unity"></a>İlk Unity projenizi Unity için Visual Studio Araçları ile  
 Gereksinim duyduğunuz her şeyi sahip olduğunuza göre Visual Studio ile ilk Unity projeniz için hazırsınız. Unity projenizi Unity hangi sürümlerinin bağlı olarak farklı ayardır ve Unity için Visual Studio Araçları yüklenir. Unity ve yüklediğiniz Unity için Visual Studio Araçları sürümü için aşağıdaki adımları izleyin.  

### <a name="unity-52-and-higher-requires-vstu-21-or-higher"></a>5.2 ve daha yüksek unity (VSTU 2.1 veya üstü gerektirir)  
 Unity 5.2 ile başlayarak, artık Visual Studio Araçları unitypackage projelerinizi aktarmanız gerekir. Projenizi bu unitypackage alıyorsa, Unity 5.2 göz ardı eder ve doğrudan Unity için Visual Studio Araçları yüklü konumundan yükler.  

#### <a name="1---create-a-unity-project"></a>1 - bir Unity projesi oluşturma  
 Zaten ile Unity deneyimli, yeni bir proje oluşturun ya da kendi yükler. Unity önceki bir sürümü ile Unity için Visual Studio Araçları kullanmak için Visual Studio Araçları unitypackage alınan bir proje yüklemekte olduğunuz, UnityVS dizin silerek bu kaldırmanızı öneririz.  

 Aksi takdirde, Unity için yeniyseniz, temel bir eğitici küçük başlatın. İle başlangıç örnek projeler ve Unity kendi oyun oluşturmak için gelen öğrenebilirsiniz dersleri öğreticiler bulmak için Unity öğrenin sayfasını ziyaret edin. Unity öğrenin sayfasında izleyin kolay öğreticileri birkaç farklı oyunlar için vardır.  

 [Öğreticiler - Unity bilgi sayfası](http://unity3d.com/learn/tutorials/modules)  

#### <a name="2---configure-unity-editor-to-use-visual-studio-tools-for-unity"></a>2 - Unity Düzenleyicisi'ni Unity için Visual Studio Araçları kullanmak için yapılandırın  
 Projenizi Unity için Visual Studio Araçları kullanmak üzere etkinleştirmek için Visual Studio, dış betik düzenleyicisi olarak ayarlamanız yeterlidir. Unity Düzenleyicisi'nde, ana menüdeki seçin **düzenleme, Tercihler**; ardından **Unity Tercihler** iletişim kutusunda, seçin **Harici Araçlar**. Ardından, ayarlayın **dış komut dosyası Düzenleyicisi** kullanmak istediğiniz Visual Studio sürümünü özelliğine (Unity için Visual Studio Araçları, Visual Studio'nun bu sürümü için de yüklenmelidir) ve emin olun **Düzenleyicisiekleme** özelliği ayarlanmış.  

 Unity şu anda etkin için Visual Studio Araçları için yerleşik destekleyen emin olmak için bkz: **hakkında Unity** iletişim. Ana menüde Unity Düzenleyicisi'nde seçin **hakkında Unity Yardımı.** Unity için Visual Studio Araçları yüklü olduğunu ve doğru şekilde yapılandırıldığını varsa sol alt köşesinde görüntülenen bir ileti görürsünüz **hakkında Unity** iletişim.  

 Son olarak, bir yapı hedef aracılığıyla ayarladığınızdan emin olun **Build Settings** sayfası ve, **komut dosyasında hata ayıklama** etkinleştirilir.  

 ![Hata ayıklama için Unity derleme ayarlarını yapılandırın. ] (../cross-platform/media/vstu_debugging_build_settings.png "vstu_debugging_build_settings")  

#### <a name="3---launch-visual-studio-from-the-unity-editor"></a>3 - Visual Studio'yu Unity Düzenleyicisi'nden başlatın  
 Unity 5.2 ile başlayan **Visual Studio Araçları** uzantısı menüsü Visual Studio'yu başlatın veya Unity için Visual Studio Araçları yapılandırmak için artık gerekli. Visual Studio Dış betik düzenleyicisi olarak yapılandırıldıktan sonra bunun yerine, yalnızca Visual Studio'da Unity Düzenleyicisi'ni ve kodunuzu betik dosyasından açılacak seçin.  

### <a name="previous-versions-of-unity-pre-52"></a>Önceki sürümlerini Unity (5.2 öncesi)  
 Unity 5.2 önce Unity için Visual Studio Araçları için yerleşik destek yoktu. Bunun yerine, Visual Studio Araçları unitypackage almak ve Unity için Visual Studio Araçları kullanmak için diğer proje ayarlarını yapılandırmak için her proje gerekiyordu.  

#### <a name="1---create-a-unity-project"></a>1 - bir Unity projesi oluşturma  
 Zaten ile Unity deneyimli, yeni bir proje oluşturun ya da kendi yükler. Yeni bir proje başlatıyorsanız oluşturduğunuzda Visual Studio Araçları unitypackage içeri aktarın.  

 Aksi takdirde, Unity için yeniyseniz, temel bir eğitici küçük başlatın. İle başlangıç örnek projeler ve Unity kendi oyun oluşturmak için gelen öğrenebilirsiniz dersleri öğreticiler bulmak için Unity öğrenin sayfasını ziyaret edin. Unity öğrenin sayfasında izleyin kolay öğreticileri birkaç farklı oyunlar için vardır.  

 [Öğreticiler - Unity bilgi sayfası](http://unity3d.com/learn/tutorials/modules)  

#### <a name="2---configure-unity-editor-to-use-visual-studio-tools-for-unity"></a>2 - Unity Düzenleyicisi'ni Unity için Visual Studio Araçları kullanmak için yapılandırın  
 Varolan bir Unity projeden başlatıyorsanız veya proje oluşturduğunuzda, Visual Studio Araçları unitypackage içe alamadık, unitypackage şimdi içeri aktarmanız gerekir. Ana menüde Unity Düzenleyicisi'nde seçin **varlıklar, içeri aktarma paketini, Visual Studio 2015 Araçları** (Visual Studio yüklü olan sürümü için bir seçenek görmeniz gerekir).  

 ![VSTU paket Unity projenize alın. ] (../cross-platform/media/vstu_configure_unity_import_vstu.png "vstu_configure_unity_import_vstu")  

 Son olarak, bir yapı hedef aracılığıyla ayarladığınızdan emin olun **Build Settings** sayfası ve, **komut dosyasında hata ayıklama** etkinleştirilir.  

 ![Hata ayıklama için Unity derleme ayarlarını yapılandırın. ] (../cross-platform/media/vstu_debugging_build_settings.png "vstu_debugging_build_settings")  

#### <a name="3---launch-visual-studio-from-unity-editor"></a>3 - Visual Studio'yu Unity Düzenleyicisi'nden başlatın  
 Son adım, Unity Visual Studio başlatmaktır. Bu projeniz için bir Visual Studio çözümü oluşturur ve ardından Visual Studio'da açar.  

 Unity Düzenleyicisi'nde, ana menüdeki seçin **Visual Studio Araçları, Visual Studio'da açın**.  

 ![Unity projenizi Visual Studio'da açın. ] (../cross-platform/media/vstu_configure_open_in_visual_studio.png "vstu_configure_open_in_visual_studio")  

## <a name="next-steps"></a>Sonraki adımlar  

 Çalışmak ve Unity projenizi Visual Studio'da hata ayıklama öğrenmek için bkz: [Unity için Visual Studio araçları kullanarak](../cross-platform/using-visual-studio-tools-for-unity.md).  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Unity giriş sayfası](http://unity3d.com)
