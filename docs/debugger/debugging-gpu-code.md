---
title: "GPU kodunda hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
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
ms.assetid: c7e77a5a-cb57-4b11-9187-ecc89acc8775
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 0699df7890528a200648ad10975b3cf272a3534f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="debugging-gpu-code"></a>GPU Kodunda Hata Ayıklama
Grafik işlemci birimi (GPU) çalıştıran C++ kodu ayıklayabilirsiniz. Hata ayıklama desteği Visual Studio GPU yarış algılama işlemleri başlatma ve bunları ve hata ayıklama windows tümleştirmeye ekleme içerir.  
  
## <a name="supported-platforms"></a>Desteklenen Platformlar  
 Hata ayıklama desteklenir [!INCLUDE[win7](../debugger/includes/win7_md.md)], [!INCLUDE[win8](../debugger/includes/win8_md.md)], [!INCLUDE[winsvr08_r2](../debugger/includes/winsvr08_r2_md.md)], ve [!INCLUDE[winserver8](../debugger/includes/winserver8_md.md)]. Yazılım öykünücüsünde hata ayıklama için [!INCLUDE[win8](../debugger/includes/win8_md.md)], veya [!INCLUDE[winserver8](../debugger/includes/winserver8_md.md)] gereklidir. Donanımda hata ayıklamak için grafik kartınız için sürücüleri yüklemeniz gerekir. Tüm donanım satıcıları tüm hata ayıklayıcı özellikler uygular. Sınırlamalar satıcı belgelerine bakın.  
  
> [!NOTE]
>  Visual Studio'da GPU hata ayıklamayı desteklemek isteyen bağımsız donanım satıcıları hedefleri ve VSD3DDebug arabirimini uygulayan bir DLL kendi sürücüleri oluşturmanız gerekir.  
  
## <a name="configuring-gpu-debugging"></a>GPU hata ayıklama yapılandırma  
 Hata ayıklayıcı hem CPU kodu hem de GPU kodunda aynı uygulama yürütme kesemez. Varsayılan olarak, hata ayıklayıcı üzerindeki CPU kodu keser. GPU kodunda hata ayıklama için iki aşağıdaki adımlardan birini kullanın:  
  
-   İçinde **hata ayıklama türü** listesini **standart** araç seçin **yalnızca GPU**.  
  
-   İçinde **Çözüm Gezgini**, proje kısayol menüsünden seçin **özellikleri**. İçinde **özellik sayfaları** iletişim kutusunda **hata ayıklama**ve ardından **yalnızca GPU** içinde **hata ayıklayıcı türü** listesi.  
  
## <a name="launching-and-attaching-to-applications"></a>Başlatma ve uygulamalara ekleme  
 GPU hata ayıklamayı durdurmak ve başlatmak için Visual Studio hata ayıklama komutlarını kullanabilirsiniz. Daha fazla bilgi için bkz: [hata ayıklayıcısı ile kodlarda gezinme](../debugger/navigating-through-code-with-the-debugger.md). Bu işlem GPU kodunda yürütülürse GPU hata ayıklayıcı ancak yalnızca bir çalışan işlemi ekleyebilirsiniz. Daha fazla bilgi için bkz: [eklemek için çalışan işlemler](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
## <a name="run-current-tile-to-cursor-and-run-to-cursor"></a>İmleci ve imleci çalışmaya çalışma geçerli döşeme  
 GPU üzerinde ayıklarken İmleç konumuna çalıştırmak için iki seçeneğiniz vardır. Kod Düzenleyicisi kısayol menüsünde kullanılabilir her iki seçenek için komutlardır.  
  
1.  **Çalıştırmak için imleç** imleç konumu ulaşana ve ardından sonları kadar uygulamanızın komutu çalıştırır. Bu, geçerli iş parçacığı için imleç çalıştığını göstermez; Bunun yerine, imleç noktasına ulaştığında ilk iş parçacığı sonu tetikler anlamına gelir. Bkz: [hata ayıklayıcısı ile kodlarda gezinme](../debugger/navigating-through-code-with-the-debugger.md)  
  
2.  **İmleç için geçerli döşeme çalıştırmak** tüm iş parçacıklarının geçerli döşemesinin imleci ve ardından sonları ulaşana kadar uygulamanızın komutu çalıştırır.  
  
## <a name="debugging-windows"></a>Windows hata ayıklama  
 Belirli hata ayıklama windows kullanarak inceleyin, bayrak ve GPU iş parçacıklarını dondurmak. Daha fazla bilgi için bkz.:  
  
-   [Paralel Yığınlar penceresini kullanma](../debugger/using-the-parallel-stacks-window.md)  
  
-   [Görevleri penceresini kullanma](../debugger/using-the-tasks-window.md)  
  
-   [Nasıl yapılır: paralel İzleme penceresini kullanma](../debugger/how-to-use-the-parallel-watch-window.md)  
  
-   [İş parçacıklarında ve işlemlerde hata ayıklama](../debugger/debug-threads-and-processes.md) (hata ayıklama konumu araç çubuğu)  
  
-   [Nasıl yapılır: GPU iş parçacıkları penceresini kullanma](../debugger/how-to-use-the-gpu-threads-window.md)  
  
## <a name="data-synchronization-exceptions"></a>Veri eşitleme özel durumlar  
 Hata ayıklayıcı birkaç veri eşitleme durum yürütme sırasında tanımlayabilirsiniz. Bir koşul algılandığında, hata ayıklayıcı sonu durumuna girer. İki seçeneğiniz vardır:**bölün** veya **devam**. Kullanarak **özel durumları** iletişim kutusunda, bu koşullar hata ayıklayıcı algılar ve ayrıca hangi koşullar, için kesintiye uğrar olup olmadığını yapılandırabilirsiniz. Daha fazla bilgi için bkz: [yönetme özel durumları hata ayıklayıcısı ile](../debugger/managing-exceptions-with-the-debugger.md). Aynı zamanda **seçenekleri** yazılan veriler veri değeri değiştirmez, hata ayıklayıcısını özel durumlar yoksay belirtmek için iletişim kutusu. Daha fazla bilgi için bkz: [genel, hata ayıklama, Seçenekler iletişim kutusu](../debugger/general-debugging-options-dialog-box.md).  
  
## <a name="troubleshooting"></a>Sorun giderme  
  
### <a name="specifying-an-accelerator"></a>Hızlandırıcı belirtme  
 Kod çalışıyorsa, GPU kodunda kesme noktası isabet yalnızca [accelerator::direct3d_ref](/cpp/parallel/amp/reference/accelerator-class.md#accelerator__direct3d_ref_Data_Member) (REF) Hızlandırıcı. Hızlandırıcı kodunuzda belirtmezseniz, REF Hızlandırıcı olarak otomatik olarak seçilir **hata ayıklama Hızlandırıcı türü** Proje Özellikleri'nde. Kodunuzu açıkça Hızlandırıcı seçerse, REF Hızlandırıcı, hata ayıklama sırasında kullanılmaz ve hata ayıklama desteği GPU donanım olmadığı sürece kesme noktası isabet değil. Bu hata ayıklama sırasında REF Hızlandırıcı kullanır, böylece kodunuzu yazarak çözebilirsiniz. Daha fazla bilgi için bkz: Proje özelliklerini ve [Hızlandırıcı ve accelerator_view nesnelerini kullanma](/cpp/parallel/amp/using-accelerator-and-accelerator-view-objects) ve [bir C++ hata ayıklama yapılandırması proje ayarları](../debugger/project-settings-for-a-cpp-debug-configuration.md).  
  
### <a name="conditional-breakpoints"></a>Koşullu kesme noktaları  
 GPU kodunda koşullu kesme noktaları desteklenir, ancak her ifade cihazda değerlendirilebilir. Bir ifade cihazda değerlendirilemez çalışırken hata ayıklayıcıyı değerlendirilir. Hata ayıklayıcı aygıt daha yavaş çalışmasına olasıdır.  
  
### <a name="error-there-is-a-configuration-issue-with-the-selected-debugging-accelerator-type"></a>Hata: Seçili hata ayıklama Hızlandırıcı türüne sahip bir yapılandırma sorunu var.  
 Proje ayarları ve üzerinde hata ayıklama PC yapılandırması arasında bir tutarsızlık olduğunda bu hata oluşur. Daha fazla bilgi için bkz: [bir C++ hata ayıklama yapılandırması proje ayarları](../debugger/project-settings-for-a-cpp-debug-configuration.md).  
  
### <a name="error-the-debug-driver-for-the-selected-debugging-accelerator-type-is-not-installed-on-the-target-machine"></a>Hata: Seçili hata ayıklama Hızlandırıcı türü için hata ayıklama sürücü hedef makinede yüklü değil.  
 Uzak bir bilgisayarda hata ayıklama, bu hata oluşur. Sürücüleri uzak bilgisayarında yüklü olup olmadığını hata ayıklayıcı çalışma zamanına kadar belirleyemiyor. Sürücüleri, ekran kartı üreticisinden kullanılabilir.  
  
### <a name="error-timeout-detection-and-recovery-tdr-must-be-disabled-at-the-remote-site"></a>Hata: Zaman aşımı algılama ve Kurtarma (TDR) uzak sitede devre dışı gerekir.  
 C++ AMP hesaplamalar Windows zaman aşımı algılama ve kurtarma işlemi (TDR) tarafından belirlenen varsayılan zaman aralığını aşan mümkündür. Bu durum oluştuğunda hesaplama iptal edilir ve veriler kaybolur. Daha fazla bilgi için bkz: [işleme TDRs C++ AMP içinde](http://go.microsoft.com/fwlink/p/?LinkId=249154).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: C++ AMP uygulamasında hata ayıklama](/cpp/parallel/amp/walkthrough-debugging-a-cpp-amp-application)   
 [C++ hata ayıklama yapılandırması proje ayarları](../debugger/project-settings-for-a-cpp-debug-configuration.md)   
 [GPU Visual Studio'da hata ayıklamayı Başlat](http://go.microsoft.com/fwlink/p/?LinkId=255381)