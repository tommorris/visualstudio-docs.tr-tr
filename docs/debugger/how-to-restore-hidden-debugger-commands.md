---
title: 'Nasıl yapılır: gizli hata ayıklayıcı komutlarını geri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugger, restoring commands
- debugging [Visual Studio], restoring commands
- commands, debugger
ms.assetid: 76ac9b77-f536-43b5-a9fc-984854b1c566
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f47f8cbb342f480e6124f765b3b427a615ec6a38
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-restore-hidden-debugger-commands"></a>Nasıl Yapılır: Gizli Hata Ayıklayıcı Komutlarını Geri Yükleme
Visual Studio'yu kurarken IDE ayarları birincil programlama diliniz için varsayılan bir dizi seçin istenir. Bazı diller için varsayılan IDE ayarları belirli hata ayıklayıcı komutlarını gizlemek.  
  
 Varsayılan IDE ayarlarınız tarafından gizli hata ayıklayıcı özelliğini kullanmak istiyorsanız, aşağıdaki yordamı kullanarak menüsüne geri komutu ekleyebilirsiniz.  
  
### <a name="to-restore-hidden-debugger-commands"></a>Gizli hata ayıklayıcı komutlarını geri yüklemek için  
  
1.  Açık bir proje ile **Araçları** menüsünde tıklatın **Özelleştir**.  
  
2.  İçinde **Özelleştir** iletişim kutusu, tıklatın **komutları** sekmesi.  
  
3.  İçinde **menü çubuğu:** açılan listesinde, select **hata ayıklama** , geri yüklenen komutu içermesi istediğiniz menüsü.  
  
4.  Tıklatın **komut Ekle...**  düğmesi.  
  
5.  İçinde **Add komutunu** kutusunda, istediğiniz eklenecek ve tıklatın komutu seçin **Tamam**.  
  
6.  Başka bir komut eklemek için önceki adımı yineleyin.  
  
7.  Tıklatın **Kapat** menüye komut ekleme tamamladığınızda.  
  
    > [!WARNING]
    >  Hata ayıklayıcı çalışma modunda veya kesme modu gibi belirli modda olduğunda bazı menü öğeleri yalnızca görünür. Bu nedenle, bu adımları tamamladıktan sonra eklenen bir öğeyi hemen görünür olmayabilir.  
  
## <a name="restoring-commands-not-available-from-the-customize-dialog-box"></a>Özelleştir iletişim kutusu kullanılamaz geri yükleme komutları  
 Bazı komutlar, özellikle hiyerarşik menülerde bulunanlar geri yüklenemez **Özelleştir** iletişim kutusu. Bu komutlar geri yüklemek için yeni bir koleksiyon IDE ayarları içeri aktarmanız gerekir.  
  
#### <a name="to-import-new-ide-settings"></a>Yeni IDE ayarları içeri aktarmak için  
  
1.  Üzerinde **Araçları** menüsünde tıklatın **içeri ve dışarı aktarma ayarları**.  
  
2.  Üzerinde **içeri aktarma ve dışarı aktarım ayarları Sihirbazı Hoş Geldiniz** sayfasında, **seçili ortam ayarları**ve ardından **sonraki**.  
  
3.  Üzerinde **geçerli ayarları Kaydet** sayfasında, varolan ayarlarınızı kaydedin ve ardından gerekip gerekmediğini karar **sonraki**.  
  
4.  Üzerinde **almak için ayarlar koleksiyonu seçin** sayfasında **varsayılan ayarları** klasörü, kullanmak istediğiniz komutları sahip geliştirme ayarlar koleksiyonu seçin. Hangi koleksiyonu seçmek için bilmiyorsanız deneyin **genel geliştirme ayarları** veya **Visual C++ geliştirme ayarları**, en fazla hata ayıklayıcı komutlarını sağlar.  
  
5.  **İleri**'ye tıklayın.  
  
6.  Üzerinde **almak için ayarları seçin** sayfasında **seçenekleri**, emin olun **hata ayıklama** seçilir. Bu ayarları da içeri aktarmak istediğiniz sürece diğer onay kutularını temizleyin.  
  
7.  **Son**'a tıklayın.  
  
8.  Üzerinde **alma tam** sayfasında, ayarlarınızı altında sıfırlama ile ilişkili hataları gözden geçirin **ayrıntıları**.  
  
9. **Kapat**'ı tıklatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama güvenliği](../debugger/debugger-security.md)   
 [Hata ayıklayıcı temel bilgileri](../debugger/debugger-basics.md)