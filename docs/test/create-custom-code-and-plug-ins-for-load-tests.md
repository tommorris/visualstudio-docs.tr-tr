---
title: Özel kod ve eklentiler yük testleri için Visual Studio'da oluşturma
ms.date: 10/19/2016
ms.topic: conceptual
f1_keywords:
- vs.test.dialog.recorderplugin
helpviewer_keywords:
- Web performance tests, plug-ins
- load tests, plug-ins
ms.assetid: 0c0fcc99-673b-4ea0-a268-0475f66e5cb6
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 55386b5e586b88e91e252280da9510ce395daf78
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31965830"
---
# <a name="create-custom-code-and-plug-ins-for-load-tests"></a>Yük testleri için özel kod ve eklentiler oluşturma

Özel bir eklenti yazma ve bir yük testi veya Web performans testine ekleme kodu kullanır. Yerleşik işlevselliği genişletmek testleri için özel eklentiler oluşturmak için yük testi API'si ve Web performans testi API'sini kullanabilirsiniz. Yükleme testiniz birden fazla eklenti ekleyebilirsiniz.

## <a name="tasks"></a>Görevler

|Görevler|İlgili Konular|
|-----------|-----------------------|
|**Özel bir yük testi eklentisi oluşturma**: özel bir yük testine daha fazla işlevsellik eklemek için eklenti oluşturmak için yük testi API'sini kullanabilirsiniz.|-   [Nasıl yapılır: yük testi API'si kullanma](../test/how-to-use-the-load-test-api.md)<br />-   [Nasıl yapılır: yük testi eklentisi oluşturma](../test/how-to-create-a-load-test-plug-in.md)|
|**Özel bir Web performans testi eklentisi oluşturma:** özel bir Web performans testi isteği düzeyinde de dahil olmak üzere, daha fazla test işlevselliği eklemek için eklenti oluşturmak için Web performans testi API'sini kullanabilirsiniz. Bir Web hizmeti testi de oluşturabilirsiniz.<br /><br /> Ayrıca, bir Web kaydedici eklentisi Web performans testine kaydedildikten sonra ancak Web Performans Testi Sonuç Görüntüleyicisi'nde görünmeden önce değiştirebilirsiniz oluşturabilirsiniz.|-   [Nasıl yapılır: Web başarım testi API'si kullanma](../test/how-to-use-the-web-performance-test-api.md)<br />-   [Nasıl yapılır: Web başarım testi eklentisi oluşturma](../test/how-to-create-a-web-performance-test-plug-in.md)<br />-   [Nasıl yapılır: istek düzeyi eklentisi oluşturma](../test/how-to-create-a-request-level-plug-in.md)<br />-   [Nasıl yapılır: Web hizmet testi oluşturma](../test/how-to-create-a-web-service-test.md)<br />-   [Nasıl yapılır: kaydedici eklentisi oluşturma](../test/how-to-create-a-recorder-plug-in.md)|
|**Web Performans Testi Sonuçları Görüntüleyicisi için kullanıcı Arabirimi özellikleri ekleyin:** Visual Studio eklentisini kullanarak Web Performans Testi Sonuçları Görüntüleyicisi için daha fazla kullanıcı Arabirimi özelliklerini ekleyebilirsiniz.|-   [Nasıl yapılır: Web Performans Testi Sonuçları Görüntüleyicisi için Visual Studio eklentisi oluşturma](../test/how-to-create-an-add-in-for-the-web-performance-test-results-viewer.md)|
|**Özel HTTP Gövde Düzenleyicisi oluşturma:** bir web hizmetinden ikili veya dize http XML yanıtlarını düzenlemek için özel bir düzenleyici oluşturabilirsiniz.|-   [Nasıl yapılır: bir özel HTTP Gövde Düzenleyicisi için Web Performans Testi Düzenleyicisi oluşturma](../test/how-to-create-a-custom-http-body-editor-for-the-web-performance-test-editor.md)|

## <a name="reference"></a>Başvuru

<xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestPlugin>

<xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRequestPlugin>

<xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin>

<xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRecorderPlugin>

<xref:Microsoft.VisualStudio.TestTools.LoadTesting>

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Oluşturma ve kodlanmış web performans testini çalıştırma](../test/generate-and-run-a-coded-web-performance-test.md)