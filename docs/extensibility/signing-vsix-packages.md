---
title: VSIX paket imzalama | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- signature
- signing
- authenticode
- vsix
- packages
ms.assetid: e34cfc2c-361c-44f8-9cfe-9f2be229d248
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d5a27b4e76e0cd8f986441778ed39c7fbb5a2211
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="signing-vsix-packages"></a>VSIX paket imzalama
Uzantı derlemeleri Visual Studio'da çalıştırabilirsiniz ancak bunu yapmak için iyi bir uygulama olmasından önce oturum açmanız gerekmez.  
  
 Uzantınızı güvenli ve ile değiştirilmediğinden emin olmak istiyorsanız, bir dijital imza VSIX paket ekleyebilirsiniz. Bir VSIX imzalandığında VSIX yükleyici, imza hakkında daha fazla bilgi artı imzalanmasını belirten bir ileti görüntüler. VSIX içeriğini değiştirilmiş ve VSIX yeniden imzalı değil, VSIX yükleyici imzası geçerli değil gösterir. Yükleme durdurulmadı, ancak kullanıcı uyarılır.  
  
> [!IMPORTANT]
>  2015'te başlayarak, SHA256 şifreleme dışında her şey ile imzalanmış VSIX paket geçersiz bir imza sahibi olarak tanımlanır. VSIX yükleme engellenmez ancak kullanıcı uyarı alırsınız.  
  
## <a name="signing-a-vsix-with-vsixsigntool"></a>VSIX VSIXSignTool ile imzalama  
 İmzalama aracı kullanılabilir SHA256 şifreleme yok [VisualStudioExtensibility](http://www.nuget.org/profiles/VisualStudioExtensibility) nuget.org üzerinde [VsixSignTool](http://www.nuget.org/packages/Microsoft.VSSDK.Vsixsigntool).  
  
#### <a name="to-use-the-vsixsigntool"></a>VSIXSignTool kullanmak için  
  
1.  VSIX bir projeye ekleyin.  
  
2.  Çözüm Gezgini'nde, proje düğümüne sağ tıklayın seçerek **Ekle &#124; NuGet paketlerini Yönet**.  NuGet ve NuGet paketleri bakın ekleme hakkında daha fazla bilgi için bkz: [NuGet belgelerine](http://docs.microsoft.com/NuGet) ve [Paket Yöneticisi kullanıcı Arabirimi](http://docs.microsoft.com/NuGet/Tools/Package-Manager-UI) Konular.  
  
3.  VisualStudioExtensibility gelen VSIXSignTool arayın ve NuGet paketini yükleyin.  
  
4.  Bu gibi durumlarda, VSIXSignTool şimdi projenin yerel paketler konumdan çalıştırabilirsiniz. İmzalama senaryonuz için aracın komut satırı Yardımı'na başvurun (VSIXSignTool.exe /?).  
  
 Örneğin bir parola korumalı sertifika dosyası ile imzalamak için:  
  
 VSIXSignTool.exe oturum /f \<SertifikaDosyası > /p \<parola > \<VSIXfile >  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio uzantıları aktarma](../extensibility/shipping-visual-studio-extensions.md)