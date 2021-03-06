---
title: VSIX paketlerini imzalama | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- signature
- signing
- authenticode
- vsix
- packages
ms.assetid: e34cfc2c-361c-44f8-9cfe-9f2be229d248
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f25ce39fe1c96d0e45b89fdd6114ce6984be2d16
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632975"
---
# <a name="signing-vsix-packages"></a>VSIX Paketlerini İmzalama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [VSIX paketlerini imzalama](https://docs.microsoft.com/visualstudio/extensibility/signing-vsix-packages).  
  
Uzantı derlemelerini Visual Studio'da çalışabilirler, ancak bunu yapmak için iyi bir uygulamadır önce oturum açmanız gerekmez.  
  
 Uzantınızı güvenli ve ile değiştirilmediğinden emin olmak istiyorsanız, VSIX paketine bir dijital imza ekleyebilirsiniz. Bir VSIX imzalandığında VSIX yükleyici, imza hakkında daha fazla bilgi artı imzalanmış olduğunu belirten bir ileti görüntülenir. VSIX içeriğini değiştirilmiş ve VSIX yeniden imzalı değil, VSIX yükleyici imzası geçerli değil gösterilir. Yükleme durdurulmadı, ancak kullanıcı uyarılır.  
  
> [!IMPORTANT]
>  İçinde bir 2015'ten itibaren VSIX paketlerini SHA256 şifreleme dışında herhangi bir şey ile imzalanmış geçersiz imzaya sahip olunması olarak tanımlanır. VSIX yüklemesi engellenmez, ancak kullanıcı uyarılır.  
  
## <a name="signing-a-vsix-with-vsixsigntool"></a>Bir VSIX VSIXSignTool ile imzalama  
 İmzalama aracı bulunan bir SHA256 şifreleme yok [VisualStudioExtensibility](http://www.nuget.org/profiles/VisualStudioExtensibility) nuget.org [VsixSignTool](http://www.nuget.org/packages/Microsoft.VSSDK.Vsixsigntool).  
  
#### <a name="to-use-the-vsixsigntool"></a>VSIXSignTool kullanmak için  
  
1.  Kendi VSIX bir projeye ekleyin.  
  
2.  Çözüm Gezgini'nde proje düğümüne sağ tıklayın seçerek **Ekle &#124; NuGet paketlerini Yönet**.  NuGet ve NuGet ekleme hakkında daha fazla bilgi için bkz: paketleri [NuGet genel bakış](http://docs.nuget.org/) ve [yönetme NuGet paketlerini kullanarak iletişim](http://docs.nuget.org/Consume/Package-Manager-Dialog).  
  
3.  VSIXSignTool VisualStudioExtensibility gelen arayın ve NuGet paketini yükleyin.  
  
4.  Şimdi, VSIXSignTool projenin yerel paketleri konumundan çalıştırabilirsiniz. İmzalama senaryonuz için Aracı'nın komut satırı yardımına bakın (VSIXSignTool.exe /?).  
  
 Örneğin: bir parola korumalı bir sertifika dosyası ile imzala  
  
 VSIXSignTool.exe oturum /f \<certfile > /p \<parola > \<VSIXfile >  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Uzantıları Gönderme](../extensibility/shipping-visual-studio-extensions.md)

