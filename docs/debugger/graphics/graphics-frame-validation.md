---
title: Grafik Çerçeve doğrulama | Microsoft Docs
ms.custom: ''
ms.date: 03/02/2017
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.graphics.FrameValidation
ms.assetid: 1e639182-1301-4e28-9c1e-b5df732f3f1b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3773fc5df0df05d3f275d7e628bef0def6290d3f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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