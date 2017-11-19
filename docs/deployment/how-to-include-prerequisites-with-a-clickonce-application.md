---
title: "Nasıl yapılır: ClickOnce uygulamasına Önkoşullar dahil | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c66bf0a5-8c93-4e68-a224-3b29ac36fe4d
caps.latest.revision: "16"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 18431ea15b53959234da4b2c6dedb24b8fa2e390
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-include-prerequisites-with-a-clickonce-application"></a>Nasıl yapılır: ClickOnce Uygulamasına Önkoşullar Dahil Etme
Önkoşul yazılım dağıtabilmeniz için önce bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama, ilk indirmeniz gerekir bu Önkoşullar geliştirme bilgisayarınıza yükleyicisi paketleri. Ne zaman bir uygulamayı yayımlamak ve seçin **Uygulamamla aynı konumda önkoşulları karşıdan**, yükleyici paketlerini, yoksa bir hata meydana gelir **paketleri** klasör.  
  
> [!NOTE]
>  .NET Framework için bir yükleyici paketi eklemek için bkz: [geliştiriciler için .NET Framework Dağıtım Kılavuzu](http://msdn.microsoft.com/library/ee942965\(v=vs.110\).aspx).  
  
##  <a name="Package"></a>Package.xml kullanarak bir yükleyici paketi eklemek için  
  
1.  Dosya Gezgini'nde Aç **paketleri** klasör.  
  
     Varsayılan olarak, C:\Program Files\Microsoft Visual Studio 14.0\SDK\Bootstrapper\Packages 32 bit sistemdeki ve 64-bit sisteminde C:\Program Files (x86) \Microsoft Visual Studio 14.0\SDK\Bootstrapper\Packages yoludur.  
  
2.  Eklemek istediğiniz önkoşul klasörünü açın ve ardından yüklü sürümünüz için dil klasörünü açın [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] (örneğin, **tr** İngilizce için).  
  
3.  Not Defteri'nde açın **Package.xml** dosya.  
  
4.  Bulun **adı** içeren öğeyi **http://go.microsoft.com/fwlink**ve URL'yi kopyalayın. Dahil **LinkId** bölümü.  
  
    > [!NOTE]
    >  Yoksa **adı** ögesinin **http://go.microsoft.com/fwlink**, açık **Product.xml** dosya önkoşul kök klasöründe ve bulun  **fwlink** dize.  
  
    > [!IMPORTANT]
    >  Bazı ön koşullar (örneğin, 32-bit veya 64-bit sistemler için) birden çok yükleme paketine sahiptirler. Birden çok **adı** öğeleri içeren **fwlink**, bunların her biri için kalan adımları yinelemeniz gerekir.  
  
5.  URL'sini tarayıcınızın adres çubuğuna yapıştırın ve ardından, çalıştırmanız veya kaydetmeniz istendiğinde, **kaydetmek**.  
  
     Bu adım, yükleyici dosyasını bilgisayarınıza yükler.  
  
6.  Dosyayı ön koşul için kök klasörüne kopyalayın.  
  
     Örneğin, Windows Installer 4.5 ön koşulları için dosyayı \Packages\WindowsInstaller4_5 klasörüne kopyalayın.  
  
     Şimdi, yükleyici paketi uygulamanız ile dağıtabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: ClickOnce uygulamasıyla Önkoşulları Yükleme](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)