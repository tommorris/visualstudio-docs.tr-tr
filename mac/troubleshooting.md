---
title: Mac sorun giderme için visual Studio
description: Ortak sorunlar ve çözümleri Visual Studio için Mac kullanıcıları için.
ms.topic: troubleshooting
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.assetid: CE860D79-E29E-4B93-B094-BE74B35FC1C2
ms.openlocfilehash: 4a6b5d2f3c5e6c84307d70308773dd353c6de883
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="troubleshooting"></a>Sorun giderme

## <a name="viewing-logs-in-visual-studio-for-mac"></a>Mac için Visual Studio'da günlüklerini görüntüleme

Günlükleri göz atarak bulunabilir **Yardım > açık günlük dizini** menü öğesi, aşağıda gösterildiği gibi:

![Günlük dizini menü öğesini Aç](media/troubleshooting-image1.png)

## <a name="viewing-exceptions"></a>Özel durumları görüntüleme

Bir özel durum yakalandı, bir özel durum Kabarcık görünür. Daha fazla ayrıntı görüntülemek için seçin **ayrıntıları görüntüle** düğmesi:

![Bir özel durum hakkında daha fazla ayrıntı görüntülemek](media/troubleshooting-image2.png)

Bu görüntüler **ayrıntıları göster** özel durumla ilgili daha fazla bilgi sağlayan iletişim:

![](media/troubleshooting-image3.png)

Yukarıdaki numaralı iletişim önemli bölümlerini aşağıda ayrıntılı olarak açıklanmıştır:

1. Özel durum türü gözlenir özel durum türünün tam adını gösterir.
2. Özel durum iletisi özel durum nesnesinin ileti özelliği değerini gösterir.
3. Özel durum türü tam adı şu anda seçili durum için iç özel durum ağaç görünümünde gösterilir iç özel durum türü.
4. İç özel durum iletisi iç özel durum ağaç görünümünde seçilen özel durum iletisi özelliğinin değerini gösterir.
5. Stacktrace görüntüleyin. Bu açıklama ok daraltılmış ve yığın çerçeveleri girişleri içerir.
6. Kullanıcı olmayan kod girişleri örneği.
7. Kullanıcı kodu girişleri örneği.
8. Tüm özellikleri ve alanları özel durumun gösterir özelliklerini görüntüleyin. Bu, bir açıklama ok daraltılmış olabilir.
9. İç özel duruma ağaç görünümü. Bu görünümde yukarı/aşağı ok veya fare ya da izleme paneli ile klavyeden iç özel durum seçin.
10. Varsayılan olarak, bu ne ayarlanır **yalnızca proje kodunda hata ayıklama** hata ayıklayıcı ayarları seçeneğinde ayarlanır. Bu kutuyu seçerek tek bir satır stacktrace olarak daraltmak tüm kullanıcı olmayan kod olanak sağlar.
11. Kopyalamak için Kopyala düğmesine `exception.ToString()` panoya çıktı.

Özel durum bir iç özel duruma sahip olduğunda bu bölümleri bazıları yalnızca görünür olacağını unutmayın.