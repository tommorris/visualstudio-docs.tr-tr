---
title: "Düzenleyici davranışı | Microsoft Docs"
description: 
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: 81EE4460-26EB-4BB0-9297-932E1F88E4B8
ms.openlocfilehash: 3515dfbf3a7cf8c23178aa9df243638f955593e9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="editor-behavior"></a>Düzenleyici davranışı

Düzenleyici davranışları yazılması olarak biçimlendirilmesi için kod izin verecek şekilde ayarlayabilirsiniz. Bu eylemler altında ayarlanır **Visual Studio > tercihleri... > Metin Düzenleyicisi > davranışı**, ve daha sık kullanılan işlevler bazıları aşağıda açıklanmıştır:

![Düzenleyici davranışı seçenekleri](media/source-editor-image9.png)

*  Kapanış köşeli parantez eşleşen otomatik olarak kod yeni sınıfları, yöntemleri veya özellikleri oluşturulurken eklenebilir. Bu seçenek belirlendiğinde, yazarak `{` otomatik olarak ekleyecek `}`.
* Üzerinde-çalışma sırasında kod biçimlendirme, noktalı virgül veya ayarlanan biçimlendirme Tercihler öykünür küme ayraçları gibi karakter basarsa tarafından tetiklenir.
* Dosya, istendiği kod yazılmasını sağlar ve IDE kod kümesi olarak mevcut Tercihler tarafından biçimlendirme sorumlu bırakır kaydedilirken biçimlendirmek seçebilirsiniz.
* Girinti None, otomatik, ayarlanması veya akıllı. Bunlar aşağıdakileri yapın:
 * Sonraki satıra başlangıcına hiçbiri - ayarlar düzeltme işareti
 * Otomatik - şapka aynı sütuna sonraki satırında ayarlar.
 * Akıllı - koduna göre aşağıdaki satırı girintileri
* İşletim sistemleri arasında Sözcük bölünmesi davranış farklıdır ve gezinti amacıyla, metin düzenleyici sözcükler burada başlayamaz veya bitemez bilmek ister. Biçimlendirme UNIX ya da Windows için ayarlanabilir.

Ayrıca, XML, CSS, HTML ve JSON için biçimlendirme kuralları ayarlayabilirsiniz.