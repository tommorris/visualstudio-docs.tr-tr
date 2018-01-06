---
title: "Nasıl yapılır: kayıt defteri ayarlarını kullanarak özel galeri yönetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSIX private galleries, managing
- managing VSIX private galleries
ms.assetid: 86b86442-4293-4cad-9fe2-876eef65f426
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 8d88c4b440f61e87792210e8a0844b6b622e8f05
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-manage-a-private-gallery-by-using-registry-settings"></a>Nasıl yapılır: kayıt defteri ayarlarını kullanarak özel galeri yönetme
Bir yönetici veya bir yalıtılmış kabuk uzantısı Geliştirici varsa, denetimleri, şablonlar ve araçlar Visual Studio Galerisi, Örnekler Galerisi veya özel galerileri erişimi denetleyebilirsiniz. Bir galeri kullanılabilir veya kullanılamaz hale getirmek için değiştirilmiş kayıt defteri anahtarları ve değerleri tanımlayan bir .pkgdef dosyasını oluşturun.  
  
## <a name="managing-private-galleries"></a>Özel galerileri yönetme  
 Birden çok bilgisayarda galerileri erişimi denetlemek için bir .pkgdef dosyası oluşturabilirsiniz. Bu dosya, aşağıdaki biçimde olması gerekir.  
  
```  
[$RootKey$\ExtensionManager\Repositories\{UniqueGUID}]  
@={URI}  (REG_SZ)  
Disabled=0 | 1 (DWORD)  
Priority=0 (highest priority) ... MaxInt (lowest priority) (DWORD) (uint)  
Protocol=Atom Feed|Sharepoint (REG_SZ)  
DisplayName={DisplayName} (REG_SZ)  
DisplayNameResourceID={ID} (REG_SZ)  
DisplayNamePackageGuid={GUID} (REG_SZ)  
  
```  
  
 `Repositories` Anahtarı etkin veya devre dışı bırakılacak Galerisine başvuruyor. Visual Studio Galerisi ve Örnekler Galerisi aşağıdaki depoyu GUID'ler kullanın:  
  
-   Visual Studio Galerisi: 0F45E408-7995-4375-9485-86B8DB553DC9  
  
-   Örnekler Galerisi: AEB9CB40-D8E6-4615-B52C-27E307F8506C  
  
 `Disabled` Değer isteğe bağlıdır. Varsayılan olarak, bir galeri etkindir.  
  
 `Priority` Değeri galerileri Seçenekleri iletişim kutusunda listelenen sırasını belirler. Visual Studio Galerisi öncelik 10 ve öncelik 20 Örnekler Galerisi sahiptir. Özel galerileri 100 öncelikli olarak başlatın. Birkaç galerileri aynı öncelik değeri varsa, bunların yerelleştirilmiş değerini göründükleri sırada belirlenir `DisplayName` öznitelikleri.  
  
 `Protocol` Değeri Atom veya SharePoint tabanlı galerileri için gereklidir.  
  
 Ya da `DisplayName`, veya her ikisini de `DisplayNameResourceID` ve `DisplayNamePackageGuid`, belirtilmesi gerekir. Tüm belirtilirse, sonra `DisplayNameResourceID` ve `DisplayNamePackageGuid` çifti kullanılır.  
  
## <a name="disabling-the-visual-studio-gallery-using-a-pkgdef-file"></a>Visual Studio Galerisi .pkgdef dosyasını kullanarak devre dışı bırakma  
 Bir galeri .pkgdef dosyasında devre dışı bırakabilirsiniz. Şu girdiyi Visual Studio Galerisi devre dışı bırakır:  
  
```  
[$RootKey$\ExtensionManager\Repositories\{0F45E408-7995-4375-9485-86B8DB553DC9}]  
"Disabled"=dword:00000001  
  
```  
  
 Şu girdiyi Örnekler Galerisi devre dışı bırakır:  
  
```  
[$RootKey$\ExtensionManager\Repositories\{AEB9CB40-D8E6-4615-B52C-27E307F8506C}]  
"Disabled"=dword:00000001  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Galeriler](../extensibility/private-galleries.md)