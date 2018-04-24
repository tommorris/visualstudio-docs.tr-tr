---
title: Karışık mod uygulamalarında hata ayıklama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], mixed-mode
- mixed-mode debugging, property evaluation
- Call Stack window
- mixed-mode debugging
- Call Stack window, mixed-mode debugging
- debugging managed code, mixed code
- mixed-mode debugging, call stack
ms.assetid: 60e34477-ae4e-48c7-9093-3e37f72e1bc3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a0564a1e4a03d0b2d72298f0467e6cd1a91cdab9
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="debugging-mixed-mode-applications"></a>Karışık Mod Uygulamalarında Hata Ayıklama
Bir karma mod uygulaması yerel kod (C++)'yı yönetilen kodla (örneğin, Visual Basic, Visual C# veya ortak dil çalışma zamanında çalışan C++) bir araya getiren herhangi bir uygulamadır. Karışık mod uygulamalarında hata ayıklama büyük ölçüde saydam [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]; tek modlu uygulama hata ayıklama çok farklı değildir. Ancak birkaç özel nokta vardır.  
  
## <a name="enable-c-edit-and-continue-in-mixed-mode-debugging"></a>C++ Düzenlemeyi Etkinleştir ve Karma Mod Hata Ayıklamaya Devam Et  

Düzenle ve devam et için C++ etkinleştirmek için bkz: [etkinleştirme ve devre dışı Düzenle ve devam et](../debugger/how-to-enable-and-disable-edit-and-continue.md).

> [!NOTE]
> Visual Studio 2013'de C++ için Düzenle ve Devam Et'i kullanmak için eski hata ayıklama alt yapısına dönmeniz gerekir. Bkz: [uyumluluk modunda Yönetilen Visual Studio 2013 geçiş](http://blogs.msdn.com/b/visualstudioalm/archive/2013/10/16/switching-to-managed-compatibility-mode-in-visual-studio-2013.aspx) Microsoft uygulama yaşam döngüsü yönetimi blogunda.  
  
## <a name="property-evaluation-in-mixed-mode-applications"></a>Karma Mod Uygulamalarında Özellik Değerlendirme  
 Karma modlu bir uygulamada, hata ayıklayıcı tarafından özelliklerin değerlendirilmesi maliyetli bir işlemdir. Sonuç olarak, atlama gibi hata ayıklama işlemleri yavaşlamaya neden olabilir. Daha fazla bilgi için bkz: [Stepping](http://msdn.microsoft.com/en-us/8791dac9-64d1-4bb9-b59e-8d59af1833f9). Karma mod hata ayıklama içinde düşük performansla karşılaşırsanız, hata ayıklayıcısını penceresindeki özellik değerlendirmesini devre dışı bırakmayı düşünebilirsiniz.  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
#### <a name="to-turn-off-property-evaluation"></a>Özellik değerlendirmeyi devre dışı bırakmak için  
  
1.  Üzerinde **Araçları** menüsünde seçin **seçenekleri**.  
  
2.  İçinde **seçenekleri** açık iletişim kutusunu **hata ayıklama** klasörü ve select **genel** kategorisi.  
  
3.  Clear **özellik değerlendirmesi ve diğer dolaylı işlev çağrılarını etkinleştirme** onay kutusu.  
  
 Yerel çağrı yığınları ve yönetilen çağrı yığınları farklı olduğundan, hata ayıklayıcı karma kod için tam çağrı yığınını her zaman sağlayamaz. Yerel kod yönetilen kodu çağırdığında, bazı tutarsızlıklar görebilirsiniz. Daha fazla bilgi için bkz: [karışık kod ve eksik bilgiler çağrı yığını penceresinde](../debugger/mixed-code-and-missing-information-in-the-call-stack-window.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen kodda hata ayıklama](../debugger/debugging-managed-code.md)