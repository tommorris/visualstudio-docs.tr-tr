---
title: "Çıktı penceresi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.build.output
- vs.debug.output
- vs.output
helpviewer_keywords:
- Output window, about Output window
- Output window
- Toolbox, removing controls
ms.assetid: d8931d88-250e-4db4-963f-2c5b3e99b45f
caps.latest.revision: "30"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 1e886e88ad7ab4e943908e003ffe56719bd13211
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="output-window"></a>Çıktı Penceresi
**Çıkış** penceresi tümleşik geliştirme ortamı (IDE) çeşitli özellikleri için durum iletilerini görüntüleyebilir. Açmak için **çıkış** menü çubuğunda, pencere **görünüm/çıkış** (veya CTRL + ALT + O tıklatın).  
  
> [!WARNING]
>  Çıktı penceresi, Visual Studio Express sürümlerinde Görünüm menüsünde görünmez. Bunu ortaya çıkarmak için kısayol tuşu kullanın CTRL + ALT + o  
  
## <a name="toolbar"></a>Araç Çubuğu  
 **Gelen çıktıyı Göster**  
 Görüntülemek için bir veya daha fazla çıkış bölmeleri görüntüler. Bilgilerin birkaç bölmeleri IDE hangi araçlarında kullandınız bağlı olarak, kullanılabilir **çıkış** kullanıcıya iletileri sunmak için penceresi.  
  
 **Kodda ileti bulma**  
 Ekleme noktasını Seçili yapı hata içeren bir satır kod düzenleyicisinde taşır.  
  
 **Önceki iletiye gider.**  
 Odak değişiklikleri **çıkış** önceki penceresine hata oluşturmak ve ekleme noktasını Kod Düzenleyicisi'nde hata yapı içeren satırına taşır.  
  
 **Sonraki iletiye gider.**  
 Odak değişiklikleri **çıkış** sonraki penceresine hata oluşturmak ve ekleme noktasını Kod Düzenleyicisi'nde hata yapı içeren satırına taşır.  
  
 **Tümünü temizle**  
 Tüm metni temizler **çıkış** bölmesi.  
  
 **Sözcük kaydırmayı değiştirme**  
 Sözcük kaydırma özelliğini açar ve kapatır **çıkış** bölmesi. Sözcük kaydırma açık olduğunda görüntüleme alanı genişleten metin uzun girdileri aşağıdaki satırda görüntülenir.  
  
## <a name="output-pane"></a>Çıkış bölmesi  
 **Çıkış** bölmesinde seçili **Göster çıktı** belirtilen kaynak çıktısını görüntüler.  
  
## <a name="routing-messages-to-the-output-window"></a>Çıktı penceresi yönlendirme iletileri  
 Görüntülenecek **çıkış** bir projeyi de derleme zaman penceresi **genel, projeler ve çözümler, Seçenekler** iletişim kutusunda **yapı başladığında Göster çıktı penceresi**. Düzenlemek için bir kod dosyası açıkken, ardından **sonraki iletiye gider** ve **önceki iletiyi** üzerinde düğmeleri **çıkış** penceresi araç girişleriniseçin **Çıktı** bölmesi. Bunu yaparken ekleme noktasını, seçilen sorunun oluştuğu kod satırı Kod Düzenleyicisi atlar.  
  
 Belirli IDE özellik ve çağrılması komutları [komut penceresi](../../ide/reference/command-window.md) çıktılarını için teslim **çıkış** penceresi. Genellikle bir komut istemi penceresinde görüntülenen, .bat ve .com dosyaları gibi harici araçlar çıktısı için yönlendirilir bir **çıkış** seçtiğinizde bölmesinde **çıktı penceresini kullan** seçeneğinde[Dış araçları yönetme](../../ide/managing-external-tools.md). İletileri pek çok değişik görüntülenebilen **çıkış** bölmeleri de. Saklı yordam Transact-SQL söz dizimi hedef veritabanına karşı işaretlendiğinde, örneğin, sonuçları görüntülenir **çıkış** penceresi.  
  
 Çalışma zamanında tanılama iletileri yazmak için kendi uygulamalarınızı programlama yapabilirsiniz bir **çıkış** bölmesi. Bunu yapmak için üyeleri kullanın <xref:System.Diagnostics.Debug> sınıfı veya <xref:System.Diagnostics.Trace> sınıfını <xref:System.Diagnostics> ad alanı .NET Framework sınıf kitaplığı. Üyeleri <xref:System.Diagnostics.Debug> çözüm ya da proje hata ayıklama yapılandırmaları derlerken sınıfı görüntüsü çıkışı; üyeleri <xref:System.Diagnostics.Trace> sınıfı görüntüleme çıkış hata ayıklama veya yayın yapılandırmaları oluşturduğunuzda. Daha fazla bilgi için bkz: [çıktı penceresindeki tanılama iletileri](../../debugger/diagnostic-messages-in-the-output-window.md).  
  
 İçinde [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)], özel derleme adımları oluşturma ve derleme olayları, uyarıları ve hataları görüntülenir ve sayılı **çıkış** bölmesi. Çıktı satırında F1'e basarak uygun bir Yardım konusu görüntüleyebilirsiniz. Daha fazla bilgi için bkz: [özel derleme adımı veya derleme olayının çıktısını biçimlendirme](/cpp/ide/formatting-the-output-of-a-custom-build-step-or-build-event).  
  
## <a name="scrolling-behavior"></a>Kaydırma davranışını  
 Çıktı penceresinde autoscrolling kullanıyorsanız ve fareyi veya ok tuşlarını kullanarak gidin, autoscrolling durdurur. Autoscrolling devam etmek için CTRL + END tuşlarına basın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çıktı penceresindeki tanılama iletileri](../../debugger/diagnostic-messages-in-the-output-window.md)   
 [Nasıl yapılır: Çıktı penceresi denetleme](http://msdn.microsoft.com/Library/91aebd15-8854-4a7a-9f7d-57376fb4e858)   
 [Derleme ve oluşturma](../../ide/compiling-and-building-in-visual-studio.md)   
 [Derleme yapılandırmalarını anlama](../../ide/understanding-build-configurations.md)   
 [Sınıf Kitaplığına Genel Bakış](/dotnet/standard/class-library-overview)