---
title: Uzantıları Windows Installer dağıtımı için hazırlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- vsix msi
ms.assetid: 5ee2d1ba-478a-4cb7-898f-c3b4b2ee834e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ef51b3cb0f84a470f104ff688c1149e607d16f71
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="preparing-extensions-for-windows-installer-deployment"></a>Uzantıları Windows Installer dağıtımı için hazırlama
VSIX paketi dağıtmak için Windows Installer paketi (MSI) kullanamazsınız. Ancak, MSI dağıtımı için VSIX paket içeriğini ayıklayabilirsiniz. Bu belge, varsayılan çıktısı bir kurulum projesi eklenmesi için VSIX paket olduğu projesinde hazırlamak gösterilmiştir.  
  
## <a name="preparing-an-extension-project-for-windows-installer-deployment"></a>Uzantı projesi Windows Installer dağıtımı için hazırlama  
 Kurulum projesine eklemeden önce yeni uzantı projelerde aşağıdaki adımları gerçekleştirin.  
  
#### <a name="to-prepare-an-extension-project-for-windows-installer-deployment"></a>Windows Installer dağıtımı için bir uzantı projesi hazırlamak için  
  
1.  Bir VSPackage, MEF Bileşeni, Düzenleyicisi Adornment veya VSIX bildirim içeren başka bir genişletilebilirlik proje türü oluşturun.  
  
2.  VSIX bildirimini Kod düzenleyicisinde açın.  
  
3.  VSIX bildiriminin InstalledByMsi öğesini ayarlamak `true`. VSIX bildirimi hakkında daha fazla bilgi için bkz: [VSIX uzantı şema 2.0 başvurusu](../extensibility/vsix-extension-schema-2-0-reference.md).  
  
     Bu, VSIX Yükleyici'nin bileşeni yüklemek denemelerini engeller.  
  
4.  ' Nde projeye sağ **Çözüm Gezgini** tıklatıp **özellikleri**.  
  
5.  Seçin **VSIX** sekmesi.  
  
6.  Etiketli kutuyu **aşağıdaki konuma kopyalama VSIX içerik** ve Kurulum projesi dosyaları nerede çeker yolunu yazın.  
  
## <a name="extracting-files-from-an-existing-vsix-package"></a>Var olan bir VSIX paketinden dosyalar ayıklanıyor  
 Kaynak dosyaları olmadığında varolan VSIX paketi içeriğini Kurulum projesine eklemek için aşağıdaki adımları gerçekleştirin.  
  
#### <a name="to-extract-files-from-an-existing-vsix-package"></a>Var olan bir VSIX paketinden dosyaları ayıklayın  
  
1.  Yeniden adlandırın. Uzantı içeren VSIX dosyası *filename*.vsix *filename*.zip.  
  
2.  .Zip dosyasının içeriğini bir dizine kopyalayın.  
  
3.  [Content_types] .xml dosyasını dizinden silin.  
  
4.  VSIX bildirimini önceki yordamda gösterildiği gibi düzenleyin.  
  
5.  Kalan dosyaları kurulum projenize ekleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Installer dağıtımı](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0)   
 [İzlenecek yol: özel bir eylem oluşturma](http://msdn.microsoft.com/en-us/4bd4b63a-2b91-431e-839c-5752443f0eaf)