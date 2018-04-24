---
title: 'Nasıl yapılır: bağımsız profil oluşturucuyu yükleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- performance tools, installing stand-alone profiler
- profiling tools, stand-alone profiler
ms.assetid: cae81c95-83cd-4ab6-8a98-84ef977a2f6d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 21a285c95e3649cc7aaa53995070091f0abea509
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-install-the-stand-alone-profiler"></a>Nasıl yapılır: Bağımsız Profil Oluşturucuyu Yükleme
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir komut satırı tabanlı yüklemeden çalıştırılabilir bağımsız profil oluşturucuyu sağlar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE. Bir bilgisayar yok ya da yüklü bir geliştirme ortamı olamaz bu durum oluşur. Örneğin, bir üretim Web sunucusunda bir geliştirme ortamı yüklememelidir.  
  
> [!NOTE]
>  ASP.NET Web sitesi için performans verilerini toplamak için bağımsız profil oluşturucuyu kullanırken [VSPerfASPNetCmd](../profiling/vsperfaspnetcmd.md) Çizgi aracı üzerinden önerilir [VSPerfCmd](../profiling/vsperfcmd.md) aracı.  
  
### <a name="to-install-the-stand-alone-profiler"></a>Bağımsız profil oluşturucuyu yükleme  
  
1.  Bağımsız Profil Yükleyicisi (vs_profiler.exe) bulmak [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] yükleme medyasını Directory'de \Standalone profil oluşturucu yolu içerir ve çalıştırın.  
  
2.  Vsintr.exe ve msdis150.dll yollarının sistem yoluna ekleyin.  
  
    > [!NOTE]
    >  Varsayılan yüklemesinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], vsinstr.exe ve msdis150.dll Files\Visual Studio 10\Team Araçlar\Performans araçları bulunur.  
  
3.  Komut isteminde **Vsınstr**.  
  
    > [!NOTE]
    >  Vsinstr.exe için kullanım bilgilerini gösterilirse, her şeyin doğru şekilde ayarlanır. Vsinstr.exe belirten bir hata göreceğiniz veya bağımlılıklarından biri bulunamazsa, 2. adımda açıklandığı şekilde doğru olarak ayarlanmış, yolları olduğundan emin olun.  
  
4.  Simge Sunucusu'nu ayarlamak, **_NT_SYMBOL_PATH** değişkenini **symsrv\*symsrv.dll\*c:\localcache\*http://msdl.microsoft.com/download/symbols**  
  
5.  Sistem ortam değişkenleri kullanılarak simgesi sunucunuzu ayarladıktan sonra komut satırından profil oluşturucu Araçlar yeni bir komut isteminde çalıştırın. Bu, etkili olması yeni ortam değişkenleri sağlar. Komut İstemi penceresinde aşağıdaki komutu yazın:  
  
     **COMSPEC % Başlat**  
  
    > [!NOTE]
    >  Sembol sunucu paketi ayarlama hakkında ayrıntılı yönergeler için bkz: [nasıl yapılır: başvuru pencereleri sembol bilgileri](../profiling/how-to-reference-windows-symbol-information.md).  
  
6.  Kullanım [VSPerfReport](../profiling/vsperfreport.md) profil oluşturma veri (.vsp) dosyasına, simgeler serileştirmek için aracı. Kullanım **VSPerfReport /summary:all /packsymbols** anahtarları. Veri dosyasında eklenen simgeleri yoksa _NT_SYMBOL_PATH ortam değişkeni kümesi olduğundan emin olun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Komut satırından profil oluşturma](../profiling/using-the-profiling-tools-from-the-command-line.md)   
 [İzlenecek yol: Örnekleme kullanarak komut satırı profili oluşturma](../profiling/walkthrough-command-line-profiling-using-sampling.md)   
 [İzlenecek yol: İzleme kullanarak komut satırı profili oluşturma](../profiling/walkthrough-command-line-profiling-using-instrumentation.md)   
 [Nasıl yapılır: başvuru pencereleri sembol bilgileri](../profiling/how-to-reference-windows-symbol-information.md)   
 [VSPerfReport](../profiling/vsperfreport.md)