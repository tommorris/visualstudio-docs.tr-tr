---
title: "Yayımla Sayfası, Proje Tasarımcısı (Visual Studio'da Office Geliştirme) | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VST.ProjectProperties.Publish.2007System
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- deploying applications [Office development in Visual Studio]
- publishing, Office solutions
- Property Pages dialog box, Publish [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: d9cc3fa102c0552893c6f7859a256b7df26e3af5
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="publish-page-project-designer-office-development-in-visual-studio"></a>Yayımlama Sayfası, Proje Tasarımcısı (Visual Studio'da Office Geliştirme)
  **Yayımla** sayfasında **Proje Tasarımcısı** dağıtım özelliklerini yapılandırmak için kullanılır.  
  
 Bu sayfaya erişmek için projede seçin **Çözüm Gezgini**ve ardından **proje** menüsünde seçin *Projectname* **özellikleri** . Varsa **Yayımla** sayfası görüntülenmez, seçin **Yayımla** sekmesi.  
  
> [!NOTE]  
>  De yayımlama konumu ayarlayabilirsiniz **Yayımlama Sihirbazı**. Daha fazla bilgi için bkz: [nasıl yapılır: Office çözümünü kullanarak ClickOnce tarafından yayımlama](http://msdn.microsoft.com/en-us/2b6c247e-bc04-4ce4-bb64-c4e79bb3d5b8).  
  
## <a name="uielement-list"></a>UIElement Listesi  
 **Yayımlama klasörü konumu (web sitesi, ftp sunucusu veya dosya yolu)**  
 Gerekli.  
  
 Yayımlama klasörü konumu için ve Visual Studio bildirimleri, derlemeler ve diğer dosyaları gibi çözüm dosyaları derlemeden kopyalar dizindir. Bu dizine yazma erişimi olmalıdır.  
  
 Yerel bilgisayar, bir UNC dosya paylaşımı veya bir HTTP/HTTPS web sitesi seçenekleri içerir. Yol yerel olabilir (*c:\foldername\publishfolder*), göreli (*yayımlama\\*), ya da tam bir konum (*\\\servername\foldername* veya http://*SunucuAdı/KlasörAdı*).  
  
 Varsayılan olarak, yayımlama konumdur *http://localhost/projectname/* IIS yüklü veya bunu yaparsanız publish\ dizin IIS yüklü.  
  
 **Yükleme klasörü URL'si**  
 İsteğe bağlı.  
  
 Yükleme klasörü URL'i son kullanıcının ondan özelleştirmeyi yüklediği dizindir. Bu da çözümü güncelleştirmeleri denetlemek için kullanacağı yoludur. Yol yayımlama klasörü konumu ile aynı olabilir, ancak bu zorunlu değildir.  
  
 Yerel bilgisayar, bir UNC dosya paylaşımı veya bir HTTP/HTTPS web sitesi seçenekleri içerir. Yol yerel olabilir (*c:\foldername\publishfolder*), göreli (*yayımlama\\*), ya da tam bir konum (*\\\servername\foldername* veya http://*SunucuAdı/KlasörAdı*). Tüm HTTP/HTTPS konumları US-ASCII karakter ile oluşturulması gerekir. Unicode karakterler desteklenmez.  
  
 Yükleme yolu ayarlarsanız, özelleştirme dosyaları özelleştirme kullanıcılar o konumda olması gerekir. Yalnızca son dağıtım konumunu biliyorsanız konumu ayarlamanız gerekir.  
  
 Yükleme dosyalarını belge ya da kurulum programı, göreli bir konumda gibi CD seçeneğiyle varsa bu kutuyu boş bırakın.  
  
 Bu değer daha sonra bir yönetici tarafından atanabilir. Daha fazla bilgi için bkz: [nasıl yapılır: Office çözümü yükleme konumunu değiştirmek](http://msdn.microsoft.com/en-us/d0eaa07b-2d72-4902-899f-2f9fb165b8fd).  
  
 **Önkoşullar**  
 Önkoşulları Kurulum programına dahil veya isteğe bağlı yükleme sırasında indirilir.  
  
-   **Bileşen satıcısının web sitesinden önkoşulları**: Bu önkoşulları Microsoft'tan indirmek için bu seçeneği kullanın.  
  
-   **Aynı konumda Uygulamamla önkoşulları indirmesi**: Yükleyicinizle Önkoşullar paketlemek için bu seçeneği kullanın. Kurulum programı önkoşul dosyalarıyla dahil olmak üzere, çözüm boyutu artar.  
  
-   **Aşağıdaki konumdan önkoşulları indir**: önkoşulları son kullanıcılara ayrı ayrı bir web sayfası veya ağ paylaşımında başka bir Kurulum programı olarak kullanılabilmesi için bu seçeneği kullanın.  
  
 **Güncelleştirmeler**  
 Çözüm güncelleştirmeleri ne sıklıkta denetleyeceğini güncelleştirme aralığını belirler. Her yedi günde denetlemek için varsayılandır.  
  
 Belge düzeyi özelleştirme veya VSTO eklenti her yüklenişinde güncelleştirmeleri denetleniyor güncel tutun, ancak başlangıç performansını etkileyecektir.  
  
 Bir CD ya da çıkarılabilir sürücü kullanarak dağıtıyorsanız, bu ayar **hiçbir zaman güncelleştirmeleri denetlemek için**.  
  
 **Seçenekler (Açıklama)**  
 Aşağıdaki özellikler için yayımlama seçeneklerini ayarlayabilirsiniz:  
  
-   Yayımlama dili: Office çözümü yerel.  
  
-   Yayımcı adı: Şirket veya Geliştirici adıyla görünür **Program Ekle/Kaldır** veya **programlar ve Özellikler**.  
  
-   Ürün adı: göründüğü şekliyle Office çözümü adı **Program Ekle/Kaldır** veya **programlar ve Özellikler**.  
  
-   Destek URL'si: konumun son kullanıcıların Office çözümü için teknik destek birimine başvurun.  
  
 **Seçenekler (Office ayarları)**  
 Aşağıdaki özellikler için yayımlama seçeneklerini ayarlayabilirsiniz:  
  
-   Çözüm adı: Office uygulamasında göründüğü şekliyle Office çözümü adı.  
  
-   Açıklama: Office çözümü olarak açıklaması Office uygulamasında görüntülenir.  
  
-   VSTO eklenti yükleme davranışı.  
  
    -   Başlangıçta yüklenen: Office uygulaması başlatıldığında VSTO eklenti yükleneceğini belirtir.  
  
    -   İsteğe bağlı yükleme: uygulama, bir kullanıcı VSTO eklenti işlevselliği kullanan bir kullanıcı Arabirimi öğesi tıkladığında gibi gerektirdiğinde VSTO eklenti yükleneceğini belirtir.  
  
 **Yayımlama dili**  
 Bu seçenek, Microsoft Yazılımı Lisans koşulları dili ayarlar ve önkoşullar listesinde dil paketlerini içerir. Özelleştirmenin dilini etkilemez. Kurulum programı dilde Visual Studio yüklü dilleri tarafından belirlenir.  
  
 Nasıl değiştirileceği hakkında daha fazla bilgi için **yayımlama dili**, bkz: [nasıl yapılır: ClickOnce uygulaması için yayımlama dilini değiştirme](/visualstudio/deployment/how-to-change-the-publish-language-for-a-clickonce-application).  
  
 **Sürüm yayımlayın.**  
 Özelleştirme için sürüm numarasını ayarlar. Sürüm numarasını değiştirildiğinde, uygulama bir güncelleştirme olarak yayımlanır. Yeni bir klasör her sürüm için önceden yayımlanan sürümü üzerine yazılmasını engellemek için oluşturma işlemi sırasında oluşturulur. Her bir parçasını Yayımla sürümü (**ana**, **küçük**, **yapı**, **düzeltme**) en fazla beş rakam içerebilir.  
  
 **Her sürüm düzeltmelerle otomatik olarak Artır**  
 İsteğe bağlı. (Varsayılan), seçili olduğunda **düzeltme** sürüm numarasını parçası artırılır tarafından özelleştirme yayımlanan her zaman. Bu, bir güncelleştirme yayımlanmasına özelleştirme neden olur.  
  
 **Şimdi Yayımla**  
 Geçerli ayarları kullanarak uygulamayı yayımlar. Eşdeğer **son** düğmesini **Yayımlama Sihirbazı**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md)   
 [ClickOnce kullanarak Office çözümü dağıtma](../vsto/deploying-an-office-solution-by-using-clickonce.md)   
 [Dağıtım için Office çözümleri önkoşulları](http://msdn.microsoft.com/en-us/9f672809-43a3-40a1-9057-397ce3b5126e)  
  
  