---
title: "İzlenecek yol: bir özel düzenleyici oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], custom - create
ms.assetid: d090abb6-d99f-4083-a3db-cd16bf81ce7d
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 74408fd88a594503c2a585cd0edfa86f28ed596e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-creating-a-custom-editor"></a>İzlenecek yol: bir özel düzenleyici oluşturma
VSPackage proje şablonu basit bir özel düzenleyici C++'da oluşturabilirsiniz.  VSPackage proje şablonu artık C# veya Visual Basic projeleri destekler. Daha fazla bilgi için bkz: [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuzda izlemek için Visual Studio SDK'yı yüklemeniz gerekir. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="the-visual-studio-package-project-template"></a>Visual Studio Paketi proje şablonu  
 Visual Studio Paketi proje şablonu bulunabilir **yeni proje** C++ genişletilebilirlik klasöründeki iletişim  
  
### <a name="to-create-a-vspackage-using-the-visual-studio-package-template"></a>Visual Studio Paketi şablonu kullanarak bir VSPackage oluşturmak için  
  
1.  Bir proje ile Visual Studio Paketi şablonu oluşturun.  
  
2.  Seçin **özel düzenleyici** seçeneğini ve tıklayın **sonraki**. **Düzenleyici Seçenekleri** sayfası görüntülenir.  
  
3.  Düzenleyicinizde adını yazın **Düzenleyici adı** kutusu. Düzenleyicinizde ile ilişkili olmasını istediğiniz dosya uzantısını yazın **dosya uzantısı** kutusu. Düzenleyicinizi bu uzantılı dosyalar kullanılabilir. Dosya uzantısı için Visual Studio yalnızca, Windows için kayıtlı değil. Düzenleyicinizde ile oluşturulan yeni belgeler için varsayılan dosya adı yazın **varsayılan dosya adı** kutusu.  
  
4.  Tıklatın **son** , VSPackage belirttiğiniz klasörde oluşturun.  
  
### <a name="to-test-your-custom-editor"></a>Özel düzenleyici sınamak için  
  
1.  Üzerinde **dosya** menüsündeki **yeni** ve ardından **dosya**.  
  
2.  İçinde **yüklü şablonlar** bölmesinde **yeni dosya** dosya şablonu sonra dosya türünü yalnızca kayıtlı iletişim kutusunda, seçin.  
  
3.  Tıklatın **açık** görüntülemek ve belgeyi düzenlemek için.  
  
     Düzenleyici kesme ve yapıştırma, bulma ve değiştirme ve açık ve yükleme işlemlerini destekler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPackages](../extensibility/internals/vspackages.md)