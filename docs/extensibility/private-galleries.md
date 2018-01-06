---
title: "Özel galerileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSIX galleries, private
- private galleries, VSIX
ms.assetid: b6b3dee7-91c5-4556-9f69-0d56b675e83b
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 5226ff7a4ed77333d2a6f9287f129c6a6d754cac
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="private-galleries"></a>Özel galerileri
Denetimleri, şablonlar ve bunlara göndererek geliştirme araçları paylaşabilirsiniz bir *özel galeri* aşağıdaki gibi kuruluşunuz için intranet üzerindeki:  
  
-   Bir Atom (düzgün yapılandırılmış merkezi bir konuma (depo) intranetinizdeki RSS akışı) oluşturun. Daha fazla bilgi için bkz: [nasıl yapılır: Özel Galeri için bir Atom akışı oluşturma](../extensibility/how-to-create-an-atom-feed-for-a-private-gallery.md).  
  
-   Özel Galeri tanımlayan bir .pkgdef dosyasını dağıtın. Bu yapılandırma aynı anda çok sayıda bilgisayara özel bir galeri bağlanmak isteyen yöneticiler için öneririz.  
  
## <a name="adding-a-private-gallery-to-extensions-and-updates-in-visual-studio"></a>Uzantılar ve güncelleştirmeler Visual Studio'da Özel Galeri ekleme  
 Özel bir galeri kullanılabilir olduğunda, ona ekleyebilirsiniz **Uzantılar ve güncelleştirmeler** Visual Studio.  
  
 ![Uzantı Yöneticisi ekleme iletişim kutusu](../extensibility/media/em_adddialog.png "EM_AddDialog")  
  
#### <a name="to-add-a-private-gallery-to-extensions-and-updates"></a>Uzantılar ve güncelleştirmeler için özel bir galeri eklemek için  
  
1.  Menü çubuğunda seçin **Araçları**, **seçenekleri**.  
  
2.  İçinde **ortam** düğümü, select **Uzantılar ve güncelleştirmeler**.  
  
3.  Seçin **Ekle** düğmesi.  
  
4.  İçinde **adı** alanında, özel galeri için bir ad girin, örneğin, `My Gallery`.  
  
5.  İçinde **URL** alanı, Atom akışı veya özel galeri barındırma SharePoint sitesinin URL'sini girin.  
  
    1.  Ana bilgisayar Atom akışı ise özel Galerisine bağlanır, URL bu benzeyecektir: http://www.mywebsite/mygallery/atom.xml.  Bu URL, bir dosya veya bir ağ yolu başvurabilir.  
  
    2.  Konak bir SharePoint sitesi ise, URL bu benzeyecektir: http://mysharepoint/sites/mygallery/forms/AllItems.aspx.  
  
### <a name="managing-private-galleries"></a>Özel galerileri yönetme  
 Bir yönetici özel bir galeri kullanılabilir birkaç bilgisayar için aynı anda her bilgisayarda Sistem kayıt defterini değiştirerek yapabilirsiniz. Bunu gerçekleştirmek için yeni kayıt defteri anahtarları ve değerleri tanımlayan bir .pkgdef dosyası oluşturun.  Bu dosya biçimi aşağıdaki gibidir.  
  
```  
[$RootKey$\ExtensionManager\Repositories\{UniqueGUID}]  
@={URI}  (REG_SZ)  
Disabled=0 | 1 (DWORD)  
Priority=0 (highest priority) ... MaxInt (lowest priority) (DWORD) (uint)  
Protocol=Atom|Sharepoint (REG_SZ)  
DisplayName={DisplayName} (REG_SZ)  
DisplayNameResourceID={ID} (REG_SZ)  
DisplayNamePackageGuid={GUID} (REG_SZ)  
  
```  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: bir özel Galerisi tarafından kayıt defteri ayarlarını kullanarak yönetmek](../extensibility/how-to-manage-a-private-gallery-by-using-registry-settings.md).  
  
## <a name="installing-extensions-from-a-private-gallery"></a>Bir özel galerisinden uzantıları yükleme  
 Arama ve özel bir galeride Visual Studio uzantılarını yüklemenize **Uzantılar ve güncelleştirmeler**. Adlı özel bir galeri aşağıdaki adımları kullanın `My Gallery`.  
  
 ![Uzantı Özel Galeri yükleme yöneticisi](../extensibility/media/em_.png "EM_")  
  
#### <a name="to-search-for-and-install-extensions-from-a-private-gallery"></a>Aramak ve özel galerisinden uzantıları yüklemek için  
  
1.  Menü çubuğunda seçin **Araçları**, **Uzantılar ve güncelleştirmeler**.  
  
2.  Sol bölmede seçin **çevrimiçi uzantıları**ve ardından **My galeri**.  
  
3.  Sağ bölmede, bir uzantı seçin ve ardından **karşıdan** düğmesi.  
  
## <a name="updating-extensions-from-a-private-gallery"></a>Özel Galeri uzantılardan güncelleştiriliyor  
 Visual Studio Uzantıları'nın yeni sürümleri Özel Galeri gönderilen gibi yüklediğiniz uzantıları güncelleştirebilirsiniz. Adlı özel bir galeri aşağıdaki adımları kullanın `My Repository`.  
  
 ![Uzantı Yöneticisi Özel Galeri güncelleştirme](../extensibility/media/em_update.png "EM_Update")  
  
#### <a name="to-update-an-installed-extension-from-a-private-gallery"></a>Özel galerisinden yüklenmiş bir uzantı güncelleştirmek için  
  
1.  Menü çubuğunda seçin **Araçları**, **Uzantılar ve güncelleştirmeler**.  
  
2.  Sol bölmede seçin **güncelleştirmeleri**ve ardından **My deposu**.  
  
3.  Sağ bölmede, bir uzantı seçin ve ardından **güncelleştirme** düğmesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bulma ve Visual Studio uzantıları kullanma](../ide/finding-and-using-visual-studio-extensions.md)   
 [Visual Studio Uzantıları Gönderme](../extensibility/shipping-visual-studio-extensions.md)