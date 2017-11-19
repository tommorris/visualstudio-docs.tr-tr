---
title: "IntelliTrace olayları görüntülemek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1c9c91a-0009-4c4e-9b4f-c9ab3a6022a7
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eff33b87d647d28f4af8f452ea4662656a15a61e
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="view-events-with-intellitrace-in-visual-studio"></a>Visual Studio IntelliTrace ile olaylarını görüntüle
IntelliTrace veya hakkında bilgi belirli olayları ya da olayların kategorilerini, ayrı ayrı işlev çağrılarını ayrıca olaylarını toplamak için kullanabilirsiniz. Aşağıdaki yordamlar, bunun nasıl yapılacağını gösterir.  
  
 Visual Studio Enterprise edition, ancak değil Professional veya topluluk sürümleri IntelliTrace kullanabilirsiniz.  
  
##  <a name="GettingStarted"></a>IntelliTrace yapılandırın  
 Yalnızca IntelliTrace olayları ile hata ayıklama deneyebilirsiniz. IntelliTrace hata ayıklayıcı olayları, özel durumlar, .NET Framework olayları ve diğer sistem olayları olaylardır. Açma veya hata ayıklama başlamadan önce IntelliTrace kaydeden olayları denetlemek için belirli olayları devre dışı bırakma. Daha fazla bilgi için bkz: [IntelliTrace özellikleri](../debugger/intellitrace-features.md).  
  
 - Dosya erişimi için IntelliTrace olayı kapatın. Git **Araçlar > Seçenekler > IntelliTrace > IntelliTrace olayları** sayfasında ve genişletin **dosya** kategorisi. Denetleme **dosya** olay kategorisi. Bu denetlenecek tüm dosya olayları (erişim, Kapat, silme) neden olur.

## <a name="create-your-app"></a>Uygulamanızı oluşturma
  
1.  Bir C# konsol uygulaması oluşturun. Program.cs dosyasında aşağıdaki ekleyin `using` deyimi:  
  
    ```CSharp  
    using System.IO;  
    ```  
  
2.  Oluşturma bir <xref:System.IO.FileStream> , okumak Main yönteminde kapatın ve dosyayı silin. Yalnızca bir kesme noktası ayarlamak için bir yer olan başka bir satırı ekleyin:  
  
    ```CSharp  
    static void Main(string[] args)  
    {  
        FileStream fs = File.Create("WordSearchInputs.txt");  
        fs.ReadByte();  
        fs.Close();  
        File.Delete("WordSearchInputs.txt");  
  
        Console.WriteLine("done");  
    }  
    ```  
  
3.  Bir kesme noktası ayarlayın`Console.WriteLine("done");`  

## <a name="start-debugging-and-view-intellitrace-events"></a>Hata Ayıklamayı Başlat ve IntelliTrace olayları görüntülemek
  
1.  Her zamanki gibi hata ayıklamayı Başlat. (Tuşuna **F5** veya **hata ayıklama > hata ayıklamayı Başlat**.  
  
    > [!TIP]
    >  Tutmak **Yereller** ve **otomobiller** windows bakın ve bu Windows'ta değerleri kaydetmek için hatalarını ayıkladığınız sırada açın.  
  
2.  Yürütme kesme noktasında durur. Görmüyorsanız, **tanılama araçları** penceresinde tıklatın **hata ayıklama > Windows > IntelliTrace olayları**.  
  
     İçinde **tanılama araçları** penceresinde Bul **olayları** sekmesini (3 sekmeleri görürsünüz **olayları**, **bellek kullanımı**, ve **CPU Kullanım**). **Olayları** sekmesini kronolojik olayları, hata ayıklayıcı yürütme ihlal önce son olay ile biten listesini gösterir. Adlı bir olay görmelisiniz **erişim WordSearchInputs.txt**.  
  
     Aşağıdaki ekran görüntüsünde, Visual Studio 2015 güncelleştirme 1 ' dir.  
  
     ![IntelliTrace &#45; Update1](../debugger/media/intellitrace-update1.png "IntelliTrace Update1")  
  
3.  Olay ayrıntılarını genişletmek için seçin.  
  
     Aşağıdaki ekran görüntüsünde, Visual Studio 2015 güncelleştirme 1 ' dir.  
  
     ![IntelliTraceUpdate1 &#45; SingleEvent](../debugger/media/intellitraceupdate1-singleevent.png "IntelliTraceUpdate1 SingleEvent")  
  
     Dosyayı açmak için pathname bağlantı seçebilirsiniz. Tam yol kullanılamıyorsa, **Dosya Aç** iletişim kutusu görüntülenir.  
  
     Tıklatın **geçmiş hata ayıklama etkinleştirme**, hangi kümelerinin Hata Ayıklayıcı'nın bağlamı zaman seçili olay saat için toplanan, gösteren geçmiş verileri de **çağrı yığını**, **Yereller** ve diğer windows hata ayıklayıcı katılan. Kaynak kodu varsa, onu incelemek için Visual Studio işaretçinin kaynak penceresinde ilgili kod taşır.  
  
     Aşağıdaki ekran görüntüsünde, Visual Studio 2015 güncelleştirme 1 ' dir.  
  
     ![HistoricalDebugging &#45; Update1](../debugger/media/historicaldebugging-update1.png "HistoricalDebugging Update1")  
  
4.  Hatanın bulamadıysanız, hataya yol diğer olayları inceleniyor deneyin. İşlev çağrıları üzerinden adım için IntelliTrace kayıt çağrı bilgileri sahip olabilir. 
  
## <a name="next-steps"></a>Sonraki Adımlar

Bazı gelişmiş özelliklerin bir kısmı IntelliTrace geçmiş hata ayıklama ile kullanabilirsiniz:

 - Anlık görüntüler görüntülemek için bkz: [IntelliTrace adım geri kullanarak anlık görüntüleri görüntüleme](../debugger/how-to-use-intellitrace-step-back.md)
 - Değişkenleri inceleyin ve kod gidin öğrenmek için bkz: [geçmiş hata ayıklama ile uygulamanızı inceleyin.](../debugger/historical-debugging-inspect-app.md)