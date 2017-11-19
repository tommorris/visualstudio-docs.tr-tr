---
title: "Nasıl yapılır: belirli DLL'ler için araçları sınırlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: performance tools, runtime profiling control window
ms.assetid: 17c5996f-e3d0-4e44-b175-52b401b0f2d5
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 59d24a6cc67429fb6c0231f9487d80abe91de965
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-limit-instrumentation-to-specific-dlls"></a>Nasıl yapılır: Belirli DLL'ler için İzleme Sınırlama
Profil Oluşturucu izleme yöntemini kullanarak, bir uygulamada bir veya daha fazla DLL'ler için profil oluşturma veri koleksiyonunu sınırlayabilirsiniz. Bir uygulama bir veya daha fazla DLL'lerde profil için hedefleri olarak .dll dosyalarını içeren bir performans oturumu oluşturun. Projelerinde olarak profil istediğiniz DLL'leri belirtebilirsiniz bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çözüm veya bağımsız ikili dosyaları olarak.  
  
### <a name="to-limit-instrumentation-to-specific-dlls-in-a-visual-studio-solution"></a>Visual Studio çözümünde belirli DLL'ler için araçları sınırlamak için  
  
1.  DLL'de içeren çözümü açmak [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)].  
  
2.  Üzerinde **Çözümle** menüsünde, select **başlatma performans Sihirbazı**.  
  
3.  Seçin **Araçları** 'ye tıklayın ve profil oluşturma yöntemi olarak **sonraki**.  
  
4.  Gelen **aşağıdaki kullanılabilir hedefleri hangisinin profiline ister misiniz?**, .dll projesinin adını seçin ve ardından **sonraki**.  
  
5.  Tıklatın **son** sihirbazdan çıkın ve yeni performans oturumu görüntülemek için **performans Gezgini** penceresi.  
  
6.  Sağ **hedefleri** ve ardından **hedef Proje Ekle**.  
  
7.  Gelen **hedef Proje Ekle** listesinde, DLL alıştırma için kullanmak istediğiniz yürütülebilir projesini seçin.  
  
     İsteğe bağlı. İstediğiniz tüm DLL projeleri profiline ekleyebilirsiniz.  
  
8.  Eklenen bir proje için veri toplama önlemek için proje adına sağ tıklayın ve ardından temizlemek **Gereci** onay kutusu.  
  
### <a name="to-specify-specific-dlls-to-profile-as-independent-binaries"></a>Profil için belirli DLL'ler bağımsız ikili belirtmek için  
  
1.  Açık [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)].  
  
2.  Üzerinde **Çözümle** menüsünde, select **başlatma performans Sihirbazı**.  
  
3.  Gelen **profiline aşağıdaki kullanılabilir hedefleri hangisinin istediğiniz**seçin **dinamik bağlantı kitaplığı profil (. DLL)** ve ardından **sonraki**.  
  
4.  Sihirbazın ikinci sayfasında aşağıdaki adımları gerçekleştirin:  
  
    -   Profilinde istediğiniz .dll dosyasının yolunu ve dosya adı yazın **Dll yolu**. Dosyayı bulmak için üç nokta düğmesini (…) de tıklatabilirsiniz **profiline dinamik bağlantı kitaplığı** iletişim kutusu. Sonraki seçtiğiniz yürütülebilir dosyanın (.exe) dosyayı tarafından başlatılacak .dll dosyasının kopyasını belirtmeniz gerektiğini unutmayın.  
  
    -   .dll çalışma yürütülebilir dosyanın (.exe) dosya yolu ve dosya adını yazın **yürütülebilir dosya yolu**. Dosyayı bulmak için üç nokta düğmesini (…) de tıklatabilirsiniz **başlatmak için yürütülebilir** iletişim kutusu.  
  
    -   İsteğe bağlı. Yürütülebilir dosya olarak geçirmek istediğiniz herhangi bir komut satırı bağımsız değişkeni tür **komut satırı bağımsız değişkenleri**. Gerekirse, uygulama için çalışma dizini belirtin **çalışma dizini**.  
  
    -   
              **İleri**'ye tıklayın.  
  
5.  Seçin **Araçları** 'ye tıklayın ve profil oluşturma yöntemi olarak **sonraki**.  
  
6.  Tıklatın **son** sihirbazdan çıkın ve yeni performans oturumu görüntülemek için **performans Gezgini** penceresi.  
  
7.  İsteğe bağlı. Daha fazla .dll dosyaları eklemek için sağ tıklatın **hedefleri** ve ardından **hedef ikili eklemek**. İstediğiniz dosyaları seçin **hedef ikili eklemek** iletişim kutusu.  
  
    > [!NOTE]
    >  DLL'leri uygular yürütülebilir dosyanın (.exe) dosyayı belirtmeyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri toplama denetimi](../profiling/controlling-data-collection.md)   
 [Nasıl yapılır: belirli işlevler için araçları sınırlama](../profiling/how-to-limit-instrumentation-to-specific-functions.md)