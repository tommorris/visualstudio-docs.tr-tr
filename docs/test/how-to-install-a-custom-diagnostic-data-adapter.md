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
ms.openlocfilehash: d24ce9f954164cd8d243edfab4387f6b174c0648
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-install-a-custom-diagnostic-data-adapter"></a>Nasıl yapılır: Özel Tanılama Veri Bağdaştırıcısı Yükleme

Özel tanılama veri bağdaştırıcısı oluşturduğunuz veya kullanmak için bir özel tanılama veri bağdaştırıcısı ile sağlanmış olan, derleme dosyası için doğru dizine yerel makinenizde kopyalayarak tanılama veri bağdaştırıcısı derlemenizi yükleyebilirsiniz.

 Bir ortamda bir rol için özel tanılama veri bağdaştırıcınızı kullanmak istiyorsanız, bu rol için kullanılan test aracılarını çalıştırmak tüm makinelerde tanılama veri bağdaştırıcısı yüklemeniz gerekir.

 Özel tanılama bağdaştırıcınızı uygun yerlere yüklemek için aşağıdaki yordamı kullanın. Tanılama veri bağdaştırıcısı yüklediğiniz herhangi bir makinede yönetici izinleri gerekir.

## <a name="installing-a-custom-diagnostic-data-adapter"></a>Özel tanılama veri bağdaştırıcısı yükleme

### <a name="to-install-a-custom-diagnostic-data-adapter"></a>Özel tanılama veri bağdaştırıcısı yüklemek için

1.  İstemci makinenizde veya aracı makine testlerini çalıştırdığınızda, tanılama veri bağdaştırıcısı kullanmak için aşağıdaki dizine yükleme yola göre hedef makinede yapı dizininizden tüm dosyaları kopyalayın:

     *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies\DataCollectors*

     Kopyalanacak dosyaların şunlardır:

    -   (Gerekli) tanılama veri bağdaştırıcısı derlemesi (.dll).

    -   Hata ayıklama için veri dosyası (.pdb) bağdaştırıcınızı (isteğe bağlı).

    -   Bağdaştırıcınızı yapılandırma dosyası (`<diagnostic data adapter name>.dll.config`), varsayılan yapılandırma ayarları (isteğe bağlı) varsa.

    -   (İsteğe bağlı) bağdaştırıcısı için yapılandırma ayarlarını düzenlemek için oluşturduysanız yapılandırma düzenleyicisi derleme. Bu, yalnızca istemci makineler içindir. Aracı makineleri Düzenleyicisi kullanmayın.

    > [!NOTE]
    > Tanılama veri bağdaştırıcınızın ve yapılandırma Düzenleyicisi aynı projede oluşturulup aynı derlemeye yerleşik rağmen ayrı projeler kullanabilir ve isterseniz bunları için ayrı derlemeler oluşturun.

     Testlerinizi çalıştırdığınızda, bir ortam kullanmak için test ayarlarını yapılandırma hakkında daha fazla bilgi için bkz: [el ile testlerde (VSTS) Tanılama verileri toplama](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests).

2.  Bir test için tanılama veri bağdaştırıcınızı seçmek için önce varolan test ayarlarını seçin veya yeni bir Microsoft Test Yöneticisi'ni ya da Visual Studio oluşturup gerekir üzerinde tanılama veri bağdaştırıcınızı seçmek **veri ve tanılama** Seçili test ayarları sekmesi.

3.  Oluşturulan ve test ayarlarınız için tanılama veri bağdaştırıcınızı yapılandırmak için bir tanılama veri bağdaştırıcısı yapılandırma Düzenleyicisi, yüklediyseniz seçin **yapılandırma** bağdaştırıcısı ve yapma yanındaki değişiklikler. Ardından **kaydetmek**. Tanılama veri toplayıcınız için Düzenleyicisi yapılandırmanın oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: tanılama veri bağdaştırıcısı bilgisayarınızı veri için bir özel düzenleyici oluşturma](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md).

4.  Microsoft Test Yöneticisi'nden testlerinizi çalıştırıyorsanız, bu atayabilirsiniz testleri çalıştırma veya kullanmadan önce test ayarları test planınıza **seçenekleriyle çalıştırın** test ayarlarınızı atamak ve geçersiz kılmak için komut test ayarları. Test ayarları hakkında daha fazla bilgi için bkz: [toplamak tanılama bilgileri kullanarak Test ayarlarını](../test/collect-diagnostic-information-using-test-settings.md).

     Visual Studio'dan testler çalıştırıyorsanız, bu ayarlamalısınız etkin olması için test ayarları. Test ayarları hakkında daha fazla bilgi için bkz: [toplamak tanılama bilgileri kullanarak Test ayarlarını](../test/collect-diagnostic-information-using-test-settings.md).

5.  Seçilen tanılama veri bağdaştırıcısı ile test ayarlarını kullanarak testleri çalıştırın.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: tanılama veri bağdaştırıcısı oluşturma](../test/how-to-create-a-diagnostic-data-adapter.md)
- [Nasıl yapılır: tanılama veri bağdaştırıcınızın verileri için bir özel düzenleyici oluşturma](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md)
- [Tanılama veri bağdaştırıcısı oluşturmak için örnek proje](../test/sample-project-for-creating-a-diagnostic-data-adapter.md)
- [Özel veri toplayan veya Test makinesini etkileyen tanılama veri bağdaştırıcısı oluşturma](../test/create-a-diagnostic-data-adapter-to-collect-custom-data-or-affect-a-test-machine.md)
- [Test ayarlarını kullanarak tanılama bilgileri Topla](../test/collect-diagnostic-information-using-test-settings.md)