---
title: Visual Studio'da yük testleri için veri ve tanılama eklerini görüntüleme
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, data and diagnostics attachments
ms.assetid: 73309bdd-437a-4eb0-88c8-702c3e24b9b0
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 228f8306b803fcbd0e83e23e5b8e919dc2116c37
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/31/2018
ms.locfileid: "39382470"
---
# <a name="how-to-view-data-and-diagnostic-attachments-using-the-load-test-analyzer"></a>Nasıl yapılır: veri ve yük testi çözümleyicisini kullanarak tanılama eklerini görüntüleme

Çalıştırmadan önce bir yük testi, kullanmak istediğiniz tanılama ve veri bağdaştırıcılarının belirten bir test ayarı seçebilirsiniz. Yük testi bittikten sonra kullandığınız **Yük Testi Çözümleyicisi** sonuçlarını analiz ederken, bu tanılama ve veri bağdaştırıcılarının ayrıntılarını görüntülemek için. Veri ve tanılama bağdaştırıcısı ayrıntılarını görüntülemek için seçin **veri ve Tanılama Eklerini Görüntüle** düğmesini **Yük Testi Çözümleyicisi** araç çubuğu. Örneğin, yük testi bir test ayarında yapılandırılan sistem bilgileri bağdaştırıcısına sahipse, yük testi çalıştırdığınızda, kullanılan makine için sistem bilgilerini görüntüleyebilirsiniz.

![Tanılama veri bağdaştırıcısı eki iletişim seçme](../test/media/load_adapterdialog.png)

IntelliTrace bağdaştırıcısını içeren test ortamında yük testi başka bir örnektir. IntelliTrace bağdaştırıcısını açmanızı sağlar **IntelliTrace özeti** sayfası.

![IntelliTrace özeti](../test/media/load_intellitrace.png)

Daha fazla bilgi için [test ayarlarını kullanarak tanılama bilgi toplayan](../test/collect-diagnostic-information-using-test-settings.md) ve [toplamak IntelliTrace verilerini](../test/how-to-collect-intellitrace-data-to-help-debug-difficult-issues.md).

## <a name="to-view-data-and-diagnostic-attachments-in-a-load-test-from-the-load-test-analyzer"></a>Bir yük testi Yük Testi Çözümleyicisi'ndan veri ve tanılama eklerini görüntülemek için

1.  Bir yük testi tamamlandıktan sonra veya bir yük testi sonucu açın, sonra **Yük Testi Çözümleyicisi** araç seçin **veri ve Tanılama Eklerini Görüntüle**.

     **Seçin, tanılama veri bağdaştırıcısı** iletişim kutusu görüntülenir.

2.  Analiz edin ve ardından istediğiniz tanılama veri bağdaştırıcısı eki Seç **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
