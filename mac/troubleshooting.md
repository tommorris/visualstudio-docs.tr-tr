---
title: Sorun giderme | Microsoft Docs
description: 
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: CE860D79-E29E-4B93-B094-BE74B35FC1C2
ms.openlocfilehash: 4e483548e916bf00b07c472b18adac8504b6e967
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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