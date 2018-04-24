---
title: 'Nasıl yapılır: başvuru pencereleri sembol bilgileri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- performance tools, symbol servers
- servers, symbol servers
- profiling tools, symbol servers
- symbol servers
ms.assetid: b7c67318-6be2-4b1e-a161-077b1f4a7c30
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 247a152cd04a262115cbde78a7a06ad2e95f250c
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-reference-windows-symbol-information"></a>Nasıl yapılır: Başvuru Pencereleri Sembol Bilgileri
Profil oluşturma Visual Studio Araçları, program ikili dosyaları işlevi adları gibi simgesel adları çözümlemek için simge (.pdb) dosyalarını kullanın. Otomatik olarak karşıdan yükle ve yerel bilgisayarda Windows sürümü için doğru .pdb dosyaları güncelleştirmek için aşağıdaki adımları izleyebilirsiniz.  
  
> [!NOTE]
>  Bu ayar, varolan raporları etkilemez. Yalnızca simge sunucusunu belirttikten sonra oluşturulan raporlar sembol bilgileri gerekir.  
  
 Daha fazla bilgi için bkz: [belirtin simge (.pdb) ve kaynak dosyaları](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).  
  
### <a name="to-use-the-microsoft-symbol-server"></a>Microsoft Simge sunucusunu kullanmak için  
  
1.  C:\SymbolCache gibi simge dosyası bilgileri içeren bir klasör oluşturun.  
  
2.  Üzerinde **Araçları** menüsünde tıklatın **seçenekleri**.  
  
     **Seçenekleri** iletişim kutusu görüntülenir.  
  
3.  Genişletme **hata ayıklama** ağacı ve ardından **simgeleri**.  
  
4.  İçinde **simge (.pdb) dosya konumları**seçin **Microsoft simge sunucuları**  
  
5.  İçinde **önbelleğe bu dizin simge sunucusundan simgeleri**, adım 1 ' de örneğin oluşturulduğu klasörünün yolunu yazın:  
  
     **C:\SymbolCache**  
  
     Üç nokta düğmesini tıklatarak (**...** ) ve ardından bir dizinden **klasöre Gözat** iletişim kutusu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Performans oturumlarını yapılandırma](../profiling/configuring-performance-sessions.md)   
 [Nasıl yapılır: sembol bilgilerini serileştirme](../profiling/how-to-serialize-symbol-information.md)