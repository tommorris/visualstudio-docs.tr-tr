---
title: Visual Studio'nun verilere bağlı denetimler için başlık oluşturma biçimini özelleştirme
ms.date: 11/03/2017
ms.topic: conceptual
helpviewer_keywords:
- Label captions, Data Sources window
- smart captions
- captions, data-bound
- Data Sources Window, label captions
ms.assetid: 6d4d15f8-4d78-42fd-af64-779ae98d62c8
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 69e97efe6db8b06f476b7dc004e3b52a77701cb0
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36758426"
---
# <a name="customize-how-visual-studio-creates-captions-for-data-bound-controls"></a>Visual Studio'nun verilere bağlı denetimler için başlık oluşturma biçimini özelleştirme

Öğelerden sürüklediğinizde [veri kaynakları penceresi](add-new-data-sources.md) bir tasarımcı bir ayrıcalık oyuna gelir: resim yazısı etiketleri içindeki sütun adlarının yeniden biçimlendirilen daha okunabilir bir dizeye iki veya daha fazla sözcükler olarak bulunan birlikte art arda eklenmiş. İçinde bu etiketler oluşturulur, ayarlayarak şekilde özelleştirebilirsiniz **SmartCaptionExpression**, **SmartCaptionReplacement**, ve **SmartCaptionSuffix** değerler **HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\15.0\Data tasarımcıları** kayıt defteri anahtarı.

> [!NOTE]
> Oluşturduğunuz kadar bu kayıt defteri anahtarı yok.

Akıllı açıklamalı alt yazı değeri girdiğiniz normal ifade tarafından denetlenir **SmartCaptionExpression** değeri. Ekleme **veri tasarımcıları** kayıt defteri anahtarı başlık denetimleri varsayılan normal ifade geçersiz kılar. Normal ifadeler hakkında daha fazla bilgi için bkz: [Visual Studio'da normal ifadeler kullanarak](../ide/using-regular-expressions-in-visual-studio.md).

Başlık denetleyen kayıt defteri değerleri aşağıdaki tabloda açıklanmaktadır.

|Kayıt defteri öğesi|Açıklama|
|-------------------|-----------------|
|**SmartCaptionExpression**|Normal ifade alışkanlıklarınıza eşleştirmek için kullanın.|
|**SmartCaptionReplacement**|İçinde eşleşen gruplarını görüntülemek için kullanılacak biçimi **SmartCaptionExpression**.|
|**SmartCaptionSuffix**|Resim yazısını sonuna eklenecek isteğe bağlı bir dize.|

Aşağıdaki tabloda, bu kayıt defteri değerlerini iç varsayılan ayarlarını listeler.

|Kayıt defteri öğesi|Varsayılan değer|Açıklama|
|-------------------|-------------------|-----------------|
|**SmartCaptionExpression**|**(\\\p{Ll}) (\\\p{Lu})&#124;_ +**|Bir büyük harf karakter veya alt çizgiyle tarafından izlenen bir küçük harf karakterle eşleşir.|
|**SmartCaptionReplacement**|**$1 $2**|**$1** ifade ilk parantez içinde eşleşen herhangi bir karakteri temsil eder ve **$2** ikinci parantez içinde eşleşen herhangi bir karakteri temsil eder. İlk eşleşmeye, boşluk ve ardından ikinci eşleşme yerini alır.|
|**SmartCaptionSuffix**|**:**|Döndürülen dize eklenmiş bir karakteri temsil eder. Örneğin, resim yazısını ise `Company Name`, sonek kolaylaştırır `Company Name:`|

> [!CAUTION]
> Kayıt Defteri Düzenleyicisi'nde hiçbir şey yaparken çok dikkatli olmanız gerekir. Düzenlemeye başlamadan önce kayıt defterini yedekleyin. Kayıt Defteri Düzenleyicisi'ni yanlış kullanırsanız, işletim sisteminizi yeniden yüklemenizi gerektirebilecek önemli sorunlara neden olabilir. Microsoft Kayıt Defteri Düzenleyicisi'ni kullanarak neden sorunları çözmek için garanti etmez. Kayıt Defteri Düzenleyicisi'ni kullanım riski size aittir.
>
> Aşağıdaki Bilgi Bankası makalesi yedekleme, düzenleme ve kayıt defterini geri yüklemek için yönergeleri içerir: [Microsoft Windows kayıt defterinin açıklaması](http://support.microsoft.com/default.aspx?scid=kb;en-us;256986) (http://support.microsoft.com/default.aspx?scid=kb; en-us; 256986)

## <a name="modify-the-smart-captioning-behavior-of-the-data-sources-window"></a>Veri kaynakları penceresinden akıllı açıklamalı alt yazı davranışını değiştirmek

1.  Bir komut penceresi açın **Başlat** ve ardından **çalıştırmak**.

2.  Tür `regedit` içinde **çalıştırmak** iletişim kutusu ve tıklatın **Tamam**.

3.  Genişletme **HKEY_CURRENT_USER** > **yazılım** > **Microsoft** > **Visual Studio**düğüm.

7.  Sağ **15.0** düğümü ve yeni bir **anahtar** adlı `Data Designers`.

8.  Sağ **veri tasarımcıları** düğümü ve üç yeni dize değerlerini oluşturun:

    - `SmartCaptionExpression`
    - `SmartCaptionReplacement`
    - `SmartCaptionSuffix`

11. Sağ **SmartCaptionExpression** değer ve seçin **Değiştir**.

12. İstediğiniz normal ifade girin **veri kaynakları** penceresini kullanın.

13. Sağ **SmartCaptionReplacement** değer ve seçin **Değiştir**.

14. Değiştirme girin, normal ifade ile eşleşen desenleri görüntülemek istediğiniz şekilde biçimlendirilmiş dize.

15. Sağ **SmartCaptionSuffix** değer ve seçin **Değiştir**.

16. Resim yazısını sonunda görünmesini istediğiniz herhangi bir karakter girin.

    Sonraki öğelerinden sürükleyin **veri kaynakları** penceresinin başlık etiketleri oluşturulur sağlanan yeni kayıt defteri değerleri kullanarak.

## <a name="turn-off-the-smart-captioning-feature"></a>Akıllı resim yazısı özelliğini kapatma

1.  Bir komut penceresi açın **Başlat** ve ardından **çalıştırmak**.

2.  Tür `regedit` içinde **çalıştırmak** iletişim kutusu ve tıklatın **Tamam**.

3.  Genişletme **HKEY_CURRENT_USER** > **yazılım** > **Microsoft** > **Visual Studio**düğüm.

7.  Sağ **15.0** düğümü ve yeni bir **anahtar** adlı `Data Designers`.

8.  Sağ **veri tasarımcıları** düğümü ve üç yeni dize değerlerini oluşturun:

    - `SmartCaptionExpression`
    - `SmartCaptionReplacement`
    - `SmartCaptionSuffix`

11. Sağ **SmartCaptionExpression** öğesi ve seçin **Değiştir**.

12. Girin `(.*)` değeri. Bu, tüm dizeyi eşleştir.

13. Sağ **SmartCaptionReplacement** öğesi ve seçin **Değiştir**.

14. Girin `$1` değeri. Bu dize tüm dize ve böylece değişmeden kalır eşleşen değeri ile değiştirir.

    Sonraki öğelerinden sürükleyin **veri kaynakları** penceresinin başlık etiketleri değiştirilmemiş resim yazıları ile oluşturulur.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da verilere denetimler bağlama](../data-tools/bind-controls-to-data-in-visual-studio.md)