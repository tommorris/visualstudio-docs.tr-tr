---
title: "Nasıl yapılır: belirli DLL'ler için araçları sınırlama | Microsoft Docs"
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- performance tools, runtime profiling control window
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6ca2c966c395edf189cbab04c20cdb77c6b0e4e3
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-limit-instrumentation-to-specific-dlls"></a>Nasıl yapılır: Belirli DLL'ler için İzleme Sınırlama

Profil Oluşturucu izleme yöntemini kullanarak, bir uygulamada bir veya daha fazla DLL'ler için profil oluşturma veri koleksiyonunu sınırlayabilirsiniz. Bir uygulama bir veya daha fazla DLL'lerde profil için hedefleri olarak .dll dosyalarını içeren bir performans oturumu oluşturun. Visual Studio çözümü projelerinde veya bağımsız ikili dosyaları olarak profil oluşturmayı istediğiniz DLL'leri belirtebilirsiniz.

## <a name="to-limit-instrumentation-to-specific-dlls-in-a-visual-studio-solution"></a>Visual Studio çözümünde belirli DLL'ler için araçları sınırlamak için

1. Visual Studio'da DLL içeren çözümü açın].

2. Üzerinde **Çözümle** menüsünde, select **başlatma performans Sihirbazı**.

3. Seçin **Araçları** 'ye tıklayın ve profil oluşturma yöntemi olarak **sonraki**.

4. Gelen **aşağıdaki kullanılabilir hedefleri hangisinin profiline ister misiniz?**, .dll projesinin adını seçin ve ardından **sonraki**.

5. Tıklatın **son** sihirbazdan çıkın ve yeni performans oturumu görüntülemek için **performans Gezgini** penceresi.

6. Sağ **hedefleri** ve ardından **hedef Proje Ekle**.

7. Gelen **hedef Proje Ekle** listesinde, DLL alıştırma için kullanmak istediğiniz yürütülebilir projesini seçin.

     İsteğe bağlı. İstediğiniz tüm DLL projeleri profiline ekleyebilirsiniz.

8. Eklenen bir proje için veri toplama önlemek için proje adına sağ tıklayın ve ardından temizlemek **Gereci** onay kutusu.

## <a name="to-specify-specific-dlls-to-profile-as-independent-binaries"></a>Profil için belirli DLL'ler bağımsız ikili belirtmek için

1. Visual Studio'yu açın.

2. Üzerinde **Çözümle** menüsünde, select **başlatma performans Sihirbazı**.

3. Gelen **profiline aşağıdaki kullanılabilir hedefleri hangisinin istediğiniz**seçin **dinamik bağlantı kitaplığı profil (. DLL)** ve ardından **sonraki**.

4. Sihirbazın ikinci sayfasında aşağıdaki adımları gerçekleştirin:

    - Profilinde istediğiniz .dll dosyasının yolunu ve dosya adı yazın **Dll yolu**. Dosyayı bulmak için üç nokta düğmesini (…) de tıklatabilirsiniz **profiline dinamik bağlantı kitaplığı** iletişim kutusu. Sonraki seçtiğiniz yürütülebilir dosyanın (.exe) dosyayı tarafından başlatılacak .dll dosyasının kopyasını belirtmeniz gerektiğini unutmayın.

    - .dll çalışma yürütülebilir dosyanın (.exe) dosya yolu ve dosya adını yazın **yürütülebilir dosya yolu**. Dosyayı bulmak için üç nokta düğmesini (…) de tıklatabilirsiniz **başlatmak için yürütülebilir** iletişim kutusu.

    - İsteğe bağlı. Yürütülebilir dosya olarak geçirmek istediğiniz herhangi bir komut satırı bağımsız değişkeni tür **komut satırı bağımsız değişkenleri**. Gerekirse, uygulama için çalışma dizini belirtin **çalışma dizini**.

    - **İleri**'ye tıklayın.

5. Seçin **Araçları** 'ye tıklayın ve profil oluşturma yöntemi olarak **sonraki**.

6. Tıklatın **son** sihirbazdan çıkın ve yeni performans oturumu görüntülemek için **performans Gezgini** penceresi.

7. İsteğe bağlı. Daha fazla .dll dosyaları eklemek için sağ tıklatın **hedefleri** ve ardından **hedef ikili eklemek**. İstediğiniz dosyaları seçin **hedef ikili eklemek** iletişim kutusu.

    > [!NOTE]
    > DLL'leri uygular yürütülebilir dosyanın (.exe) dosyayı belirtmeyin.

## <a name="see-also"></a>Ayrıca bkz.

[Veri toplama denetimi](../profiling/controlling-data-collection.md)  
[Nasıl yapılır: belirli işlevler için araçları sınırlama](../profiling/how-to-limit-instrumentation-to-specific-functions.md)