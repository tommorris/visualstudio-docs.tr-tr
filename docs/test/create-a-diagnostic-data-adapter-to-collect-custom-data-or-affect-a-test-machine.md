---
title: Visual Studio'da Test etmek için tanılama veri bağdaştırıcısı oluşturma
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Diagnostic Data Adapter [Visual Studio ALM]
- Diagnostic Data Adapter
ms.assetid: b0b53fae-7007-4ad9-a604-21685937622f
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: a514459e834e5652e544991eb061f0c96767dd32
ms.sourcegitcommit: 498e39e89a89ad7bf9dcb0617424fff999b1c3b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/21/2018
ms.locfileid: "36302646"
---
# <a name="create-a-diagnostic-data-adapter-to-collect-custom-data-or-affect-a-test-machine"></a>Özel veri toplayan veya test makinesini etkileyen tanılama veri bağdaştırıcısı oluşturma

Test çalıştırma veya test bir parçası olarak test makinesini etkileyen isteyebilirsiniz, veri toplamak için kendi tanılama veri bağdaştırıcısı oluşturmak isteyebilirsiniz. Örneğin, test altındaki uygulamanız tarafından oluşturulan ve test sonuçlarınızı ekleme günlük dosyaları toplamak isteyebilirsiniz veya bilgisayarınızda sol sınırlı disk alanı olduğunda testleri çalıştırmak isteyebilirsiniz. Visual Studio kuruluş içinde sağlanan API'leri kullanarak test çalışması belirli noktalarda görevler gerçekleştirmek üzere kod yazabilirsiniz. Örneğin, bir testi başlamadan önce ve sonra her test çalıştırıldığında ve test çalışması sona erdiğinde görevleri gerçekleştirebilirsiniz.

Özel tanılama veri bağdaştırıcınızı yapılandırma ayarları dosyası kullanarak varsayılan giriş sağlayabilirsiniz. Örneğin, dosyasının konumu hakkında bilgi toplamak ve test sonuçlarınızı eklemek istediğiniz sağlayabilir veya ne kadar disk alanı sistemde kalan istiyor. Bu veriler, oluşturduğunuz her test ayarları için yapılandırılabilir. Görüntülenebilir ve düzenlenen Microsoft Test Yöneticisi'ni veya, ile sağlanan varsayılan Düzenleyicisi'ni kullanarak bir düzenleyici olarak kullanmak için kendi kullanıcı denetimi oluşturabilirsiniz. Düzenleyicinizde bağdaştırıcısı yapılandırması için yapılan tüm değişiklikler, test ayarlarınızla depolanır.

Visual Studio'dan testler çalıştırıyorsanız, bu ayarlamalısınız etkin olması için test ayarları. Test ayarları hakkında daha fazla bilgi için bkz: [tanılama bilgileri toplama kullanarak test ayarlarını](../test/collect-diagnostic-information-using-test-settings.md).

## <a name="tasks"></a>Görevler

 Tanılama veri bağdaştırıcıları oluşturmanıza yardımcı olması için aşağıdaki konulara bakın:

|Görevler|İlişkili Konular|
|-----------|-----------------------|
|**Tanılama veri bağdaştırıcısı oluşturma:** bir sınıf kitaplığı oluşturarak tanılama veri bağdaştırıcısı oluşturmak ve bilgiyi toplamak istediğiniz veya testleri çalıştırmak için kullandığınız bir test sistemini etkilemek için tanılama veri bağdaştırıcısı API'leri kullanın.|-   [Nasıl yapılır: tanılama veri bağdaştırıcısı oluşturma](../test/how-to-create-a-diagnostic-data-adapter.md)|
|**Özel tanılama veri bağdaştırıcısı yükleme:** tanılama veri bağdaştırıcınızın veya doğru dizine kopyalayarak başkası tarafından sağlanan bir bağdaştırıcı yükleyebilirsiniz.|-   [Nasıl yapılır: özel tanılama veri bağdaştırıcısı yükleme](../test/how-to-install-a-custom-diagnostic-data-adapter.md)|
|**Kullanın, testleri için özel tanılama veri bağdaştırıcısı seçme çalıştırılır:** test ayarlarınız için kullanmak üzere hangi tanılama veri bağdaştırıcısı testlerinizi çalıştırdığınızda bağdaştırıcısı kullanılan seçebilirsiniz.|-   [(VSTS) test ederken tanılama verisi toplama](/vsts/manual-test/collect-diagnostic-data)<br />-   [El ile testlerde (VSTS) tanılama verisi toplama](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests)|
|**Tanılama veri bağdaştırıcısı yaptığı yapılandırma:** tanılama veri bağdaştırıcısı bu belirli test ayarlarında eylemlerini denetlemek için ayarları yapılandırabilirsiniz.|-   [Nasıl yapılır: tanılama veri bağdaştırıcınızın verileri için bir özel düzenleyici oluşturma](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md)|

## <a name="see-also"></a>Ayrıca bkz.

- [Tanılama veri bağdaştırıcısı oluşturmak için örnek proje](../test/sample-project-for-creating-a-diagnostic-data-adapter.md)
- [Test ayarlarını kullanarak tanılama bilgileri Topla](../test/collect-diagnostic-information-using-test-settings.md)