---
title: "Nasıl yapılır: Visual Studio'da özel tanılama veri bağdaştırıcısı yükleme"
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Diagnostic Data Adapter, installing
ms.assetid: 907e65d8-0408-44b3-9e5e-e631892c1726
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 0755f77b2eea2860a3514480504c7aed041711d4
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/31/2018
ms.locfileid: "39379295"
---
# <a name="how-to-install-a-custom-diagnostic-data-adapter"></a>Nasıl yapılır: özel tanılama veri bağdaştırıcısı yükleme

Özel tanılama veri bağdaştırıcısı oluşturduysanız veya size bir özel tanılama veri bağdaştırıcısı ile kullanmak için sağlanmış olan derleme dosyası için yerel makinenizde doğru dizine kopyalayarak tanılama veri bağdaştırıcısı derlemenizi yükleyebilirsiniz.

 Ortamdaki bir rol için özel tanılama veri bağdaştırıcınızı kullanmak istiyorsanız, bu rol için kullanılabilecek test aracılarını tüm makinelerde tanılama veri bağdaştırıcınızı yüklemeniz gerekir.

 Özel tanılama bağdaştırıcınızı uygun yerlere yüklemek için aşağıdaki yordamı kullanın. Tanılama veri bağdaştırıcısını yüklediğiniz tüm makinelerde yönetimsel izinlere ihtiyacınız.

## <a name="install-a-custom-diagnostic-data-adapter"></a>Özel tanılama veri bağdaştırıcısı yükleme

### <a name="to-install-a-custom-diagnostic-data-adapter"></a>Özel tanılama veri bağdaştırıcısı yüklemek için

1.  İstemci makinenizde veya bir aracı makinede testler çalıştırırken tanılama veri bağdaştırıcısı kullanmak için yapı dizininizden tüm dosyaları yükleme yoluna göre hedef makinedeki aşağıdaki dizine kopyalayın:

     *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies\DataCollectors*

     Kopyalanacak dosyaları şunlardır:

    -   Tanılama veri bağdaştırıcısı derlemesi (*.dll*) (gerekli).

    -   Hata ayıklama veri dosyası (*.pdb*) (isteğe bağlı) bağdaştırıcı.

    -   Bağdaştırıcı yapılandırma dosyası (`<diagnostic data adapter name>.dll.config`), varsayılan yapılandırma ayarları (isteğe bağlı) varsa.

    -   (İsteğe bağlı) bağdaştırıcı yapılandırma ayarlarını düzenlemek için oluşturduysanız yapılandırma düzenleyicisi derleme. Bu, yalnızca istemci makineler içindir. Aracı makineleri düzenleyiciyi kullanmaz.

    > [!NOTE]
    > Tanılama veri bağdaştırıcınız ve yapılandırma düzenleyiciniz aynı projede oluşturulup aynı derlemeye yerleştirilebilse de ayrı projeler kullanabilir ve isterseniz onlar için ayrı derlemeler oluşturabilirsiniz.

     Test ayarlarınızı testlerinizi çalıştırdığınızda kullanacağınız ortam için yapılandırma hakkında daha fazla bilgi için bkz. [el ile testler (VSTS), tanılama verilerini toplama](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests).

2.  Bir test için tanılama veri bağdaştırıcınızı seçmek için önce varolan test ayarlarını seçin veya yeni bir Microsoft Test Yöneticisi ya da Visual Studio ve gerekir tanılama veri bağdaştırıcınızı seçin **veri ve tanılama** Seçili test ayarları sekmesi.

3.  Belirleyin oluşturulur ve test ayarlarınız için tanılama veri bağdaştırıcınızı yapılandırmak için bir tanılama veri bağdaştırıcısı yapılandırma Düzenleyicisi, yüklü **yapılandırma** yapma ve bağdaştırıcısı yanındaki değişiklikler. Ardından **Kaydet**. Yapılandırma Düzenleyicisi, tanılama veri toplayıcınız için oluşturma hakkında daha fazla bilgi için bkz. [nasıl yapılır: tanılama veri bağdaştırıcınızın verileri için özel bir düzenleyici oluşturmak](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md).

4.  Microsoft Test Yöneticisi'nden testleri çalıştırıyorsanız, bunları atayabilir kullanmadan veya testlerinizi çalıştırmadan önce test planınıza test **seçenekler ile Çalıştır** komut test ayarlarınızı atamak ve yok saymak için test ayarları. Test ayarları hakkında daha fazla bilgi için bkz. [test ayarlarını kullanarak tanılama bilgi toplayan](../test/collect-diagnostic-information-using-test-settings.md).

     Testlerinizi Visual Studio'dan çalıştırıyorsanız, bunları ayarlamalısınız etkin olması için test ayarları. Test ayarları hakkında daha fazla bilgi için bkz. [test ayarlarını kullanarak tanılama bilgi toplayan](../test/collect-diagnostic-information-using-test-settings.md).

5.  Seçilen tanılama veri bağdaştırıcısıyla test ayarlarını kullanarak testlerinizi çalıştırın.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: tanılama veri bağdaştırıcısı oluşturma](../test/how-to-create-a-diagnostic-data-adapter.md)
- [Nasıl yapılır: tanılama veri bağdaştırıcınızın verileri için özel bir düzenleyici oluşturma](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md)
- [Tanılama veri bağdaştırıcısı oluşturmak için örnek proje](../test/sample-project-for-creating-a-diagnostic-data-adapter.md)
- [Özel veri toplayan veya test makinesini etkileyen tanılama veri bağdaştırıcısı oluşturma](../test/create-a-diagnostic-data-adapter-to-collect-custom-data-or-affect-a-test-machine.md)
- [Test ayarlarını kullanarak tanılama bilgileri Topla](../test/collect-diagnostic-information-using-test-settings.md)