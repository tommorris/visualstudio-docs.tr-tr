---
title: "Grafik Çerçeve doğrulama | Microsoft Docs"
ms.custom: 
ms.date: 03/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.graphics.FrameValidation
ms.assetid: 1e639182-1301-4e28-9c1e-b5df732f3f1b
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d349222b138a8d5c359d174849faf7641befc482
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="graphics-frame-validation"></a>Grafik Çerçeve doğrulama
<!-- VERSIONLESS -->
Visual Studio 2017 ve daha fazla destek **çerçeve doğrulama** aracı.  Çerçeve doğrulama penceresi hataları ve Uyarıları olay listesiyle ilişkilendirilmiş görüntüler.  Bu pencereyi görüntülemek için seçin **Görünüm > Çerçeve doğrulama** menüsü.

![Çerçeve doğrulama](media/gfx_diag_frame_validation.png)

Tıklatın **doğrulama çalışması** analiz başlatmak için sol üst köşede düğmesini.  Çerçeve karmaşıklığına bağlı olarak tamamlanması birkaç dakika sürebilir.  İki kaynak bileşiminden İşte görüntülenen verileri: iletileri bu D3D kendisini ne zaman yayar [SDK katmanları](https://msdn.microsoft.com/library/windows/desktop/ff476881(v=vs.85).aspx) etkin ve izleme aracın kendi iç durumundan toplanan verileri. Tamamlandıktan sonra birkaç veri sütunlarının görürsünüz:

**Sütun**|**Açıklama**
---|---
Olay Kimliği | İçindeki bir girdiye eşleştiren kimliği [olay listesi](graphics-event-list.md) penceresi.
Önem Derecesi | Bozulması, hata, uyarı, bilgi veya ileti.
Kategori | Uygulama tanımlı, çeşitli, başlatma, temizleme, derleme, durum oluşturma, durum ayarı, durum alınıyor, yürütme, kaynak işleme, gölgelendirici, gereksiz ve kullanılmayan.
İleti | Olayla ilişkili ileti.
Olay | Hata veya uyarı ile ilişkili olay.

## <a name="see-also"></a>Ayrıca Bkz.  
[Grafik tanılama (hata ayıklama DirectX grafik)](visual-studio-graphics-diagnostics.md)   
<!-- /VERSIONLESS -->