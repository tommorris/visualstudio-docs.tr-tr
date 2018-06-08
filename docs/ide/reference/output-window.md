---
title: Çıktı Penceresi
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vs.build.output
- vs.debug.output
- vs.output
helpviewer_keywords:
- Output window, about Output window
- Output window
- Toolbox, removing controls
ms.assetid: d8931d88-250e-4db4-963f-2c5b3e99b45f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8e9af45262649473f9676bff80b4a238fdd642ac
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2018
ms.locfileid: "34844218"
---
# <a name="output-window"></a>Çıktı penceresi

**Çıkış** penceresi tümleşik geliştirme ortamı (IDE) çeşitli özellikleri için durum iletilerini görüntüler. Açmak için **çıkış** menü çubuğunda, pencere **Görünüm** > **çıkış**, veya basın **Ctrl** +  **Alt**+**O**.

## <a name="toolbar"></a>Araç Çubuğu

Aşağıdaki denetimleri araç çubuğunda gösterilir **çıkış** penceresi.

### <a name="show-output-from"></a>Gelen çıktıyı Göster

Görüntülemek için bir veya daha fazla çıkış bölmeleri görüntüler. Bilgilerin birkaç bölmeleri IDE hangi araçlarında kullandınız bağlı olarak, kullanılabilir **çıkış** kullanıcıya iletileri sunmak için penceresi.

### <a name="find-message-in-code"></a>Kodda ileti bulma

Ekleme noktasını Seçili yapı hata içeren bir satır kod düzenleyicisinde taşır.

### <a name="go-to-previous-message"></a>Önceki iletiye gider.

Odak değişiklikleri **çıkış** önceki penceresine hata oluşturmak ve ekleme noktasını Kod Düzenleyicisi'nde hata yapı içeren satırına taşır.

### <a name="go-to-next-message"></a>Sonraki iletiye gider.

Odak değişiklikleri **çıkış** sonraki penceresine hata oluşturmak ve ekleme noktasını Kod Düzenleyicisi'nde hata yapı içeren satırına taşır.

### <a name="clear-all"></a>Tümünü temizle

Tüm metni temizler **çıkış** bölmesi.

### <a name="toggle-word-wrap"></a>Sözcük kaydırmayı değiştirme

Sözcük kaydırma özelliğini açar ve kapatır **çıkış** bölmesi. Sözcük kaydırma açık olduğunda görüntüleme alanı genişleten metin uzun girdileri aşağıdaki satırda görüntülenir.

## <a name="output-pane"></a>Çıkış bölmesi

**Çıkış** bölmesinde seçili **Göster çıktı** belirtilen kaynak çıktısını görüntüler.

## <a name="route-messages-to-the-output-window"></a>İletileri yönlendirmek için çıktı penceresi

Görüntülenecek **çıkış** bir projeyi de derleme zaman penceresi **seçenekleri** iletişim kutusundaki **projeler ve çözümler** > **genel**  sayfasında, **yapı başladığında Göster çıktı penceresi**. Düzenlemek için bir kod dosyası açıkken, ardından **sonraki iletiye gider** ve **önceki iletiyi** üzerinde **çıkış** girişleri seçmek için penceresi araç  **Çıktı** bölmesi. Bunu yaparken ekleme noktasını, seçilen sorunun oluştuğu kod satırı Kod Düzenleyicisi atlar.

Belirli IDE özellik ve çağrılması komutları [komut penceresi](../../ide/reference/command-window.md) çıktılarını için teslim **çıkış** penceresi. Çıktı dış araçları gibi *.bat* ve *.com* genellikle komut penceresinde görüntülenir, dosyalar için yönlendirilir bir **çıkış** seçtiğinizdebölmesi **Çıktı penceresi kullanmak** seçeneğini [dış araçları yönetme](../../ide/managing-external-tools.md). İletileri pek çok değişik görüntülenebilen **çıkış** bölmeleri de. Saklı yordam Transact-SQL söz dizimi hedef veritabanına karşı işaretlendiğinde, örneğin, sonuçları görüntülenir **çıkış** penceresi.

Çalışma zamanında tanılama iletileri yazmak için kendi uygulamalarınızı programlama yapabilirsiniz bir **çıkış** bölmesi. Bunu yapmak için üyeleri kullanın <xref:System.Diagnostics.Debug> sınıfı veya <xref:System.Diagnostics.Trace> sınıfını <xref:System.Diagnostics> ad alanı .NET Framework sınıf kitaplığı. Üyeleri <xref:System.Diagnostics.Debug> çözüm ya da proje hata ayıklama yapılandırmaları derlerken sınıfı görüntüsü çıkışı; üyeleri <xref:System.Diagnostics.Trace> sınıfı görüntüleme çıkış hata ayıklama veya yayın yapılandırmaları oluşturduğunuzda. Daha fazla bilgi için bkz: [çıktı penceresindeki tanılama iletileri](../../debugger/diagnostic-messages-in-the-output-window.md).

C++'da özel derleme adımları oluşturma ve derleme olayları, uyarıları ve hataları görüntülenir ve sayılı **çıkış** bölmesi. Basarak **F1** bir çıktı satıra uygun bir Yardım konusu görüntüleyebilirsiniz. Daha fazla bilgi için bkz: [özel derleme adımı çıktısını biçimlendirme](/cpp/ide/formatting-the-output-of-a-custom-build-step-or-build-event).

## <a name="scroll-behavior"></a>Kaydırma davranışı

İçinde autoscrolling kullanırsanız **çıkış** penceresi ve autoscrolling durdurur, fareyi veya ok tuşlarını kullanarak gidin. Autoscrolling sürdürmek için basın **Ctrl**+**son**.

## <a name="see-also"></a>Ayrıca bkz.

- [Çıktı penceresindeki tanılama iletileri](../../debugger/diagnostic-messages-in-the-output-window.md)
- [Nasıl yapılır: Çıktı penceresi denetleme](http://msdn.microsoft.com/Library/91aebd15-8854-4a7a-9f7d-57376fb4e858)
- [Derleme ve oluşturma](../../ide/compiling-and-building-in-visual-studio.md)
- [Derleme yapılandırmalarını anlama](../../ide/understanding-build-configurations.md)
- [Sınıf kitaplığına genel bakış](/dotnet/standard/class-library-overview)