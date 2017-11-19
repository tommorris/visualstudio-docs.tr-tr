---
title: "Visual Studio 2017 hata ayıklayıcıda yenilikler | Microsoft Docs"
ms.custom: 
ms.date: 03/07/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, what's new
- what's new [debugger]
- debugging [Visual Studio], what's new
- what's new [Visual Studio], debugging
ms.assetid: 2aed9caa-2384-4e49-8595-82d8b06cf271
caps.latest.revision: "81"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2a08c56ae60822e6d4183e5789c68cbe383b4dd5
ms.sourcegitcommit: 2c7f48ad6073a81fa927568793633f26cc1f0b15
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/17/2017
---
# <a name="whats-new-for-the-debugger-in-includevsdev15miscincludesvsdev15mdmd"></a>Hata Ayıklayıcısı'ndaki yenilikler nelerdir?[!include[vs_dev15](../misc/includes/vs_dev15_md.md)]

Hata ayıklayıcı bu yeni özellikler içerir:

- 15,5, yeni **anlık görüntü hata ayıklayıcı** ilgilendiğiniz kod yürüttüğünde üretim uygulamalarınızın bir anlık görüntüsünü alır. Bir anlık görüntüyü almaya hata ayıklayıcı istemek üzere kodunuzda snappoints ve logpoints ayarlayın. Hata ayıklayıcı tam olarak ne üretim uygulamanızın trafiğini etkilemeden sorun oluştu görmenizi sağlar. Anlık görüntü hata ayıklayıcı üretim ortamlarında ortaya çıkan sorunları çözmek için gereken süreyi önemli ölçüde azaltmaya yardımcı olabilir.

    Anlık görüntü koleksiyonu, Azure App Service içinde çalışan aşağıdaki web uygulamaları için kullanılabilir:

    * .NET Framework 4.6.1 çalışan ASP.NET uygulamalarını veya sonraki bir sürümü.
    * .NET Core 2.0 veya daha sonra Windows üzerinde çalışan ASP.NET Core uygulamaları.

    Daha fazla bilgi için bkz: [Debug anlık görüntü hata ayıklayıcı kullanarak canlı ASP.NET uygulamaları](../debugger/debug-live-azure-applications.md).

- Yalnızca, Visual Studio kuruluştaki 15,5 yeni **IntelliTrace adım sonradan** otomatik olarak bir anlık görüntüsünü her kesme ve hata ayıklayıcı uygulamanızın adım olayını alır. Kaydedilmiş anlık görüntüler, önceki kesme noktaları veya adımları geri dönün ve geçmişte haliyle uygulamanın durumunu görüntülemek etkinleştirin. IntelliTrace adım arka önceki uygulama durumu görmek istediğiniz ancak hata ayıklamayı yeniden başlatın veya istenen uygulama durumu yeniden istemediğiniz durumlarda size zaman kazandırabilir.

    Gidin ve görüntülemek anlık görüntülerini kullanarak **adım geriye dönük** ve **İleri** hata ayıklama araç çubuğu düğmeleri. Bu düğmeleri görünür olayları gidin **olayları** sekmesinde **tanılama araçları** penceresi.

    ![Geri ve İleri düğmelerini adım](../debugger/media/intellitrace-step-back-icons-description.png  "adım geri ve İleri düğmelerini")

    Daha fazla bilgi için bkz: [görüntülemek IntelliTrace adım geri kullanarak anlık görüntüsünü](../debugger/how-to-use-intellitrace-step-back.md) sayfası.

- **Özel durum Yardımcısı** özel durum Yardımcısı'nın yerini alır ve hatanın oluştuğu kalıcı olmayan iletişim kutusunda görüntülenir. **Özel durum Yardımcısı** herhangi bir iç özel durum, hata ayıklayıcı (varsa) göre ek analiz için daha hızlı erişim ve anında erişim sağlayan **Exception ayarlarını** özel durum için. Bunu görmek için gereken bir şey engelliyorsa özel durum Yardımcısı kayan görünümüne de sürüklenebilir.

    Örneğin, bir **NullReferenceException** şimdi null başvuru (ek bilgiler) sahip değişkeni gösterir.

    ![Hata Ayıklayıcı'nın özel durum Yardımcısı](../debugger/media/dbg-exception-helper.png "DbgExceptionHelper")

    Daha fazla bilgi için bkz: [yeni özel durum Yardımcısı Visual Studio kullanarak](https://blogs.msdn.microsoft.com/visualstudioalm/2016/03/31/using-the-new-exception-helper-in-visual-studio-15-preview/) blog postası.

- Şimdi bir hata ayıklayıcısı'ndaki seçerek duraklatıldı sırada kod satırı için çalıştırabilirsiniz **yürütülmesi için burada** yeşil ok simgesi (gördüğünüz simgeyi bir kod satırı getirildiğinde sırasında). Bu, geçici kesme noktalarını ayarlama gereğini ortadan kaldırır.

    ![Hata ayıklayıcı tıklatın çalıştıran](../debugger/media/dbg-run-to-click.png "DbgRunToClick") 

- Koşullar durumlar ayarlayabilirsiniz **Exception ayarlarını** iletişim kutusu (kullanarak bunu yapabilirsiniz **koşulu Düzenle** özel ayarları iletişim kutusunda ya da sağ tıklatma menüsünü kullanarak simgesi özel durum.) Şu anda desteklenen koşullar dahil etmek veya hariç özel durumuna modül adlarını içerir.

    ![Bir özel durum koşullara](../debugger/media/dbg-conditional-exception.png "DbgConditionalException")

- İletişim kutusu, daha hızlı bir şekilde eklemek için gereken işlem tanımanıza yardımcı olacak yeni bir arama özelliği içerir işlem iliştirin.

    ![Aramada ekleme işlemi için](../debugger/media/dbg-attach-to-process-search.png "DbgAttachToProcessSearch") 

Bu yeni özellikler hakkında daha fazla bilgi için bkz: [için sürüm notları [!include[vs_dev15](../misc/includes/vs_dev15_md.md)] ](https://www.visualstudio.com/en-us/news/releasenotes/vs2017-relnotes#debuggingdiag).
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da hata ayıklama](../debugger/index.md)  
 [Hata ayıklayıcı özelliği turu](../debugger/debugger-feature-tour.md)