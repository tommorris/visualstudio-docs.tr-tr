---
title: "Nasıl yapılır: ön ve son izleme komutları belirtme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.property.instrument
helpviewer_keywords:
- profiling tools, pre-instrument events
- events [Visual Studio], pre-instrument
- pre-instrument events, performance tools
ms.assetid: 6a8d5340-1d1b-4d81-88dd-8e1f435eb828
caps.latest.revision: "28"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7daf63f27d9c285c126e437f55d25ff674d7360f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-specify-pre--and-post-instrument-commands"></a>Nasıl yapılır: Ön ve Son İzleme Komutları Belirtme
Önce veya ikili dosyaların bir performans oturumunda işaretlendiğine sonra çalışan komutlar belirtebilirsiniz. Komut satırından verilebilmesi için herhangi bir komuttan ön izleme veya bir son izleme olayı olarak belirtilebilir. Örneğin, ikili dosyaları işaretlendiğine sonra çalıştırılan bir toplu iş dosyasında güçlü ad anahtar ile bir derlemenin bildirimin otomatikleştirmek komutları belirtebilirsiniz.  
  
 Profil oluşturma çalıştırmada tüm izleme eklenmiş ikili dosyalar ya da bireysel ikili dosyaları komutları belirtebilirsiniz. Ancak, daha önce çalıştırılması için yalnızca bir ön izleme ve sonra izleme işlemini çalıştırmak için yalnızca bir son izleme komutunu belirtebilirsiniz. Komutları bireysel ikili dosyaları ve her iki tüm ikili dosyaları için belirtilemez. Tüm ikili dosyaları için komutları belirttiğinizde, komutları önce veya sonra her ikili araçları oturumunda çalıştırılır.  
  
 **Gereksinimler**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
 Çalıştırdığınız işletim systen üzerinde komutları yürütülme çalışma dizini bağlıdır [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] ve profili uygulamanın hedef platformu.  
  
 **32-bit bilgisayarlar**  
  
 32-bit bilgisayarlarda, varsayılan profil oluşturucu Araçlar önyükleme sürücüsü\Program Files\Microsoft Visual Studio 10.0\Team Araçlar\Performans araçları dizinidir.  
  
 **64-bit bilgisayarlar**  
  
 64-bit bilgisayarlarda, profili uygulamanın hedef platformu göre yolu belirtin:  
  
-   32-bit uygulamalar için varsayılan profil oluşturucu Araçlar dizindir:  
  
     *Sürücü*\Program dosyaları (x86) \Microsoft Visual Studio 10.0\Team Araçlar\Performans araçları  
  
-   64-bit uygulamalar için varsayılan profil oluşturucu Araçlar dizindir:  
  
     *Sürücü*\Program dosyaları (x86) \Microsoft Visual Studio 10.0\Team Araçlar\Performans Tools\x64  
  
### <a name="to-specify-pre-instrument-commands"></a>Ön izleme komutları belirtmek için  
  
1.  Aşağıdaki adımlardan birini uygulayın:  
  
    -   Bir performans oturumda ön izleme komutları tüm ikili dosyaları belirtmek için performans oturumu düğümünde seçin **performans Gezgini**, sonra sağ tıklatın ve seçin **özellikleri**.  
  
    -   Ön izleme komutları için belirli bir ikili belirtmek için ikili adına sağ tıklayın **hedefleri** performans oturumu ve ardından listesini **özellikleri**.  
  
2.  İçinde **özellik sayfaları**, tıklatın **Araçları**.  
  
3.  Komut yazın **komut satırı** metin kutusu altında **ön izleme olayları**.  
  
    > [!NOTE]
    >  Üç nokta düğmesini tıklatabilirsiniz **(...)**  bitişik olan **komut satırı** kutusunu gidin ve uygun .exe, .cmd ve .bat dosyasını seçin.  
  
4.  **Tamam**'ı tıklatın.  
  
     Kaldırmadan çalışmasını komutu devre dışı bırakmak için seçin **araçları hariç** onay kutusu. Derleyici veya bağlayıcı ayarlarını değiştirmek için proje özellik sayfalarını kullanın.  
  
### <a name="to-specify-post-instrument-commands"></a>Son izleme komutları belirtmek için  
  
1.  Aşağıdaki adımlardan birini uygulayın:  
  
    -   Bir performans oturumu son izleme komutları tüm ikili dosyaları belirtmek için performans oturumu düğümünde seçin **performans Gezgini**, sonra sağ tıklatın ve seçin **özellikleri**.  
  
    -   Belirli bir ikili için son izleme komutları belirtmek için ikili adına sağ tıklayın **hedefleri** performans oturumu ve ardından listesini **özellikleri**.  
  
2.  İçinde **özellik sayfaları**, tıklatın **Araçları**.  
  
3.  Komut yazın **komut satırı** metin kutusu altında **son izleme olayları**.  
  
    > [!NOTE]
    >  Üç nokta düğmesini tıklatabilirsiniz **(...)**  bitişik olan **komut satırı** kutusunu gidin ve uygun .exe, .cmd ve .bat dosyasını seçin.  
  
4.  **Tamam**'ı tıklatın.  
  
     Kaldırmadan çalışmasını komutu devre dışı bırakmak için seçin **araçları hariç** onay kutusu. Derleyici veya bağlayıcı ayarlarını değiştirmek için proje özellik sayfalarını kullanın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Performans oturumlarını yapılandırma](../profiling/configuring-performance-sessions.md)