---
title: "İzlenecek yol: Visual Studio uzantısı yayımlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- publishing web controls
- web controls, publishing
ms.assetid: a7816161-0490-4043-86f5-0f7331ed83b3
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 9b2823c15309e63262052fd3cc95d914bf1614c4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-publishing-a-visual-studio-extension"></a>İzlenecek yol: Visual Studio uzantısını yayımlama

Bu kılavuz, Visual Studio Market'te Visual Studio uzantısı yayımlamak nasıl gösterir. Market'te uzantınızı eklediğinizde, geliştiriciler kullanabilir **Uzantılar ve güncelleştirmeler** için yeni ve güncelleştirilmiş uzantıları var. gidin.

## <a name="prerequisites"></a>Önkoşullar

 Bu kılavuzda izlemek için Visual Studio SDK'yı yüklemeniz gerekir. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).

## <a name="create-a-visual-studio-extension"></a>Visual Studio uzantısı oluşturma

Bu durumda biz varsayılan VSPackage uzantısı kullanır, ancak aynı adımları her uzantı türü için geçerlidir.

1. C# ' "menü komutu sahip TestPublish" adlı bir VSPackage oluşturun. Daha fazla bilgi için bkz: [ilk uzantınızı oluşturma: Hello World](../extensibility/extensibility-hello-world.md).

## <a name="package-your-extension"></a>Uzantınızı paketi

1. Ürün adı, yazar ve sürüm doğru bilgilerle uzantısı vsixmanifest güncelleştirin.

  ![Uzantı vsixmanifest güncelleştir](media/update-extension-vsixmanifest.png)

2. Uzantınızı yapı içinde **sürüm** modu. Şimdi uzantınızı VSIX \bin\Release klasöründeki olarak paketlenmiş.

3. Yüklemeyi doğrulamak için VSIX çift tıklayabilirsiniz.

## <a name="test-the-extension"></a>Uzantı test

 Uzantı dağıtmadan önce yapı ve Visual Studio deneysel örneğinde doğru şekilde yüklendiğinden emin olmak için test.

1. Visual Studio'da hata ayıklamayı Başlat. Visual Studio deneysel örneği açmak için.

2. Deneysel örneğinde Git **Araçları** menüsüne ve ardından **Uzantılar ve güncelleştirmeler...** . TestPublish uzantısı Orta bölmede görünür olmalıdır ve etkinleştirilmiş olmalıdır.

3. Üzerinde **Araçları** menüsünde, test komutunun gördüğünüzden emin olun.

## <a name="publish-the-extension-to-the-visual-studio-marketplace"></a>Visual Studio Market'te uzantısını yayımlama

1. Uzantınızı sürümünü oluşturduktan ve güncel olduğundan emin olun.

2. Bir web tarayıcısında Aç [Visual Studio Market'te](https://marketplace.visualstudio.com/vs) Web sitesi.

3. Sağ üst köşesinde tıklatın **oturum**.

4. Oturum açmak için Microsoft hesabınızı kullanın. Bir Microsoft hesabınız yoksa, bir bu noktada oluşturabilirsiniz.

5. Tıklatın **uzantılarını yayımlama**.  Bu, tüm uzantıları Yönetme sayfasına gider.  Bir yayımcı hesabınız yoksa, şu anda oluşturmanız istenir.

  ![Market'te karşıya yükle](media/upload-to-marketplace.png)

6. Uzantınızı karşıya yüklemek için kullanmak istediğiniz publisher'ı seçin.  Sol üst köşesindeki yayımcı adına tıklayarak yayımcılar değiştirebilirsiniz.

  ![Değiştirme Market yayımcısı](media/change-marketplace-publisher.png)

7. İçinde **1: karşıya uzantısı**, doğrudan Visual Studio Market'te VSIX dosya yüklemeye veya yalnızca kendi Web sitesine bağlantı eklemek seçebilirsiniz. Bu durumda, biz TestPublish.vsix bizim uzantısı karşıya yükler.  Sürükleyip uzantınızı bırakın veya kullanmak **tıklatın** dosyasını bulmak için bağlantı.  Uzantınızı proje \bin\Release klasöründe bulunabilir.  
              **Devam**'a tıklayın.

8. İçinde **2: uzantısı ayrıntıları**, otomatik olarak doldurulmuş bazı alanlar uzantınızı source.extension.vsixmanifest dosyasından.  Aşağıda her hakkında daha fazla ayrıntı bulunabilir:

    * **İç adı** uzantının ayrıntı sayfası URL'de kullanılacak. Bir örnek için yayımcı adı "myname" altında bir uzantı yayımlama ve "myextension" olarak iç adı belirterek bir URL neden olacak "marketplace.visualstudio\.com/items?itemName=myname.myextension", uzantının için Ayrıntı Sayfası.
    
    * **Görünen ad** uzantınızın.  Bu, source.extension.vsixmanifest dosyasından otomatik olarak doldurulur.
   
    * **Sürüm** uzantısı karşıya yükleme sayısı.  Bu, source.extension.vsixmanifest dosyasından otomatik olarak doldurulur.
    
    * **VSIX kimliği** Uzantınız için Visual Studio kullanan benzersiz tanımlayıcısıdır.  Otomatik güncelleştirilmiş olması, uzantısına sahip olmasını istiyorsanız bu gereklidir.  Bu, source.extension.vsixmanifest dosyasından otomatik olarak doldurulur.
    
    * **Logo** Uzantınız için kullanılır.  Bu sağladıysanız source.extension.vsixmanifest dosyadan otomatik doldurulmuş olacaktır.
    
    * **Kısa açıklama** uzantınızı yaptığı.  Otomatik olarak doldurulmuş bu source.extension.vsixmanifest dosyasından olacaktır.
    
    * **Genel Bakış** ekran görüntüleri ve uzantınızı yaptığı hakkında ayrıntılı bilgi dahil etmek için uygun bir yerdir.
    
    * **Visual Studio sürümlerinde desteklenen** seçtiğiniz uzantınızı çalışır, Visual Studio'nun hangi sürümleri sağlar.  Uzantınızı yalnızca sürümler yüklenir.
    
    * **Desteklenen Visual Studio sürümleri** seçtiğiniz uzantınızı çalışır hangi Visual Studio sürümleri sağlar.  Uzantınızı yalnızca bu sürümleri yüklenir.
    
    * **Türü**.  Uzantıları en yaygın türü **Araçları**.
    
    * **Kategoriler**.  En çok üç Uzantınız için en uygun olan seçin.
    
    * **Etiketler** olan kullanıcıların Yardım anahtar sözcükleri bul uzantınızı. Etiketler uzantılarınızın Market'te arama alaka artırmaya yardımcı olabilir.
    
    * **Kategori fiyatlandırma** uzantınızı maliyetidir.
    
    * **Kaynak kodu deposu** kaynak kodunuzu bağlantı toplulukla paylaşmanıza olanak tanır.
    
    * **Soru- cevap uzantısı için izin** uzantısı giriş sayfanızda soruları tutulacak kullanıcıların izin verir.

9. Tıklatın **karşıya & Kaydet**. Bu sürecek yayımcınıza geri Yönet sayfası.  Uzantınızı henüz yayınlanmamış.  Uzantı vurgulu uzantınızı girişi yayımlayın ve tıklayın **...**  ve ardından **olun ortak**.  Nasıl uzantınızı Market'te seçerek görüneceğini görüntüleyebilirsiniz **ayrıntıları görüntüleyin**.  Alım numaraları için tıklayın **raporları**.  Dahili değişiklik yapmak için tıklatın **Düzenle*.

  ![Uzantı Giriş menüsü](media/extension-entry-menu.png)

10. ' I tıklattıktan sonra **genel yap**, uzantınızı ortak sunulmuştur.  Visual Studio Market'te Uzantınız için arama yapın.

## <a name="install-the-extension-from-the-visual-studio-marketplace"></a>Visual Studio marketten uzantısını yükleyin

Uzantı yayımlanan, Visual Studio'da yükleyin ve orada sınayın.

1. Visual Studio'da üzerinde **Araçları** menüsünde tıklatın **Uzantılar ve güncelleştirmeler...** .

2. Tıklatın **çevrimiçi** ve TestPublish için arama yapın.

3. **İndir**'e tıklayın. Uzantısı yükleme için zamanlanır.

4. Yüklemeyi tamamlamak için Visual Studio tüm örneklerini kapatın.

## <a name="removing-the-extension"></a>Uzantısını kaldırma

Uzantıyı Visual Studio marketten ve bilgisayarınızdan kaldırabilirsiniz.

### <a name="to-remove-the-extension-from-the-visual-studio-marketplace"></a>Visual Studio marketten uzantıyı kaldırmak için

1. Açık [Visual Studio Market'te](https://marketplace.visualstudio.com/vs) Web sitesi.

2. Sağ üst köşede tıklatın **Yayımla** uzantıları.  TestPublish yayımlamak için kullanılan yayımcı seçin.  TestPublish listesi görüntülenir.

3. Bir uzantı girişini getirin ve tıklayın **...**  ve **Kaldır...** Uzantıyı kaldırmak isteyip istemediğinizi onaylamanız istenir.  **Tamam**'ı tıklatın.

### <a name="to-remove-the-extension-from-your-computer"></a>Uzantıyı bilgisayarınızdan kaldırmak için

1. Visual Studio'da üzerinde **Araçları** menüsünde tıklatın **uzantısı ve güncelleştirmeleri...** .

2. TestPublish seçin ve ardından **kaldırma**. Uzantı sonra kaldırma işlemi için zamanlanacak.

3. Kaldırma işleminin tamamlanması için Visual Studio tüm örneklerini kapatın.
