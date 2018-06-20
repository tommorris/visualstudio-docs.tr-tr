---
title: VSIX paket imzalama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- signature
- signing
- authenticode
- vsix
- packages
ms.assetid: e34cfc2c-361c-44f8-9cfe-9f2be229d248
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1179f1fa6b642f7f2523699332ec64ccc13e4b8f
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36233561"
---
# <a name="signing-vsix-packages"></a>VSIX Paketlerini İmzalama
Uzantı derlemeleri Visual Studio'da çalıştırabilirsiniz ancak bunu yapmak için iyi bir uygulama olmasından önce oturum açmanız gerekmez.  
  
 Uzantınızı güvenli ve ile değiştirilmediğinden emin olmak istiyorsanız, bir dijital imza VSIX paket ekleyebilirsiniz. Bir VSIX imzalandığında VSIX yükleyici, imza hakkında daha fazla bilgi artı imzalanmasını belirten bir ileti görüntüler. VSIX içeriğini değiştirilmiş ve VSIX yeniden imzalı değil, VSIX yükleyici imzası geçerli değil gösterir. Yükleme durdurulmadı, ancak kullanıcı uyarılır.  
  
> [!IMPORTANT]
>  2015'te başlayarak, SHA256 şifreleme dışında her şey ile imzalanmış VSIX paket geçersiz bir imza sahibi olarak tanımlanır. VSIX yükleme engellenmez ancak kullanıcı uyarı alırsınız.  
  
## <a name="signing-a-vsix-with-vsixsigntool"></a>VSIX VSIXSignTool ile imzalama  
 İmzalama aracı kullanılabilir SHA256 şifreleme yok [VisualStudioExtensibility](http://www.nuget.org/profiles/VisualStudioExtensibility) nuget.org üzerinde [VsixSignTool](http://www.nuget.org/packages/Microsoft.VSSDK.Vsixsigntool).  
  
#### <a name="to-use-the-vsixsigntool"></a>VSIXSignTool kullanmak için  
  
1.  VSIX bir projeye ekleyin.  
  
2.  Çözüm Gezgini'nde, proje düğümüne sağ tıklayın seçme **Ekle &#124; NuGet paketlerini Yönet**.  NuGet ve NuGet ekleme hakkında daha fazla bilgi için bkz: paketleri [NuGet belgelerine](/NuGet) ve [Paket Yöneticisi kullanıcı Arabirimi](/NuGet/Tools/Package-Manager-UI) Konular.  
  
3.  VisualStudioExtensibility gelen VSIXSignTool arayın ve NuGet paketini yükleyin.  
  
4.  Bu gibi durumlarda, VSIXSignTool şimdi projenin yerel paketler konumdan çalıştırabilirsiniz. İmzalama senaryonuz için aracın komut satırı Yardımı'na başvurun (VSIXSignTool.exe /?).  
  
 Örneğin bir parola korumalı sertifika dosyası ile imzalamak için:  
  
 VSIXSignTool.exe oturum /f \<SertifikaDosyası > /p \<parola > \<VSIXfile >  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Uzantıları Gönderme](../extensibility/shipping-visual-studio-extensions.md)