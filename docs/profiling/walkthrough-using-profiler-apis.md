---
title: "İzlenecek yol: Profilini Oluşturucu API'ler kullanma | Microsoft Docs"
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling tools, walkthroughs
- performance tools, walkthroughs
ms.assetid: c2ae0b3e-a0ca-4967-b4df-e319008f520e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 50b77a343f8fe918fa079a3b4f148407701276c8
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34572991"
---
# <a name="walkthrough-using-profiler-apis"></a>İzlenecek yol: Profil Oluşturucu API'ler kullanma
İzlenecek yol bir C# uygulamasını nasıl kullanılacağını göstermek için kullanır. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profil oluşturma araçları API'leri. İzleme profili oluşturma sırasında toplanan veri miktarını sınırlamak için profil oluşturucu API kullanır.  
  
 Bu izlenecek adımları genellikle C/C++ uygulaması için geçerlidir. Her bir dil için yapı ortamınıza uygun şekilde yapılandırmanız gerekir.  
  
 Genellikle, örnek profil kullanarak uygulama performansını çözümlemek başlar. Profil oluşturma araçları örnek profil bir performans sorunu pinpoints bilgileri sağlamazsa, büyük bir ayrıntı düzeyini sağlayabilirsiniz. Profil oluşturma araçları, iş parçacığı etkileşim araştırma için çok kullanışlıdır.  
  
 Ancak, büyük bir ayrıntı düzeyini daha fazla veri toplanır anlamına gelir. Profil oluşturma araçları büyük veri dosyalarını oluşturur bulabilirsiniz. Ayrıca, araçları uygulamanın performansını etkileyip daha yüksektir. Daha fazla bilgi için bkz: [izleme veri değerlerini anlama](../profiling/understanding-instrumentation-data-values.md) ve [örnekleme veri değerlerini anlama](../profiling/understanding-sampling-data-values.md)  
  
 Visual Studio Profil Oluşturucu veri koleksiyonunu sınırlamanıza olanak sağlar. Bu kılavuzda profil oluşturucu API kullanarak veri koleksiyonunu sınırlamak nasıl bir örnek sunar. Visual Studio profil oluşturucu, bir uygulama denetleme veri toplama için bir API sağlar.  
  
 Yerel kod için Visual Studio profil oluşturucu API bulunan *VSPerf.dll*. Üstbilgi dosyası *VSPerf.h*ve içeri aktarma kitaplığını *VSPerf.lib*, bulunan *Microsoft Visual Studio 9\Team Araçlar\Performans Araçları* dizin.  
  
 Yönetilen kod için profil oluşturucu API bulunan *Microsoft.VisualStudio.Profiler.dll*. Bu DLL bulunan *Microsoft Visual Studio 9\Team Araçlar\Performans Araçları* dizin. Daha fazla bilgi için bkz. <xref:Microsoft.VisualStudio.Profiler>.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuzda, tercih ettiğiniz geliştirme ortamı hata ayıklama ve örnekleme desteklemek üzere yapılandırılmış varsayar. Aşağıdaki konular bu Önkoşullar genel bir bakış sağlar:  
  
 [Nasıl yapılır: Toplama metotlarını seçme](../profiling/how-to-choose-collection-methods.md)  
  
 [Nasıl yapılır: Başvuru pencereleri sembol bilgileri](../profiling/how-to-reference-windows-symbol-information.md)  
  
 Profil Oluşturucu başlatıldığında, varsayılan olarak, profil oluşturucu genel düzeyde veri toplar. Aşağıdaki kod program başlangıcında kapalı profil oluşturma genel etkinleştirir.  
  
```csharp  
DataCollection.StopProfile(  
ProfileLevel.Global,  
DataCollection.CurrentId);  
```  
  
 Veri toplama komut satırında bir API çağrısı kullanmadan devre dışı bırakabilirsiniz. Aşağıdaki adımlar komut satırı derleme ortamınızı profil oluşturma araçları çalıştırmak üzere yapılandırılmış varsayar ve geliştirme araçları olarak. Vsınstr ve VSPerfCmd için gerekli olan ayarları içerir. Komut satırı Profil Araçları konusuna bakın.  
  
## <a name="limit-data-collection-using-profiler-apis"></a>Profil Oluşturucu API kullanarak veri toplama sınırla  
  
#### <a name="to-create-the-code-to-profile"></a>Kod profil oluşturmak için  
  
1.  Visual Studio'da yeni bir C# projesi oluşturma veya tercihinize bağlı olarak bir komut satırı derleme kullanın.  
  
    > [!NOTE]
    >  Yapınızın başvurmalıdır *Microsoft.VisualStudio.Profiler.dll* bulunan kitaplık*Microsoft Visual Studio 9\Team Araçlar\Performans Araçları* dizin.  
  
2.  Kopyalayın ve projenize aşağıdaki kodu yapıştırın:  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using Microsoft.VisualStudio.Profiler;  
  
    namespace ConsoleApplication2  
    {  
        class Program  
        {  
            public class A  
            {  
             private int _x;  
  
             public A(int x)  
             {  
              _x = x;  
             }  
  
             public int DoNotProfileThis()  
             {  
              return _x * _x;  
             }  
  
             public int OnlyProfileThis()  
             {  
              return _x + _x;  
             }  
  
             public static void Main()  
             {  
            DataCollection.StopProfile(  
            ProfileLevel.Global,  
            DataCollection.CurrentId);  
              A a;  
              a = new A(2);  
              int x;      
              Console.WriteLine("2 square is {0}", a.DoNotProfileThis());  
              DataCollection.StartProfile(  
                  ProfileLevel.Global,  
                  DataCollection.CurrentId);  
              x = a.OnlyProfileThis();  
              DataCollection.StopProfile(  
                  ProfileLevel.Global,   
                  DataCollection.CurrentId);  
              Console.WriteLine("2 doubled is {0}", x);  
             }  
            }  
  
        }  
    }  
    ```  
  
#### <a name="to-collect-and-view-data-in-the-visual-studio-ide"></a>Toplamak ve Visual Studio IDE içinde verileri görüntülemek için  
  
1.  Açık [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE. Oturum **Çözümle** menüsündeki **profil oluşturucu**ve ardından **yeni performans oturumu**.  
  
2.  Derlenmiş ikili dosyanız için ekleme **hedefleri** listesinde **performans Gezgini** penceresi. Sağ **hedefleri**ve ardından **hedef ikili eklemek**. İkili bulun **hedef ikili eklemek** iletişim kutusunu ve ardından **açık**.  
  
3.  Seçin **Araçları** gelen **yöntemi** listesini **performans Gezgini** araç.  
  
4.  Tıklatın **başlatma profil oluşturma ile**.  
  
     Profil Oluşturucu izleme ve ikili yürütme ve performans raporu dosyası oluştur. Performans Raporu dosyası görünür **raporları** düğümünün **performans Gezgini**.  
  
5.  Sonuçta elde edilen performans raporu dosyasını açın.  
  
 Profil Oluşturucu başlatıldığında, varsayılan olarak, profil oluşturucu genel düzeyde veri toplar. Aşağıdaki kod program başlangıcında kapalı profil oluşturma genel etkinleştirir.  
  
```csharp  
DataCollection.StopProfile(  
ProfileLevel.Global,  
DataCollection.CurrentId);  
```  
  
#### <a name="to-collect-and-view-data-at-the-command-line"></a>Toplamak ve komut satırında verileri görüntülemek için  
  
1.  "Profili kod oluşturma" yordamı, bu kılavuzda daha önce oluşturduğunuz örnek kodda hata ayıklama sürümü derleyin.  
  
2.  Yönetilen bir uygulama profili için uygun ortam değişkenlerini ayarlamak için aşağıdaki komutu yazın:  
  
     **VsPefCLREnv /traceon**  
  
3.  Aşağıdaki komutu yazın:**Vsınstr \<filename > .exe**  
  
4.  Aşağıdaki komutu yazın:**VSPerfCmd /start:trace/Output:\<filename > .vsp**  
  
5.  Aşağıdaki komutu yazın:**VSPerfCmd /globaloff**  
  
6.  Programınızı yürütün.  
  
7.  Aşağıdaki komutu yazın:**VSPerfCmd Shutdown**  
  
8.  Aşağıdaki komutu yazın:**VSPerfReport /calltrace:\<filename > .vsp**  
  
     A. *csv* dosyası geçerli dizinde sonuç performans verileri ile oluşturulur.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 <xref:Microsoft.VisualStudio.Profiler>   
 [Visual Studio profil oluşturucu API Başvurusu (yerel)](../profiling/visual-studio-profiler-api-reference-native.md)   
 [Başlarken](../profiling/getting-started-with-performance-tools.md)   
 [Komut satırından profil](../profiling/using-the-profiling-tools-from-the-command-line.md)