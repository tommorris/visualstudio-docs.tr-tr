---
title: "Kabuğu (yalıtılmış veya tümleşik) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio shell
- Visual Studio, Shell
- Shell [Visual Studio]
- Visual Studio shell, shell-based applications
- Shell [Visual Studio], shell-based applications
ms.assetid: c64a9bf0-9bf8-45c3-8fa2-306fa6cab66a
caps.latest.revision: "25"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 92462699141f9d0a1af2d9eb461caadf4ee467ef
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="shell-isolated-or-integrated"></a>Kabuğu (yalıtılmış veya tümleşik)
Tümleşik veya yalıtılmış modda kendi Visual Studio tabanlı bir uygulama oluşturabilirsiniz. Tümleşik modda Visual Studio özelliklerinin yanı sıra, uygulamanızın kullanılabilir. Yalıtılmış modda yanı sıra kendi uzantısı dağıtmak istediğiniz Visual Studio özelliklerinin bir alt kümesi seçin.  
  
## <a name="integrated-mode"></a>Tümleşik mod  
 Tümleşik mod, özel araçlar birlikte standart Visual Studio özellikleri kullanmak, kullanıcılarınızın sağlar. Tümleşik kabuk programlama dilleri ve yazılım geliştirme araçlarına öncelikle barındırmak için tasarlanmıştır.  
  
 Tümleşik Kabuk üzerinde otomatik olarak oluşturulan özel araçlar aynı bilgisayarda yüklü Visual Studio diğer sürümü ile birleştirin. Visual Studio zaten yüklü değilse, tümleşik Visual Studio Kabuğu'nu yeniden dağıtılabilir sürümünü sağlayabilirsiniz.  
  
 Tümleşik Visual Studio Kabuğu'nu yeniden dağıtılabilir sürümünü programlama dilleri ve ilgili proje sistemlerini destekleyen özellikler içermez.  
  
> [!NOTE]
>  Visual Studio Kabuğu tümleşik mod, Visual Studio Express sürümleri dışındaki tüm sürümleri ile birlikte yüklenebilir.  
  
 Daha fazla bilgi için bkz: [Visual Studio Kabuğu (tümleşik)](visual-studio-shell-integrated.md).  
  
## <a name="isolated-mode"></a>Yalıtılmış mod  
 Yalıtılmış mod yan yana çalıştırma özel araçlar oluşturmanıza imkan tanır diğer Visual Studio sürümleri ile. Öncelikle tüm standart Visual Studio özelliklere bağlı olarak Visual Studio Hizmetleri olmadan erişebilirsiniz araçları için hazırlanmıştır. Yalıtılmış Visual Studio Kabuğu oluşturulan uygulamaların görünümünü özelleştirebilirsiniz. Kolayca, görünmesi uygulamanız ile birlikte istemediğiniz menü komut gruplarını ve özellikler devre dışı bırakabilirsiniz.  
  
 Daha fazla bilgi için bkz: [Visual Studio yalıtılmış Kabuk](visual-studio-isolated-shell.md).  
  
## <a name="distributing-your-integrated-or-isolated-shell-application"></a>Tümleşik veya yalıtılmış Kabuk uygulamanızı dağıtma  
 Tümleşik veya yalıtılmış Kabuk uygulamanızı dağıtmak için uygulamanız, bir özel tümleşik veya yalıtılmış Kabuk yeniden dağıtılabilir ve bir yükleme programı eklemeniz gerekir. Dağıtım ve yükleme hakkında daha fazla bilgi için bkz: [dağıtma yalıtılmış kabuk uygulamaları](distributing-isolated-shell-applications.md).  
  
> [!IMPORTANT]
>  [Son kullanıcı lisans sözleşmesi (EULA)](https://www.visualstudio.com/en-us/support/legal/mt171552) Kabukları Visual Studio tümleşik ve yalıtılmış bir bölüm veri koleksiyonunu içerir (**bölüm 3. Veri**).  Uygulamanıza oluşturmak ya da tümleşik veya yalıtılmış Kabuk yazılımın kullanıcılardan Microsoft tarafından toplanan müşteri kullanım verilerini açıklar. Daha fazla bilgi için bkz: [Microsoft Visual Studio ürün ailesi gizlilik bildirimi](https://www.visualstudio.com/en-us/dn948229).  
>   
>  Uygulamanız aracılığıyla, müşterilerinizin ayrı kullanım verilerini toplamak, uygun dikkat edin, Topla, uygulamanızın kullanıcılara sağlamanız gerekir.  Visual Studio Yazılım Geliştirme Seti lisans göre uygulamanızı bir parçası olarak yalıtılmış veya tümleşik Kabuk yazılım dağıttığınızda aşağıdakilerden birini içermelidir:  
>   
>  -   Uygulama lisansı bir parçası olarak son kullanıcı lisans sözleşmesi  
> -   Visual Studio koruyan koşullarını kabul müşterilerinize gerektiren kendi EULA'yı tümleşik veya kabuk yazılım için Microsoft son kullanıcı lisans koşullarını olarak Kabuk en az kadar yalıtılmış  
  
## <a name="additional-resources"></a>Ek Kaynaklar  
 Yeniden dağıtılabilir paketler hakkında daha fazla bilgi için bkz: [Visual Studio genişletilebilirlik indirmeleri](http://go.microsoft.com/fwlink/?LinkID=119298) Web sitesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio uzantıları aktarma](../shipping-visual-studio-extensions.md)