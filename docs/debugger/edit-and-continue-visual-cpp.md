---
title: Düzenle ve devam et (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 05/31/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue [C++]
- debugging [C++], Edit and Continue
- C/C++, Edit and Continue
ms.assetid: 1815251e-a877-433e-9e5e-69bd9ba254c7
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 5d5195dd92e53a6657747758c03c87ee5463c1d5
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31474554"
---
# <a name="edit-and-continue-visual-c"></a>Düzenle ve Devam Et (Visual C++)
Düzenle ve devam et, Visual C++ projelerinde kullanabilirsiniz. Bkz: [desteklenen kod değişiklikleri (C++)](../debugger/supported-code-changes-cpp.md) Düzenle ve devam et sınırlamaları hakkında bilgi için.
  
Visual Studio 2015 güncelleştirme 3'ü iyileştirmeleri hakkında daha fazla bilgi için bkz: [C++ Düzenle ve devam et Visual Studio 2015 güncelleştirme 3'te](https://blogs.msdn.microsoft.com/vcblog/2016/07/01/c-edit-and-continue-in-visual-studio-2015-update-3/).  
  
 [/Zo (geliştirmek en iyi duruma getirilmiş hata ayıklama)](/cpp/build/reference/zo-enhance-optimized-debugging) Visual Studio 2013 güncelleştirme 3'te tanıtılan derleyici seçeneği olmadan ikili dosyaları derlenmiş bu ek bilgiler .pdb (symbol) dosyaları ekler [/Od (devre dışı bırak (Hata Ayıkla)) ](http://msdn.microsoft.com/library/aafb762y.aspx) seçeneği.  
  
 **/ZO** devre dışı bırakır Düzenle ve devam et. Bkz: [nasıl yapılır: iyileştirilmiş kodda hata ayıklama](../debugger/how-to-debug-optimized-code.md).  
  
##  <a name="BKMK_Enable_or_disable_automatic_invocation_of_Edit_and_Continue"></a> Etkinleştirmek veya devre dışı Düzenle ve devam et  
 Geçerli hata ayıklama oturumu sırasında uygulanan istemediğiniz koduna düzenlemeleri yapıyorsanız Düzenle ve devam et otomatik çağrılmasını devre dışı bırakmak isteyebilirsiniz. Aynı zamanda Otomatik Düzenle ve devam et yeniden etkinleştirebilirsiniz.

> [!IMPORTANT]
> Gerekli yapılandırma ayarlarını ve özellik uyumluluğu hakkında diğer bilgiler için [C++ Düzenle ve devam et Visual Studio 2015 güncelleştirme 3'te] bakın (https://blogs.msdn.microsoft.com/vcblog/2016/07/01/c-edit-and-continue-in-visual-studio-2015-update-3/.
  
1.  Hata ayıklama oturumunda varsa, hata ayıklamayı durdurun (**Shift + F5**).

2. Üzerinde **Araçları** menüsünde seçin **seçenekleri**.
  
3.  İçinde **seçenekleri** iletişim kutusunda **hata ayıklama > Genel**.

4.  Etkinleştirmek için seçin **etkinleştirmek Düzenle ve devam et**. Devre dışı bırakmak için onay kutusunu temizleyin.
  
5.  İçinde **Düzenle ve devam et** grubu seçin veya temizleyin **etkinleştirmek yerel Düzenle ve devam et** onay kutusu.  
  
 Bu ayar değiştirmeye çalıştığınız tüm projeleri etkiler. Bu ayarı değiştirdikten sonra uygulamanızı yeniden gerekmez. Ayarını yaparsanız, komut satırından veya bir derleme görevleri dosyası uygulamanızı, ancak Visual Studio ortamında hata ayıklama, Düzenle ve devam et kullanmaya devam edebilirsiniz **/zı** seçeneği.  
  
##  <a name="BKMK_How_to_apply_code_changes_explicitly"></a> Açıkça kod değişiklikleri uygulama  
 Visual C++'da, Düzenle ve devam et iki yolla kod değişiklikleri uygulayabilirsiniz. Kod değişiklikleri uygulanabilir örtük olarak, bir yürütme komutu seçtiğinizde veya açıkça kullanarak **kod değişikliklerini uygulama** komutu.  
  
 Kod değişiklikleri açıkça uyguladığınızda, programınızı hiçbir yürütme oluşur kesme modunda - kalır.  
  
-   Açıkça kod değişiklikleri uygulamak için üzerinde **hata ayıklama** menüsünde seçin **kod değişikliklerini uygulama**.  
  
##  <a name="BKMK_How_to_stop_code_changes"></a> Kod değişikliklerini durdurma  
 Düzenle ve devam ederken kod değişiklikleri uygulama sürecinde, işlemi durdurabilirsiniz.  
  
 Kod değişiklikleri uygulama durdurmak için:  
  
-   Üzerinde **hata ayıklama** menüsünde seçin **kod değişikliklerini uygulamayı Durdur**.  
  
 Kod değişiklikleri yalnızca uygulanmakta olduğunda bu menü öğesi görünür olur.  
  
 Bu seçeneği seçerseniz, kod değişiklikleri hiçbiri kabul edilir.  
  
##  <a name="BKMK_How_to_reset_the_point_of_execution"></a> Yürütme noktası sıfırlama  
 Bazı kod değişiklikleri Düzenle ve devam et değişiklik uyguladığında yeni bir konuma taşımak için yürütme noktası neden olabilir. Düzenle ve devam et yerleştirir yürütme noktası olarak doğru bir şekilde, ancak sonuçları tüm durumlarda doğru olmayabilir.  
  
 Visual C++'da, bir iletişim kutusu yürütme noktası değiştiğinde bildirir. Hata ayıklama devam etmeden önce konumun doğru olduğunu doğrulamanız gerekir. Doğru değilse, **sonraki deyimi Ayarla** komutu. Daha fazla bilgi için bkz: [Set yürütmek için sonraki deyimi](http://msdn.microsoft.com/library/y740d9d3.aspx#BKMK_Set_the_next_statement_to_execute).  
  
##  <a name="BKMK_How_to_work_with_stale_code"></a> Eski kod ile çalışmak nasıl  
 Bazı durumlarda, Düzenle ve devam et kod değişiklikleri yürütülebilir dosyaya hemen uygulanamıyor, ancak hata ayıklama devam ederseniz kod değişiklikleri daha sonra uygulayabilmek için olabilir. Bu geçerli işlevi çağıran bir işlev düzenlerseniz veya bir işlev çağrı yığınında 64 bayttan fazla yeni değişkenleri eklerseniz gerçekleşir  
  
 Böyle durumlarda, hata ayıklayıcı değişiklikler uygulanabilir kadar özgün kod yürütmeye devam eder. Eski kod bir geçici kaynak dosya pencere başlık içeren bir ayrı kaynak penceresinde olarak gibi görünür `enc25.tmp`. Düzenlenen kaynak özgün kaynak penceresinde görünmeye devam eder. Eski kod düzenlemeye çalışırsanız, bir uyarı iletisi görüntülenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Desteklenen Kod Değişiklikleri (C++)](../debugger/supported-code-changes-cpp.md)