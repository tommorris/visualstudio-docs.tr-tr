---
title: 'Nasıl yapılır: yayımlama sihirbazını kullanarak ClickOnce uygulaması yayımlama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, publishing
- deploying applications [ClickOnce], Publish wizard
- Windows applications, ClickOnce deployments
- publishing, ClickOnce
ms.assetid: 2e4aa67c-4445-4f7b-9e03-9acb95829127
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 762ef9813232b282b4f140e9c01e8d722a42bf3d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-publish-a-clickonce-application-using-the-publish-wizard"></a>Nasıl yapılır: Yayımlama Sihirbazını Kullanarak ClickOnce Uygulaması Yayımlama
ClickOnce uygulaması kullanıcılar tarafından kullanılabilmesi için bir dosya paylaşımı veya yolu, FTP sunucusu veya çıkarılabilir medya yayımlamanız gerekir. Uygulama Yayımlama Sihirbazı'nı kullanarak yayımlayabilirsiniz; yayımlama ile ilgili ek özellikler bulunur **Yayımla** sayfasında **Proje Tasarımcısı**. Daha fazla bilgi için bkz: [ClickOnce uygulamalarını yayımlama](../deployment/publishing-clickonce-applications.md).  
  
 Yayımlama Sihirbazı'nı çalıştırmadan önce yayımlama özellikleri uygun şekilde ayarlamanız gerekir. ClickOnce uygulamanızı imzalamak için bir anahtar belirlemek istiyorsanız, örneğin, vb. yapabileceğiniz **imzalama** sayfasında **Proje Tasarımcısı**. Daha fazla bilgi için bkz: [ClickOnce uygulamalarının güvenliğini sağlama](../deployment/securing-clickonce-applications.md).  
  
> [!NOTE]
>  ClickOnce kullanarak bir uygulama birden fazla sürümünü yüklediğinizde, yükleme uygulamanın önceki sürümleri arşivindeki belirttiğiniz yayımlama konumu adlı bir klasöre taşır. Bu şekilde tutar önceki sürümlerde yükleme dizinini temizleyin önceki sürümünden klasörlerinin arşivleme.  
  
> [!NOTE]
>  İletişim kutuları ve menü komutlarını gördüğünüz açıklanana Yardım'da etkin ayarlarınıza veya sürümünüze bağlı olarak farklı olabilir. Ayarlarınızı değiştirmek için tıklatın. **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
### <a name="to-publish-to-a-file-share-or-path"></a>Bir dosya paylaşımı veya yol yayımlamak için  
  
1.  İçinde **Çözüm Gezgini**, uygulama projesini seçin.  
  
2.  Üzerinde **yapı** menüsünde tıklatın **Yayımla**`Projectname`.  
  
     Yayımlama Sihirbazı görünür.  
  
3.  İçinde **burada uygulamayı yayımlamak istiyorsunuz?** sayfasında, geçerli bir FTP sunucusu adresi veya gösterilen biçimlerden birini kullanarak geçerli bir dosya yolu girin ve ardından **sonraki**.  
  
4.  İçinde **nasıl kullanıcılar yükler uygulama?** sayfasında, kullanıcıların gittikleri uygulamayı yüklemek için konumu seçin:  
  
    -   Kullanıcılar bir Web sitesinden kuracaksa tıklatın **bir Web sitesinden** ve karşılık gelen bir URL önceki adımda girilen dosya yolunu girin. **İleri**'ye tıklayın. (Yayımlama konumu olarak bir FTP adresi belirttiğinizde, bu seçenek genellikle kullanılır. FTP doğrudan Merkezi'nden desteklenmiyor. Bu nedenle, bir URL girmeniz gerekir.)  
  
    -   Kullanıcılar uygulamayı doğrudan dosya paylaşımından kuracaksa tıklatın **gelen bir UNC yolu veya dosya paylaşımı**ve ardından **sonraki**. (Form c:\deploy\myapp konumlarını yayımlamak için budur veya \\\server\myapp.)  
  
    -   Kullanıcılar çıkarılabilir medyadan yükleme yaparsa tıklatın **gelen bir CD-ROM veya DVD-ROM'UNDAN**ve ardından **sonraki**.  
  
5.  Üzerinde **uygulama çevrimdışı kullanılabilir olacak?** sayfasında, uygun seçeneği tıklatın:  
  
    -   Uygulamanın çalıştırılması etkinleştirmek istiyorsanız, kullanıcı kapatılacağı zaman ağdan, tıklatın **Evet, bu uygulama çevrimiçi veya çevrimdışı kullanılabilir olacak**. Bir kısayolu **Başlat** menü uygulama için oluşturulur.  
  
    -   Uygulamayı doğrudan Yayımla konumundan çalıştırmak istiyorsanız, tıklayın **Hayır, bu uygulama yalnızca çevrimiçi kullanılabilir**. Bir kısayolu **Başlat** menü oluşturulmaz.  
  
     Devam etmek için **İleri** 'ye tıklayın.  
  
6.  Tıklatın **son** uygulamayı yayımlamak için.  
  
     Yayımlama Durumu durum bildirim alanında görüntülenir.  
  
### <a name="to-publish-to-a-cd-rom-or-dvd-rom"></a>Bir CD-ROM veya DVD-ROM'UNDAN yayımlamak için  
  
1.  İçinde **Çözüm Gezgini**, uygulama projesine sağ tıklatın ve **özellikleri**.  
  
     **Proje Tasarımcısı** görüntülenir.  
  
2.  Tıklatın **Yayımla** sekmesini açmak için **Yayımla** sayfasındaki **Proje Tasarımcısı**, tıklatıp **Yayımlama Sihirbazı** düğmesi.  
  
     Yayımlama Sihirbazı görünür.  
  
3.  İçinde **burada uygulamayı yayımlamak istiyorsunuz?** sayfasında, dosya yolu veya burada uygulama yayımlanacak, FTP konumu d:\deploy girin. Ardından **sonraki** devam etmek için.  
  
4.  Üzerinde **nasıl kullanıcılar yükler uygulama?** sayfasında, gelen bir **CD-ROM veya DVD-ROM'UNDAN**ve ardından **sonraki**.  
  
    > [!NOTE]
    >  Yüklemenin otomatik olarak çalışmasını istiyorsanız, CD-ROM'dan eklenir sürücüsüne açık **Yayımla** sayfasındaki **Proje Tasarımcısı** tıklatıp **seçenekleri** düğmesini ve ardından **Yayımla Seçenekleri** seçin **için CD yüklemeleri CD eklendiğinde, Kurulum otomatik olarak Başlat**.  
  
5.  Uygulamanızı CD-ROM üzerinde dağıtırsanız, bir Web sitesinden güncelleştirmeleri sağlamak isteyebilirsiniz. İçinde **burada uygulama güncelleştirmelerini denetleme?** sayfasında, bir güncelleştirme seçeneğini seçin:  
  
    -   Uygulama güncelleştirmeleri denetler tıklatmak **uygulama güncelleştirmeleri aşağıdaki konumdan kontrol eder** ve burada güncelleştirmeleri gönderilecektir konumu girin. Bu, bir dosya konumu, Web sitesi veya FTP sunucusu olabilir.  
  
    -   Uygulama güncelleştirmeleri denetlemez tıklatmak **uygulama güncelleştirmeleri denetlemez**.  
  
     Devam etmek için **İleri** 'ye tıklayın.  
  
6.  Tıklatın **son** uygulamayı yayımlamak için.  
  
     Yayımlama Durumu durum bildirim alanında görüntülenir.  
  
    > [!NOTE]
    >  Yayımlama tamamlandıktan sonra CD-yeniden yazan kullanması gerekir veya DVD-belirtilen konumdan dosyaları kopyalamak için adım 3 ' CD-ROM veya DVD-ROM'UNDAN medyaya.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce güvenliği ve dağıtımı](../deployment/clickonce-security-and-deployment.md)   
 [ClickOnce uygulamalarının güvenliğini sağlama](../deployment/securing-clickonce-applications.md)   
 [ClickOnce Kullanarak Office Çözümü Dağıtma](/office-dev/office-dev/deploying-an-office-solution-by-using-clickonce)